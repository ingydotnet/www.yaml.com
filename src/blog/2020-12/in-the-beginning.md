---
title: In The Beginning
author: Ingy döt Net
date: December 12, 2020
---
Welcome to our new YAML blog!

This is the very first post.
It's the Beginning.
But that's not what the post is about.

This is the story of how the [YAML data language](https://en.wikipedia.org/wiki/YAML) got its start as far back as [1999](https://www.youtube.com/watch?v=rblt2EtFfC4).
The web was taking over the world.
Rich content was flying around the globe and into your eyeballs in milliseconds, all delivered in plain text package.
HTML!
Amazing!
Hey, let's abstract it a bit and it will become the end-all format for all the world's data communication.
We'll call it XML!
What could go wrong?!

Hold on...
XML?
Really?
I thought this was a story about YAML.
What does XML have to do with it?
Patience...


## Whence YAML?

According to my records...
* The first mention of "YML" was by Clark Evans on `Tue, 30 Nov 1999 22:27:00 -0500 (EST)`
* The first mention of "YAML" was by Simeon Simeonov on `Mon, 14 Feb 2000 13:10:34 -0800`
* Clark announced his purchase of [yaml.org](https://yaml.org) on `Fri, 5 Jan 2001 02:50:35 -0500 (EST)`
* Clark published "YAML Draft 0.1" on `Fri, 11 May 2001 15:50:31 -0500`, claiming:
  * YAML is a straight-forward markup language, offering an alternative to XML, borrowing ideas from C, HTML, Perl, and Python.
  * YAML texts are brief and readable.
  * YAML is very expressive and extensible.
  * YAML has a simple stream based interface.
  * YAML uses data structures native to your programming language.
  * YAML is easy to implement, perhaps too easy.
  * YAML has a solid information model, no exceptions no mess.
* Clark was made aware of Brian Ingerson and his work on [Data::Denter](https://metacpan.org/pod/Data::Denter) on `Sun, 13 May 2001 15:39:53 -0000`
  * Hey! That's me!!!
  * Brian was rebranded to Ingy in 2005 :)

Where are these "records"?
Patience...


### Primordial YAML

Here's one of Clark's earliest stabs at YAML:
```
$invoice           00034843
$date              12-JAN-2001
%buyer
    $given-name    Chris
    $family-name   Dumars
    %address
        $line1     458 Wittigen's Way
        $line2     Suite #292
        $city      Royal Oak
        $state     MI
        $postal    48046
@order
    %product
        $id        BL394D
        $desc      Grade A, Leather Hide Basketball
        $price     $450.00
        $quantity  4
    %product
        $id        BL4438H
        $desc      Super Hoop (tm)
        $price     $2,392.00
        $quantity  1
$comments
    Mr. Dumars is frequently gone in the morning
    so it is best advised to try things in late
    afternoon. \nIf Joe isn't around, try his house\
    keeper, Nancy Billsmer @ (734) 338-4338.
%delivery
    $method        UZS Express Overnight
    $price         $45.50
$tax               0%
$total             $4237.50
```

Sjoerd Visscher countered with something that may have inspired YAML's "flow" (think JSON) style:
```
%[
  invoice            [00034843]
  date               [12-JAN-2001]
  buyer %[
      given-name     [Chris]
      family-name    [Dumars]
      address %[
          line1      [458 Wittigen's Way]
          line2      [Suite #292]
          city       [Royal Oak]
          state      [MI]
          postal     [48046]
      ]
  ]
  product @[
      %[
          id         [BL394D]
          desc       [Grade A, Leather Hide Basketball]
          price      [$450.00]
          quantity   [4]
      ]
      %[
          id         [BL4438H]
          desc       [Super Hoop (tm)]
          price      [$2,392.00]
          quantity   [1]
      ]
  ]
  comments[
      Mr. Dumars is frequently gone in the morning
      so it is best advised to try things in late
      afternoon. \nIf Joe isn't around, try his house\
      keeper, Nancy Billsmer @ (734) 338-4338.
  ]
  delivery%[
      method         [UZS Express Overnight]
      price          [$45.50]
  ]
  tax                [$0.00]
  total              [$4237.50]
]
```

The next day, Oren Ben-Kiki offered:
```
invoice:            00034843
date:             12-JAN-2001
buyer:
    given name:   Chris
    family name:  Dumars
    address: %
        line1:    458 Wittigen's Way
        line2:    Suite #292
        city:     Royal Oak
        state:    MI
        postal:   48046
    : %
        id:       BL394D
        desc:     Grade A, Leather Hide Basketball
        price:    $450.00
        quantity: 4
    : %
        id:       BL4438H
        desc:     Super Hoop (tm)
        price:    $2,392.00
        quantity: 1
comments:
    Mr. Dumars is frequently gone in the morning
    so it is best advised to try things in late
    afternoon. \nIf Joe isn't around, try his house\
    keeper, Nancy Billsmer @ (734) 338-4338.
delivery:
    method:     UZS Express Overnight
    price:      $45.50
tax:            $0.00
total:          $4237.50
```

Spooky...

Now we're cooking with nitro!


## Back to XML

OK, cool, but what's any of this got to do with XML?

Back then Clark Evans, Oren Ben-Kiki and a host of others were trying to figure out how to make XML simpler.
This world-wide discussion happened on the [XML-DEV](http://www.xml.org/xml-dev/) mailing list, starting in 1997 and continuing until at least last Wednesday.
In November 1999 a faction of that list started talking about SML, a simpler more minimal XML.
They decided to create their own SML-DEV mailing list.
It was there that Clark and Oren eventually decided to break away from angle brackets altogether and... YAML was born.

At that time Ingy had landed a job in Open Source Heaven (aka ActiveState) and was sitting in a row of Perl programmers, across from a row of Python programmers.
He was working on the Perl core's plain text serialization language, Data::Dumper.
In the Spring of 2001, he must have caught some Python fever, because he made Data::Denter, an indentation based serialization language module for CPAN.

In May, he got an email from Clark which led to an hours long phone call.
He couldn't stop muttering "YAML YAML YAML" for months.
_Try it yourself. It just feels so good coming off the tongue!_


## Back to SML

Over the next 5 years or so, Oren, Clark and I(ngy) worked non-stop (on a mailing list of course) getting YAML off the ground.
They mentioned SML from time to time.

In 2017, I decided to look for the SML-DEV mailing list and to my surprise it still existed on yahoo.com!
I searched the list to find out how I was brought into the mess in the first place.
I found a single post from Jim Flanagan telling Clark about me, the same day that Clark reached out to me.
```
Date: Sun, 13 May 2001 15:39:53 -0000
Subject: Re: YAML Draft 0.1
In-Reply-To: <20010511155031.A30060@...>
From: jimfl@...

This looks very similar to the format of the Perl module Data::Denter
(by Brian Ingerson) for which there is already a fine parser available
(in perl, of course).

See:

http://search.cpan.org/doc/INGY/Data-Denter-0.12/Denter.pod
```

Next I searched for more info on Jim and it turns out we lived in the same city.
Practically the same neighborhood!
I emailed the unwitting catalyst of modern day YAML and invited him to lunch.
We had sushi.

This week I went back to the SML list to look for something and got hit with:
```
Announcement: End of Yahoo Groups We’re shutting down the Yahoo Groups website
on December 15, 2020 and members will no longer be able to send or receive
emails from Yahoo Groups. Yahoo Mail features will continue to function as
expected and there will be no changes to your Yahoo Mail account, emails,
photos or other inbox content. There will also be no changes to other Yahoo
properties or services. You can find more information about the Yahoo Groups
shutdown and alternative service options on this help page.
```

Boooooo!

Not only that, I could no longer see the SML-DEV content.

After a few tears, the internet graciously led me to archive.org where I found the entire SML-DEV list (every email!) downloadable as a [single file](https://archive.org/download/yahoo-groups-2016-06-18T17-13-11Z-9329be/sml-dev.sbxL0kc.warc.gz)!
Hmmm... `.warc.gz`.
I know gz but warc looked scary.

Nope.
It's WARC, the Web ARChive format!
Just an alternation of plain text header lines and JSON payloads.
Since JSON is a proper subset of YAML, I figured I could handle it.

The next morning I cobbled together a [shell command pipeline](https://github.com/yaml/sml-dev-archive/tree/master/fetch) that turned 5000+ emails into a nice readable plain text file that I've been scouring and devouring ever since.
I threw the whole schmear up onto a [GitHub repository](https://github.com/yaml/sml-dev-archive#readme) so you can [read it](https://raw.githubusercontent.com/yaml/sml-dev-archive/master/sml-dev.txt) too.


## Back to the Future

There is such a long and rich history of how YAML got here.
I could go on for days.
Perhaps I'll get back to some of that in a later post.

My focus is currently (as it's been since 2001) on the Future of YAML.
I want to tell you where YAML is _going_!!!

There's a lot of fantastic new activity in the YAML language, and some new dedicated people helping to move it forward.
We can't wait to share more of the YAML adventure as it unfolds...

Be safe, do good and carry on!

— Ingy döt Net
