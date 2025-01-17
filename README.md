finddomain
======

This little python script is intended to find the shorter domain names
that still are unregistered.

## Requirements

  * whois (not python whois, the stand-alone whois)

## Usage

    finddomain [OPTIONS]

### Available options
  * -c --length LENGTH  
     The length of your desired domain name  
     Default: 4
  * -t --top-level-domain TLD  
    The TLD you want to search in.  
    If not specified it will try most of the top level domains that exists  
    at the time of writing.  
    You can specify multiple TLDs by separation them with a `,` (no spaces!)
  * -l --letters LETTERS  
    The letters you want your domain to contain.  
    Default: [a-zA-Z0-9]
  * -s --sleep SECONDS  
    Some whois servers may temporarily ban you when doing many queries in short notice.  
    The argument can be written as a fraction.  
    Default: 1
  * -b --beginning COMBINATION  
    The search is performed in alphabetical order. With this option you can  
    choose which combination to start with (this reduces the number of domains that  
    will be searchd)
  * -v --verbose  
    Verbose output.  
    Default: Set if single tld is being used.

### Example
    finddomain -c 3 -t se -l abc
    
or

    finddomain --length=3 --top-level-domain=se --letters=abc
    
Will output if # from print() is removed else will be saved in file domain_output.txt:  

    aaa.se is unavailable.  expires: 2014-12-31
    aab.se is unavailable.  expires: 2014-06-06
    aac.se is unavailable.  expires: 2014-11-21
    aba.se is unavailable.  expires: 2014-12-31
    abb.se is unavailable.  expires: 2014-06-10
    abc.se is unavailable.  expires: 2014-12-31
    aca.se is unavailable.  expires: 2015-02-10
    ...
    
### Exmaple to run in background
    finddomain -c 3 -t se -l abc &
    
or to run in background

    finddomain --length=3 --top-level-domain=se --letters=abc &

Output will be saved in file "domain_output.txt"

## Licensing

All code is licensed under the terms of the 3-clause BSD-License:

    Copyright (c) 2014, jocke-l
    All rights reserved.

    Redistribution and use in source and binary forms, with or without
    modification, are permitted provided that the following conditions are met:
        * Redistributions of source code must retain the above copyright
          notice, this list of conditions and the following disclaimer.
        * Redistributions in binary form must reproduce the above copyright
          notice, this list of conditions and the following disclaimer in the
          documentation and/or other materials provided with the distribution.
        * The names of the authors must not be used to endorse or promote
          products derived from this software without specific prior written
          permission.
      
    THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS AS IS AND
    ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
    WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
    DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDERS BE LIABLE FOR ANY
    DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR  CONSEQUENTIAL DAMAGES
    (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
    LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND
    ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
    (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
    SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
