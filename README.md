COBOL on Wheelchair
===================

Micro web-framework for COBOL (in statu nascendi)

OK, [COBOL-ON-COGS](http://www.coboloncogs.org/HOME.HTM) was funny, but why not try that for real? ;)

Things you'll need to run _COBOL on Wheelchair_:

* [GNU Cobol](http://sourceforge.net/projects/open-cobol/) (```sudo apt-get install open-cobol```)
* Ability to run cgi-bin on Apache server


TL;DL READING ISN'T DEVOPS
--------------------------

```ruby
bundle install
ulimit -n 1024; VAGRANT_I_KNOW_WHAT_IM_DOING_PLEASE_BE_QUIET=true bundle exec vagrant up
```

Installation
-------------

```
git clone https://github.com/azac/cobol-on-wheelchair/
cd cobol-on-wheelchair
./downhill.sh
```

Tutorial
--------

http://azac.pl/cobol-on-wheelchair/
