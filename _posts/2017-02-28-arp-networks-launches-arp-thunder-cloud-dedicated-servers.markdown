---
layout: post
title: "Introducing ARP Thunder™ Cloud Dedicated Servers"
date: 2017-02-28T16:58:48-08:00
---

The Short
=========

[ARP Thunder™](https://arpnetworks.com/dedicated) is an advanced cloud
offering, giving both the resiliency and flexibility of a VPS with the
power of a dedicated server.  With redundant network, storage, hosts,
and our advanced management Portal.

You can stop here and check out [our new ARP Thunder™
servers for as low as **$40 per month**](https://arpnetworks.com/dedicated).

*However*, we encourage reading below about the motivations and
challenges that brought about the development and birth of this new
offering.  These are not simply low priced dedicated servers, but a new
way of offering dedicated that is a pleasure to manage and help you
sleep easier at night.

The Really Long
===============

We would like to introduce to you a new service that we call [ARP
Thunder™](https://arpnetworks.com/dedicated), a semi-dedicated server
offering that offers the simplicity and resilience of the cloud but with
the power and resources of a dedicated server.

Why not just get a dedicated server?
------------------------------------

Dedicated servers are great, but more and more we're seeing it to be the
case that the people who think they need a dedicated server, in fact,
don't anymore.  With technologies like Ceph (open-source distributed
storage system), KVM/QEMU (virtualization), and the ubiquity of power
efficient, yet powerful, Intel E3 and E5 Xeon processors, one can
segment a physical server into several distinct, non-shared, parts, and
then offer these as what we would call a "semi" dedicated server.

That's great, but still, why?
-----------------------------

Have you ever had a single disk, upon which you relied, fail in a
dedicated server?  Did you have it in a RAID 1 mirror?  Did your RAID
card ever fail and take a sh*t all over your data, completely destroying
both copies?

If not, you haven't been doing this long enough.  Wait.

Do you buy double of everything you need, in case one fails?  If so,
keep doing that and stay with double provisioned dedicated servers; it's
not a bad strategy if you can afford it.

Now, for those that don't double provision everything and _have_ had
disks fail, you know the pain I'm describing.  We feel it too, because
we're up at night just like you, working to replace the failed
components and hoping that your business is not too impacted.  This is a
situation where nobody wins.

[ARP Thunder™](https://arpnetworks.com/dedicated) provides a server
where this scenario becomes obsolete.

But how?
--------

Ceph, if you haven't heard of it or are unfamiliar, is a distributed
storage system designed for performance, resilience and scalability.

We've built our own Ceph cluster and as we started to put it in beta and
then later production, we had a light bulb moment and thought, "This
changes the way we think about storage.  Nobody is going to rely on
single disks or single RAID systems in the future.  Data will no longer
live in a **static place**, but continuously move around (in Ceph) as
conditions change."  Those conditions being, say, an HD failure, an
entire node failure, or a positive event such as adding a new disk, a
new node, or otherwise further expansion for more capacity or
performance.

Now, imagine your dedicated server being able to have a block device
carved out of this cluster, instead of a single physical disk.  We
manage the cluster.  You never have a single point of failure with
regards to your disk.  We both win.

And, using separate classes of pools that we manage, you can choose a
"storage" tier (cheapest, but largest) for your bulk storage needs, and
then a "performance" tier (more expensive, but smaller) of SSD-backed
disks for moderate loads, and/or an "ultra" tier (most expensive,
smallest) of SSD-only disks for the most demanding applications.

Even better, these can all be provisioned instantly, without waiting for
someone to physically swap in/out a disk, install a SAS controller, RAID
card or otherwise build a new server.

But this is only the disk, what about other things that can fail?
-----------------------------------------------------------------

With [ARP Thunder™](https://arpnetworks.com/dedicated), the entire host
node can fail, and your semi-dedicated server will be brought up on a
new node.  You don't need to keep two servers around just in case one
fails; we do this for you.  Since your server's data is safely stored in
Ceph, it can be accessed anywhere in our hosting cluster.

But even better, should we need to perform maintenance on a node or
otherwise take it down, we can plan ahead of time to live migrate your
server to a different node in the cluster.  Live migrations take only
seconds and there is zero downtime.  In our experiments, we usually
don't even lose 1 packet of data when we run a regular continuous ping
during live migration.

It really feels like magic!

How are things like RAM and CPU cores allocated to my server?
-------------------------------------------------------------

It's pretty easy.  Say one of our hosts has 16 cores and we have two
[ARP Thunder™](https://arpnetworks.com/dedicated) machines that want 8
cores.  We give 8 of the 16 cores to one Thunder™ machine and the other
8 to the other one.

RAM is not oversubscribed (but this has always been the case, even with
our smaller VPS systems).  For example, on a 128GB RAM host, your
Thunder™ server could get 64GB of RAM and another server could get the
other 64GB of RAM.  This is a bit of a simplification, because we need
to reserve some RAM for the host OS, but you get the idea.

Why else would I prefer ARP Thunder™ over a dedicated server?
-------------------------------------------------------------

One of the biggest reasons is out-of-band console access.  We've been
working with Supermicro, HP Proliant and (sometimes) Dell dedicated
servers for close to two decades.  In all that time, we still wonder,
why has nobody made a good IPMI / iLO / iDRAC BMC chip yet?!

THEY ALL SUCK.

For console access, they all require some form of Java that your browser
will fight.  Or a stand-alone Java app that has 6 different versions of
a KVM viewer, depending on which host you connect to.  Some work, some
don't.  It's maddening and frustrating.

We believe you should get a console over SSH, not Java!  We already give
serial port access over SSH on our console.cust.arpnetworks.com
management server, and we can do the exact same thing for an [ARP
Thunder™](https://arpnetworks.com/dedicated) machine.

Also, our web console utilizing noVNC is available for [ARP
Thunder™](https://arpnetworks.com/dedicated) machines as well.

Finally, no more fighting for console access on your dedicated server!

OK, so, million dollar question, how much does it cost?
-------------------------------------------------------

[ARP Thunder™](https://arpnetworks.com/dedicated) pricing starts at $40
per month.  Simple as that.

We are starting with 4 basic plans, but we have flexibility to offer
many more.  If you don't see what you need, please [contact
us](https://arpnetworks.com/contact), tell us your needs and goals, and
we'll give you a quote you can't refuse. :)
