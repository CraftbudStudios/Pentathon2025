Nmap Scan was performed carefully so as to not disturb any OT hardware -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe0EkMfrVkRTLj2v_-9Wxn19RdZsYirTk7xbciDHdE7uTUWhIfZL3ullOV_cjVLZ8c2Rt6B1ees-pYrOLCCbEaHPqrCtSOz-9HBSo-Z33dBQLWD6B9OH1RwzT_NiKfVOeUieudOvQ?key=OvGj73sy7evb3SYjw3i8KMhn)

|  |  |
| --- | --- |

Version scan was also performed -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfOPAUFLRpVaX7dkaWx3wDfrOS8lryaP5EGsLfDCRoycnq91X6qFIRmYA5kcyxvwE6VXSLP3hmJouABq_K1xfV5DIuuS0SapEmXdWZjIeQm_OhZl6NBEtpJFuycPQyj2cLwPw5olQ?key=OvGj73sy7evb3SYjw3i8KMhn)

At port 5000, a login page is seen -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfTe_Qp9RlR1RCLProj3mWj1yiN6RHkDUUF2x2s4TxV9hQABw2R0W8wPvlgsR1AwIC9Z60OsCmt0st3Irudh_eziseShf4TCiki0A7sB9Z_uO3hH4b7c8cBIVZB21_v2BdcmWA-Rw?key=OvGj73sy7evb3SYjw3i8KMhn)

At port 1881 we see -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfiG0u5Zbwx5XtQkf64hxBIzJV8fDdmRKUapKXs-HVJr7gX1qgrnVFVFBa2nEt_oGEKzQaLyWq9BIpF2a38Z3wUEqqFBZUJi_v5Pa_WjQSwoxrXqrtfFMrxtblX0ELAkXc1qc4QXw?key=OvGj73sy7evb3SYjw3i8KMhn)

/api endpoint discovered -

/api/settings-

{"version":1.1,"language":"en","uiPort":1881,"logDir":"\_logs","dbDir":"\_db","daqEnabled":true,"daqTokenizer":24,"workDir":"/app/\_appdata","appDir":"/usr/local/lib/node\_modules/@frangoteam/fuxa","packageDir":"/usr/local/lib/node\_modules/@frangoteam/fuxa/\_pkg","settingsFile":"/app/\_appdata/settings.js","environment":"prod","uploadFileDir":"/app/\_appdata/\_upload\_files","imagesFileDir":"/usr/local/lib/node\_modules/@frangoteam/fuxa/\_images","reportsDir":"/usr/local/lib/node\_modules/@frangoteam/fuxa/\_reports","userSettingsFile":"/app/\_appdata/mysettings.json","httpUploadFileStatic":"resources","httpStatic":"/usr/local/lib/node\_modules/@frangoteam/fuxa/dist","uiHost":"0.0.0.0","serverPort":1881}

From <[http://192.168.230.43:1881/api/settings](http://192.168.230.43:1881/api/settings)\>

Administrator password exposed in responses from server -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeEqe7fJ6h61ZlJtuJFYLiqx6K6pmMcD4bJGCNjHIzZkZT_so0UvDZ44JAmEiunyNyH6EBIZ0fWAcpfFd3hphna4pbQu0-mmgHKhsouzFaN6r-1FJnq_NgHWrCxXkhIkxuCVuiy_w?key=OvGj73sy7evb3SYjw3i8KMhn)

Normal users can control everything on the site -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcJStkL5HJfUtTLR_bP_oWIGlXVYWrQpCniyBNoN1cD74fUOQh_hvFGPV7HTUONy8h1ESZcDKARIHSLYRyrHp9qEZOfUfh0zICpqDNUvJcZrmdyxBgvRWVZnLhpBDjS75SYvV43XQ?key=OvGj73sy7evb3SYjw3i8KMhn)

A test menu has still been left intact -

From this page, going to Settings -> Connections reveals -

Going to Settings --> Users also exposes -

Server plugins reveal several core processes running -

In the background, fuzzing got some interesting details too -

Visiting the /key endpoint we get -

Sounds like SSRF, tried known payloads, will come back to this if time permits.

In FTP, anonymous login is allowed -

After traversing we got the credentials for the valve system -

Username: ops

Password:  ops

Logging in, we see -
