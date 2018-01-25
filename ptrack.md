
## Ptrack url syntax
- id	:-This case is click track if not having id then open track
- data	:-This case automation track if not having data then broadcast track
- client	:-To know clientid
- test	:-It has 3 cases,
  - 0 - Live user test
  - 1 - Automaton test
  - 2 - Manual test
- u	:-Unique id
- g	:-It has 2 cases,
  - 0 - Gmail link tracking
  - 1 - Non Gmail link tracking
- m	:-Message id
- eu	:-Encrypted user

#### For eg. *http://ltlocal.netcore.co.in/ptrack?id=eU4AAwEEAlYCUB0BVAkIUgcCBx8=&data=BVpXDgQbUhtSFQMVAA8EBgFXCQEICVEBGgA=&client=18290&test=2* 
  In this Example,
- **id=eU4AAwEEAlYCUB0BVAkIUgcCBx8=** 
  - after decryption id gives,
    - msgtype
    - fwdid
    - messageid
    - userid
    - email
- **data=BVpXDgQbUhtSFQMVAA8EBgFXCQEICVEBGgA=**
  - after decryption id gives,
    - tr_cid 
    - tr_mid
    - tr_uid
    - tr_aid
    - tr_ts
- **client=18290**
- **test=2**
 
## Location :- /opt/transmail/libs/EMM/mailauth.pm
## Subroutines of handle_ptrack
- check_clientid_in_track
