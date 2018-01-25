
## Ptrack url syntax
- id	:-This case is click track if not having id then open track
- data	:-This case automation track if not having data then broadcast track
- client	:-To know clientid
- test	:-It has 3 cases,
  - 0 - Live user test
  - 1 - Manual test
  - 2 - Automaton test
- u	:-Unique id
- g	:-It has 2 cases,
  - 0 - Non Gmail user tracking
  - 1 - Gmail user tracking
- m	:-Message id
- eu	:-Encrypted user

#### For eg. *http://ltlocal.netcore.co.in/ptrack?id=eU4AAwEEAlYCUB0BVAkIUgcCBx8=&data=BVpXDgQbUhtSFQMVAA8EBgFXCQEICVEBGgA=&client=18290&test=2* 
  In this Example,
- **id=eU4AAwEEAlYCUB0BVAkIUgcCBx8=** 
  - after decryption id gives,
    - msgtype  
      - Eg.'H' 
    - fwdid
      - Eg. '00000002'
    - messageid
      - Eg. '00000005'
    - userid
      - Eg. '1'
    - email
      - Eg. 'gaurang.acharya@netcore.co.in'
- **data=BVpXDgQbUhtSFQMVAA8EBgFXCQEICVEBGgA=**
  - after decryption data gives,
    - tr_cid 
      - Eg.'18290'
    - tr_mid  
      - Eg.'4'
    - tr_uid  
      - Eg.'1'
    - tr_aid  
      - Eg.'2'
    - tr_ts   
      - Eg.'171121111040'
- **client=18290**
- **test=2**
 
## Location :- /opt/transmail/libs/EMM/mailauth.pm

## Subroutines of handle_ptrack
- check_clientid_in_track
