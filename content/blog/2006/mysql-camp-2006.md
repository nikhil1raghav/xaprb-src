---
title: MySQL Camp 2006
date: "2006-11-15"
url: /blog/2006/11/15/mysql-camp-2006/
categories:
  - Databases
---
I recently attended the [MySQL Camp](http://mysqlcamp.org/) 2006 un-conference at Google's headquarters in Mountain View, California. This article is a high-level overview of the event. If you didn't go, you really missed something good. Go to the next one!

### The event

The event brought together the MySQL community in a distinctly un-conference setting, to gather in groups to discuss or hack on something, rather than sitting in chairs with donuts and coffee listening to someone show Powerpoint slides branded with corporate logos. There were no vendor booths, very few projected presentations, and no boredom---at least not for me.

The conference was organized via a wiki, and there was no set schedule. We were editing the list of sessions constantly, even during the event. Likewise, attendance was free and "registration" only meant writing your name down so Google could issue you a visitor pass. Google provided a bunch of rooms with tables and comfy chairs, catered meals, and helpful and friendly organizing staff (seriously, they went above and beyond).

As of a few days before the event, there were fewer than a hundred attendees registered, but in the last few days everyone and their cousin signed up. At last count there were 225 participants from all over the world. This included people from all walks of life. There were government employees, folks from startups, Google employees, interested hackers, both of MySQL's founders, MySQL developers and the CEO, and lots more. Many of the names were well-known to wider communities. These people founded and architected companies who are household names today: Friendster, YouTube, Flickr, and so on.

Despite that, the atmosphere was generally mutual respect and fun. There were no wannabe rock star blogger personalities parading around. I was happy being able to talk with the MySQL founders and developers and be treated as an equal. For example, at one point [Monty Widenius](http://en.wikipedia.org/wiki/Monty_Widenius) invited me to hop in his car and explain an idea on the way to supper with the group. While I talked on the drive, I felt completely listened to and respected, and learned a lot. I've never met a group of more down-to-earth, unassuming programmers. I find the smartest programmers are sometimes impatient and egotistical, but not in this group. It's proof that people go far by being really nice.

### The sessions

Sessions were impromptu, often written on the wiki but sometimes just posted on a whiteboard. I didn't make it to every session, but here are some of the highlights of those I did attend (you can look around on other blogs for notes on the sessions: try [Sheeri Kritzer's blog](http://sheeri.com/), [Ronald Bradford's blog](http://blog.arabx.com.au/), and [James Briggs' blog](http://jebriggs.com/blog/)).

Friday started off with everyone in one big room introducing themselves and getting a sense of what the group was interested in. I had some prior commitments, so I didn't make it to sessions much of Friday, but even the morning session was great. I met a ton of people with whom I'd emailed or chatted with on IRC. I also met authors of some of my favorite books, people running projects and companies about which I've read with great interest ([Greenplum](http://www.greenplum.com/), for example), and lots of people from the wider community. Also present was Oracle's Ken Jacobs, who is responsible for InnoDB (Oracle acquired InnoDB last year).

In the afternoon I attended two sessions by Google employees. In case you didn't know, Google runs "very large" clusters of "many" MySQL servers behind such applications as Adwords. Whenever anyone asks how many, they just pause and say "many." They've developed tools to help manage servers, such as killing queries simultaneously on many servers, dumping and reloading data at high speed, and so forth. Some of these tools are [available to the public](http://code.google.com/p/google-mysql-tools/). They also explained how they scale to mind-boggling size (but not what for---that is a secret). And finally, they don't run a stock MySQL server; they have their own internal patches to both the server and InnoDB (they use InnoDB exclusively). Mark Callaghan explained some of these. The MySQL developers and Mr. Jacobs listened intently.

On Saturday I gave a demo of innotop and asked people to discuss monitoring strategies in general. I listened for ideas, as we haven't really scaled our operation to where we need many tools to help us monitor a bunch of servers. I heard a lot of experience with tools like [cacti](http://cacti.net/) and [Groundwork](http://www.groundworkopensource.com/). I also heard a lot of nice feedback on innotop. Some people told me things like it "pulled them out of the fire" several times. One of [MySQL's Professional Services](http://www.mysql.com/consulting/) consultants told me he considers it "indispensable," and has recommended it to all his clients, as well as sending it around among the rest of the Professional Services team. The people in the session also gave me good ideas on where to go with future features, which was probably the best part of all. I got a better sense of how people use it and what they want to do with it than I could ever get from this blog, and I'll be acting on that feedback. I also learned that it is time to write a book or other significant documentation for innotop, as I got requests for several features that are already included, but I had to think hard to remember how to get to them!

I attended half of [Sheeri Kritzer's](http://sheeri.com/) session on boolean optimizations, and then sat in on half of the session on [GIS extensions in the MySQL server](http://dev.mysql.com/doc/refman/5.0/en/spatial-extensions.html). I found this particularly interesting, as my wife's archaeology projects often store spatial data, and this could be a more powerful way to represent and manipulate that data. Several other attendees have used or are using the spatial extensions in real applications, such as [MotionBased](http://www.motionbased.com/). Another attendee mentioned his plans to scale a database of astronomical objects to astronomical size: 100 petabytes. Nobody in the room knew if MySQL could scale to that size, but some were certain Oracle and Postgres couldn't. The GIS extensions are in a funny place right now, as they were implemented in 2001 (as Monty recalled) but have stagnated since then because no one gave any GIS feedback to MySQL. Here again the MySQL developers asked what the users needed, and gave every evidence of willingness to move things in that direction. Apparently there are some low-hanging fruit that could be plucked to start with, and then take it from there.

Later that evening Jeremy Cole and others set up a general discussion about MySQL replication. The discussion ranged all over the map---anything about replication, and many things not about replication, were fair game. When you have that many smart, experienced people in a room, you can bring up just about anything and get either an answer or some options you didn't know about before.

On Sunday the attendance was lower, so we re-organized everything into one big room for convenience. We had a discussion about several new storage engines for MySQL, including one the community is watching eagerly: Falcon, which is the brainchild of a relational database pioneer [Jim Starkey](http://en.wikipedia.org/wiki/Jim_Starkey). Monty also discussed the features in the upcoming MyISAM++, and Brian Aker went over his recent work on an engine that uses [memcache](http://www.danga.com/memcached/) for its storage. Finally, we heard about [ScaleDB](http://scaledb.com/), which is an upcoming storage engine that uses [Patricia Tries](http://en.wikipedia.org/wiki/Patricia_trie) instead of standard [B-Trees](http://en.wikipedia.org/wiki/B-tree). I'm no expert on this, but it was a fascinating talk and sounds like a solution to certain problems. We also had a lively and technical discussion with [Nitin Borwankar](http://www.tagschema.com/) about designing schemas to support tagging and folksonomy applications like [del.icio.us](http://del.icio.us/). Finally, we rounded it out with a demo from Sheeri, who showed us her company's production installation of the new MySQL Enterprise Dashboard, which is a monitoring system that's part of the new [MySQL Network](http://www.mysql.com/products/enterprise/) offerings (for certain license levels). It looks like a useful tool, and there was lots of feedback from the participants, which the MySQL developers noted down.

### Storage engines and the pluggable architecture

One thing that really clicked for me at this conference is the MySQL architecture. Have you ever thought about what a breakthrough it is to have a database server that supports many storage engines, each with their own strong points? Take a look around the market---you find specialized, single purpose servers, or servers that *try* to be all things to everyone. MySQL is the only product I know of that lets you keep the same server, the same management and tuning, same tools and administration and query language etc etc---and plug an entirely different back-end into it. This is truly an amazing architectural decision. Look at the choices you already have:

*   MyISAM
*   Cluster
*   Federated
*   Archive
*   Merge
*   Memory
*   CSV
*   Blackhole
*   InnoDB

This positions MySQL extremely well to compete in a market that has bloated servers that are not quite what anyone actually needs. I think MySQL the company has a bright future for this reason alone, but that's not the only thing going for them. I've been reading about [pluggable storage engines](http://solutions.mysql.com/engines.html) for a while now, probably much like you, and never thought much about it, but at this event I sensed an almost tangible electricity in the air. What if you took an innovative product that does what nobody's done before (your choice of storage engines) and made it possible to just plug storage engines in without recompiling the server? That's a quantum leap for both users and developers. I may have missed the significance till now, but developers haven't. Do you know how many new storage engines are being developed for MySQL? In addition to the existing ones, I'm aware of at least the following, in various degrees of development, some of which are pluggable:

*   [Falcon](http://mike.kruckenberg.com/archives/2006/04/jim_starkey_int.html): designed specifically for modern enterprise and Web 2.0 applications.
*   [solidDB](http://www.soliddb.com/mysql/): a multi-threaded, transactional storage engine for MySQL Server. It is designed for mission-critical implementations that require a robust, transactional database.
*   [OpenOLAP](http://forge.mysql.com/projects/view.php?id=13): An open source OLAP (On-Line Analytical Processing) tool.
*   [PrimeBase XT (PBXT)](http://www.primebase.com/xt/): a new transactional database engine for MySQL. It has been designed for modern, web-based, high concurrency environments.
*   [NitroEDB](http://www.nitrosecurity.com/): an extreme performance and highly scalable relational database technology.
*   Filesystem: will allow you to access your filesystem through SQL, doing such things as querying and updating attributes of image files.
*   [memcache](http://tangent.org/index.pl?lastnode_id=478&node_id=506): access memcache via SQL.
*   [ScaleDB](http://scaledb.com/): "currently in stealth mode. Of course, the name itself speaks volumes."
*   I've heard discussion of a storage engine whose physical storage is on
	 Amazon S3.
*   [BrightHouse](http://www.infobright.com/): a highly-compressed engine designed for archiving data from multi-terabyte data warehouses. BrightHouse compresses data at an average ratio of 10:1 (peak compression ratios exceed 30:1), whilst maintaining immediate and comprehensive query capability.

Notice how nobody's developing a storage engine for okay performance on moderate amounts of data? I guess that's up to me. I'll call it SoSoDB.

### What I got out of it

I got a lot out of this conference:

*   I met lots of great people.
*   I learned a lot. Mostly I learned about new options I didn't know about before, which is something I always love. I believe there are always more options in life overall than I know about, and it's great when I find out about them. It opens up so many more possibilities. I have so many ideas now about better ways to architect our systems for another round of scale-up before we scale out, and how to do that better when the time comes.
*   I got a better sense of what the MySQL community and company are like, and I'm prouder than ever to be part of it.
*   I learned a lot about what MySQL and its users do well and not so well. For example, the MySQL developers are probably getting less feedback from their users than they would if the users paid for the product, in my opinion, and that hurts everyone in a sense. On the other hand, I'll be the first to say MySQL listens to feedback as much or more than if they were charging for the product---more, actually.

I'd absolutely go to the next one, and I encourage you to do so also. By the way, I'm planning to be at the bigger conference in April as well, so maybe I'll see you there.

It was pretty eye-opening to attend this conference. I've been using MySQL since about 2000 I think, and have bought and read many books. I'm studying for certification. I've been blogging about it for a while, obviously, and reading other people's blogs as well. But I gained an entirely new perspective on the company, the product, and the community around it.


