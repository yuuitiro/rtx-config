# Config get set utility for YAMAHA RTX Router 

This utility have 3 functions.

1. Get configuration from YAMAHA RTX router (Use tftp). Single host and multiple host.
2. Configuration diff between local file and YAMAHA RTX router running configuration.
3. Save configuration from file to YAMAHA RTX router.

This Utility Change line feed code, Cut comment (but save revision and model name).
You can use git after get configuration.

Need support tftp (router), curl, bash (running host).

## Usage: rtx-config -H hostname -p password -f target_file -v [verbose] -d -s -o directory

```
 common)
   -v verbose

 get)
   Target Single host.
   -H  [require] Target host name or IP address. 
   -p  [require] administrator password (not login passowrd)

   * save to stdout. 

   Target Mulitple host.
   -f  [require] Sepalate by Conma file. 
         Hostname,Administrator Password
   -o  [optional] output directory
   
   * save to file (Hostname)

 diff)
   Unified diff between file and target router.

   -d  [require] Use diff
   -H  [require] Target host name or IP address. 
   -p  [require] administrator password (not login passowrd)
   -f  [require] Target file

 save)
   Save configuration from file. 
   ** WARRNING **

   - file doesn't  validation 
   - If Change IP address, Can't access router after setting.
   - always clear configuration

   -s  [require] Use Save from file
   -H  [require] Target host name or IP address. 
   -p  [require] administrator password (not login passowrd)
   -f  [require] Target file

Reports bug to <yuuitiro@vcnet.toyama.toyama.jp> 
Require curl and bash
```

## example target file 

IP Address, Administrator Password

No use space, No use "

```
192.168.1.253,admin
```
