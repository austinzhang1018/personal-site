---
layout: post
title: Eboard Update
category: eboard-project-post
date: 2017-08-05 11:35:34
---
Our electric skateboard design is near finalization. The ESC case and battery case are finished and seem pretty sturdy. Now, the only thing we still need to workout is a transmitter/remote and a battery solution. 
Currently, we're using an [HK-GT2B](https://hobbyking.com/en_us/hobbykingr-tmhk-gt2b-3ch-2-4ghz-transmitter-and-receiver-w-rechargable-li-ion-battery-1.html) transmitter/receiver combo meant for an RC car that's rehoused in a 3d printed remote case we found on Thingiverse. While this works fine, the rehousing process for the remote is a little difficult and involves some soldering and cutting to make the bulky RC controller components fit in the small controller. If we were to sell kits for our skateboard, I'd feel better with including a premade controller or at least a controller that's easier to assemble. We could either buy a specialized transmitter/receiver combo or build our own with an Arduino. I think the first option would probably be better. 
Another issue that we've yet to resolve is our battery system. Currently, we're using Lipo batteries that we charge with a balance charger, but if we're going to commercialize our board, we probably don't want to use a balance charger that takes time to set up before each charge. Plug and go would be the best. This problem is easily fixed; all we need is a BMS (Battery Management System). We'd plug the balance leads on our Lipo batteries to the BMS and wire the BMS to a port where we can connect a 25.2-volt charger. The BMS would automatically balance our batteries for us.
The larger battery system problem has to do with the batteries themselves. While Lipo batteries have a very high energy density, the main issue is their short cycle times and instability. Lipo batteries can last for around 400-500 cycles while more stable lithium chemistries, such as LiFePO4 can last up to 2000 cycles.
Another issue, the main issue, is that lipo batteries are a safety concern. Lithium polymer is one of the most unstable lithium battery chemistries, and can easily explode when overcharged or overdischarged.

Here's an example of a lipo explosion.
<iframe width="560" height="315" src="https://www.youtube.com/embed/EseOhC8n7ro?rel=0&amp;start=9" frameborder="0" allowfullscreen></iframe>

Now we won't be shooting BBs at our batteries and they should be protected from rocks and curbs by our battery case, but there's a fair bit of vibration while riding the skateboard and we really don't want to be taking any chances. Currently, our battery case is padded, but we'd prefer to work with more safe batteries. We started to experiment with building our own battery pack using 18650 li-ion cells, but that failed terribly and is for another post.

One last thing that I've been thinking about is the motor mount. I original that both the retaining piece and the motor mount itself can be thinner, and we might even be able to explore reintroducing our two-piece mount. The problem with our original two-piece mount was bending due to the high torque of the motor, but that was before we had the retaining brace. I think the retaining brace takes a significant load off the motor mount and might be enough to allow us to reintroduce some of our previously rejected thinner mount designs.

Most of what I've been writing doesn't make any sense without photos, so I'll include a few down below.

A full view of the bottom of the skateboard. The orange box is the battery case, the blue box is the ESC and receiver, the blue thing attached to the trucks at the top of the picture is the motor mount, and the yellow thing attached to the trucks is the retaining piece.
![Board Bottom]({{ "austinmzhang.com/assets/board-bottom.jpg" | absolute_url }})

A top view of our board. Although there are small points where the screws used to attach the ESC and Battery cases stick out past the grip tape, they're cut to length so they don't actually stick out of the board.
![Board Top]({{ "austinmzhang.com/assets/board-top.jpg" | absolute_url }})

A close up of the battery case with the batteries inside. 
![Batteries]({{ "austinmzhang.com/assets/batteries.jpg" | absolute_url }})

Inside our ESC case. At the top is the receiver, and the main piece is the ESC. The translucent material around the outside is hot glue that we were using to waterproof the ESC. We switched to sealant meant specifically for waterproofing after this picture.
![ESC]({{ "austinmzhang.com/assets/esc.jpg" | absolute_url }})

Our remote control. This is the only piece we didn't design ourselves besides the 3D printed pulley we used for our drive wheel. The file can be found [here](https://www.thingiverse.com/thing:922378). We plan on replacing this controller soon.
![Remote]({{ "austinmzhang.com/assets/remote.jpg" | absolute_url }})

A close up of our motor mount. Note the ridges protruding out of the motor mount; these provide more rigidity and help reduce flexing. The mount is secured using threaded rod to a retaining piece mounted on the truck to hold it in place and to reduce torque on the mount.
![Motor Mount]({{ "austinmzhang.com/assets/motor-mount.jpg" | absolute_url }})