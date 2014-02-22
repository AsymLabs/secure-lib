secure-lib
==========

The Bash library `secure-lib` can be used to help harden Bash scripts against
malicious use.  For most purposes this would not be needed but in the case a 
script is used on a public network or as a cgi file then it may be justified.
Of course if one is also truly paranoid it may be of interest too.  
  
Generally it is considered good security practice when using binary tools to
provide the full path to the binary when invoked.  To facilitate this action,
`secure-lib` provides the association `safe[]`.  For example grep may be
called with a full path by invoking `${safe[grep]}`.  This association can be
extended depending upon specific needs.  
  
`secure-lib` was inspired in part by the excellent [Bash Cookbook (Albing,
Vossen and Newham)](http://bashcookbook.com/).  

Motivation
==========

Bash can introduce security risks within public system.  Often breaches
are specific to the PATH variable and alias. Malicious software is easily 
accessed within a user area by modification of the PATH variable.  This library
attempts to isolate some of those risks - and provide additional safeguards.  

Dependencies
============

Bash 4+ and nothing else.  For earlier versions, there are workarounds for 
associations (key value maps) but we leave this as an exercise for others.   

Features
========

Basic security for most scripts, that can be tightened significantly where
required.  There is also a safe association that can be used to facilitate 
tighter security.  

Usage
=====

This is not a Bash executable.  Source it at the beginning of your executable
script with:  
  
    source '/your/path/to/secure-lib'  

That's it.  
  
Examples
========

You can invoke the safe association as follows:  
  
>[user@a52j lib]$ source secure-lib  
>[user@a52j lib]$  
>  
>[user@a52j lib]$ ${safe[grep]} 'secure' secure-lib.md  
>secure-lib  
>The Bash library `secure-lib` can be used to help harden Bash scripts against  
>`secure-lib` provides the association `safe[]`.  For example grep may be  
>`secure-lib` was inspired in part by the excellent *Bash Cookbook, Albing,  
>[user@a52j lib]$  

Terms
=====

We offer this to the community for free and you may use it as you wish.  
  
This source is Copyright (C) Applied Numerics Ltd Great Britain 2013-2014 under
the brand AsymLabs (TM) and is provided to the community under the MIT license.
Although we have not yet encountered any issues, there is no warranty of any
type given so you must use it at your own risk.  

Closure
=======

We hope that you find this Bash library to be of value.  Should you have any
comments or suggestions for improvement please let us know at
dv@angb.co.  
