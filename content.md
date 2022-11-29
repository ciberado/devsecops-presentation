[](.title.coverbg)

![Photo of a plain crossing the sky, by SevenStorm JUHASZIMRUS, ](images/pexels-sevenstorm-juhaszimrus-1436697-crop.jpg)

# DevSecOps in public cloud

Public cloud is an strategic tool for **improving agility** in the application of software
to promote competitiveness in our companies. But moving code to production much faster
is not useful if we loose reliability during the way or if we **compromise the security**
of our people and assets.

::: Notes

The plane crossing the sky is a clear **metaphor** of what we are aiming for: extreme
velocity in a highly controlled development framework.

:::

[](.coverbg)

## Traditional loom

![Top View Photo of Two Person's Hands Weaving, by Karolina Grabowska, https://www.pexels.com/photo/top-view-photo-of-two-person-s-hands-weaving-4219654)](images/pexels-karolina-grabowska-4219654.jpg)


*Weaving fabric is an ancient practice that spans both time and culture. In Maya civilization, the goddess Ixchel taught the first woman how to weave at the beginning of time.*

*The loom threads across the globe from China to Colombia, and dates back to as early as **Ancient Egypt in 4400 BC**. Through centuries, the loom evolved to be the titan of all fabric creation.*

[History of the Loom](https://marylana.com/blogs/news/history-of-the-loom-know-how-your-clothes-are-made)

::: Notes

The traditional loom is a **metaphor** of what happens when you are used to run
your business/servers in a particular way, and how difficult is to change that.

:::

[](.coverbg)

## Industrial revolution

![Three quarter view of a power loom, Wikimedia, https://commons.wikimedia.org/wiki/File:Textiles;_a_three-quarter_view_of_a_power_loom,_with_admirin_Wellcome_V0024096.jpg](images/three-quarter_view_of_a_power_loom.jpg)

*The first power loom was designed in **1786** by Edmund Cartwright and first built that same year. It was refined over the next **47** years until a design by the Howard and Bullough company made the **operation completely automatic**.* 

[Wikipedia, Power loom](https://en.wikipedia.org/wiki/Power_loom)

A similar process is happening with infrastructure administration at all levels, including security.

We are going to talk about how to developers, security teams and the operation staff
can work together in a fast and reliable way, thanks to automation.

::: Notes

* Scaling by automating
* DIfferent skills required

:::

[](.coverbg)

## Networking virtualization

![Las chicas del cable (poster), https://es.wikipedia.org/wiki/Las_chicas_del_cable](images/chicas-del-cable.jpg)

* It is possible to use a fixed infrastructure to provide dynamic configurations
* An early example, at network level, was the cable wiring machines used to stablish phone communications

::: Notes

Draw a graph of six people and then connect them all. You will get n*(n-1)/2 relations.

Now draw the six persons with a dotted matrix (of 3x3, for example) and paint some
dynamic connections between any random pair of people.

![Dynamic and static graphs](images/virtual-network-diagram.jpg)

:::

[](.coverbg)

## Compute virtualization

![A set of boxes in a bigger box](images/boxes-in-boxes.jpg)

* Operating systems are just applications that manages other applications and hardware resources
* It is possible to execute a guest operating system inside a host one
* The host operating system can provide isolation between workloads run inside the guest operating systems

This is very similar to the tactic that we use when we put a set of boxes in a drawer to avoid
mixing all the staff together.

::: Notes

Introduce the concept of HTTPs server, including:

* Virtual machines

![A diagram of a classic OS, a host OS with a guest one, and several VMs](images/virtual-machine-diagram.jpg)

:::

[](.coverbg)

## How applications ring each other

![A photo with several phones, by Alex Andrews, https://www.pexels.com/photo/three-black-handset-toys-821754/](images/pexels-alex-andrews-821754.jpg)

::: Notes

* Applications connected to the network
* IP addresses, as the telephone number of a device
* Ports, as a way to address a particular application

![A diagram of two machines communicating trough IP](images/ip-connectivity-diagram.jpg)

:::

[](.coverbg)

## The Cloud

![A woman in a Data Center, by Christina Morillo, https://www.pexels.com/photo/engineer-holding-laptop-1181316/](images/pexels-christina-morillo-1181316.jpg)


* It is a Data Center with **automation** capabilities to create **dynamic configurations**
* Provides an open **Application Program Interface** for accessing those capabilities
* The use can be exclusive for a particular entity (**private**) or multi-tenant (**public**)

::: Notes

Explain the concept of API server, API call and programable infrastructure.

![Diagram of an API call creating a VM](images/cloud-diagram.jpg)

:::

[](.coverbg)

## Hyperscalers

![hyperscalers logos](images/hyperscalers.png)

::: Notes

* Describe the main characteristics of each one of those providers.
* Talk about what hyperscale mean (global footprint, real capacity)

[](.coverbg)

## Lab: exploring the default network

![Children with laptops in a classroom, by Max Fischer, https://www.pexels.com/photo/a-two-girls-using-laptop-with-classmates-5212695/](images/pexels-max-fischer-5212695.jpg)

[](.coverbg)

## Lab: launching a server

![Children in the classroom, by Yan Krukov, https://www.pexels.com/photo/male-teacher-discussing-his-lesson-about-mathematics-8617742/](images/pexels-yan-krukov-8617742.jpg)

[](.coverbg)

## Lab: creating a brand new network

![Girls doing tasks at school, by Anastasia Shuraeva,https://www.pexels.com/photo/children-studying-inside-a-classroom-8466695/](images/pexels-anastasia-shuraeva-8466695.jpg)

[](.coverbg)

## Lab: detecting security problems in the code

![Children studying, by Norma Mortenson, https://www.pexels.com/photo/group-of-kids-studying-together-8457297/](images/pexels-norma-mortenson-8457297.jpg)

[](.coverbg)

## Imperative vs...

![Children cooking, by Kampus Production, https://www.pexels.com/photo/children-preparing-food-6481587/](images/pexels-kampus-production-6481587.jpg)

[](.coverbg)

## ...vs declarative

![Bartender serving a burger, by Edward Eyer, https://www.pexels.com/photo/person-holding-square-white-ceramic-plate-687824/](images/pexels-edward-eyer-687824.jpg)

[](.coverbg)

## Lab: advanced automated security testing

![little girl in pink dress drawing on blackboard, by Yan Krukov, https://www.pexels.com/photo/little-girl-in-pink-dress-drawing-on-blackboard-beside-a-woman-8613148/](images/pexels-yan-krukov-8613148.jpg)

[](.coverbg)

## Lab: declaratively deploying a data center

![elementary students writing on a paper, by Artem Podrez, https://www.pexels.com/photo/elementary-students-writing-on-a-paper-8087854/](images/pexels-artem-podrez-8087854.jpg)

[](.coverbg)

## Lab: declaratively updating existing resources

![female student doing a ghumbs up in front of a blackboard, by Yan Krukov, https://www.pexels.com/photo/female-student-doing-a-thumbs-up-in-front-of-a-blackboard-8617709/](images/pexels-yan-krukov-8617709.jpg)


[](.coverbg)

![teachers and preschoolers doing yoga, by Yan Krukov, https://www.pexels.com/photo/teachers-and-preschoolers-doing-yoga-8613362/](images/pexels-yan-krukov-8613362.jpg)


[](.coverbg)

## Pipeline automation

![Ford asian factory, by Ford, https://www.flickr.com/photos/fordapa/3886403372](images/ford-asian-factory.jpg)


::: Notes

Link this photography to the loom with which we started the explanation!

:::

[](.coverbg)

![Fireworks, by Anna-Louise, https://www.pexels.com/photo/photo-of-fireworks-1387577/](images/pexels-annalouise-1387577.jpg)