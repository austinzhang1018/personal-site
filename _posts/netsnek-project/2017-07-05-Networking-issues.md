---
layout: post
title: Networking issues
category: netsnek-project-post
date: 2017-07-05 11:35:34
---
One of the issues that has been really difficult for me to solve with this project is coming up with a good networking protocol. In netsnek, there are servers and players. The game is snake/tron, so the only major information players need to receive from the server is the location of other players. The only major information the server needs to receive from the player is the direction in which the player wants to move. There's some other info like leaderboards and when the game starts but that's unrelated to my issue.

My issue is that when sending all the player/server data, either not all of the data is getting through, or the data is getting through too slowly (there's a lot of lag). This issue pertains to sending and receiving directional/map data between the server and player because as the number of players goes up, the amount of network traffic caused by this communication also increases significantly. My network protocol needs to be reliable, lightweight, and fast.

Here are some things I've tried.

My first network protocol was to just send the players the entire map from the server, with the locations of every single snake, every single frame. This, of course, is highly inefficient, but because of the redundant information, it's not that big of a deal if a packet isn't received, the user's display will still update properly when the next packet is sent a fraction of a second later. The issue with this approach is lag. With one or two players, this approach works well, but when you scale up to 5-6 players, the lag starts to become very noticeable. This is because as the number of players increase, not only are you broadcasting more transmissions for each of the new players, you're also broadcasting larger transmissions, as the size of the map increases proportionally with the number of players. Therefore lag increases quadratically with the number of players, and in a fast-paced game like snake, lag makes the game almost unplayable.

My next and current approach at the time of writing this post was to only update pieces of the map that changed. The server would save the state of the map at the last broadcast and would compare the current state to the state at the last broadcast. If there were differences in any points of the map, the server would then send those differences to the players, and the players would update their screens accordingly.

This approach worked well in solving the lag problem; the game can now support its max of 9 players without any noticeable lag. However, it caused a separate issue. Sometimes not all of the packets would go through, and when this happened, the failed broadcasts would create gaps in the player maps. It caused situations where players would think that squares were empty, but there were actually snake pieces there. I'm not really sure why this is happening, the java socket class uses the TCP protocol, which theoretically ensures the delivery of practically every packet. I think the issue might not be related to the transmission of the packets, but to the reception. I'm using Inputstreamreaders to receive the data so I theorized that the dropped packets could be caused by a buffer overflow on the player end. 

To test this theory, I created a separate thread to empty the player buffer and place data into a separate queue as soon as it's received. This way, I could be sure that there's no buffer pileup caused by the main thread waiting on the GUI to draw. However, even after making sure that the buffers weren't filling up, I still had some lost packets.

I think the next approach I'm going to try is a combination of the first two ideas. I'm only going to be transmitting the data for movements that need to be updated, but I'll transmit that data a few times to ensure the message goes through. I'll also combine transmissions. Right now, I update each coordinate independently, so basically if 4 snakes move in a frame, I send 4 different packets with snake locations. This makes the packets small but does create a lot of packets. It might help if I combine these transmissions all into a single broadcast. I hope this method works because I really want to work on a different part of the project like the GUI and settings.

I'll keep you posted on the results.