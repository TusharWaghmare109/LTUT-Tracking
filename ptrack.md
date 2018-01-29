
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
    - tr_cid (track client id)
      - Eg.'18290'
    - tr_m (track message id)
      - Eg.'4'
    - tr_uid (track user id)
      - Eg.'1'
    - tr_aid (track user-agent id)
      - Eg.'2'
    - tr_ts (track transaction id)
      - Eg.'171121111040'
- **client=18290**
- **test=2**

### Open track and Broadcast example
- http://ltlocal.netcore.co.in/ptrack?g=0&m=5&eu=AQIAAwEEAlYCUw==&u=4e34e3346310080acfc1a2eb114d0296&client=18290&test=2
- In this,
  - g=0
  - m=5
  - eu=AQIAAwEEAlYCUw==
    - #### After decryption 'eu' gives 'u' means user id 
  - u=4e34e3346310080acfc1a2eb114d0296 
  - client=18290 
  - test=2

### Open track and Automation example
- http://ltlocal.netcore.co.in/ptrack?u=X&data=AAoCCgEZBksDT1McVQ4JUwUDAlIFUlEHSAY=&client=18290&test=2
- In this,
  - u=X
  - data=AAoCCgEZBksDT1McVQ4JUwUDAlIFUlEHSAY=
    - #### After decryption 'data' gives 'tr_cid, tr_mid, tr_uid, tr_aid, tr_ts'
  - client=18290
  - test=2

### Link track and Broadcast example
- http://ltlocal.netcore.co.in/ptrack?g=0&id=eU4AAwEEAlYCUB0BVAkIUgcCBh8=BR4CVkFEB1gEFlBbWVlHTlImVlVNWgpDAx5aDEpfXQ==&client=18290&test=2
- In this,
  - g=0
  - id=eU4AAwEEAlYCUB0BVAkIUgcCBh8=BR4CVkFEB1gEFlBbWVlHTlImVlVNWgpDAx5aDEpfXQ==
    - After decryption 'id' gives 'msgtype,fwdid,messageid,userid,email'
  - client=18290 
  - test=2

### Link track and Automation example
- http://ltlocal.netcore.co.in/ptrack?id=eU4AAwEEAlYCUB0BVAkIUgcCBx8=&data=BVpXDgQbUhtSFQMVAA8EBgFXCQEICVEBGgA=&client=18290&test=2
- In this,
  - id=eU4AAwEEAlYCUB0BVAkIUgcCBx8=
    - After decryption 'id' gives 'msgtype,fwdid,messageid,userid,email'
  - data=BVpXDgQbUhtSFQMVAA8EBgFXCQEICVEBGgA=
    - #### After decryption 'data' gives 'tr_cid, tr_mid, tr_uid, tr_aid, tr_ts'
  - client=18290 
  - test=2

## Location :- /opt/transmail/libs/EMM/mailauth.pm

## Subroutines of handle_ptrack
- check_clientid_in_track
- load_db_config
- read_md5sum_for_link_decode
- get_client_dbh
- decode_uniqueid
- get_click_url
- read_url_from_client_db
- check_for_mv_vm_links
- redirect_click_url
- log_data_in_redis
- check_for_usertrack
- get_trid_firstcol
- return_single_pixel_img
