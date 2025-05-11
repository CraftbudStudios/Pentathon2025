TLDR

Flags found: 3

Flag locations: opcua nodes, fuxa in challenge.py file, modbus server behind port 6060 running proxy

 

Nmap Scan was performed carefully so as to not disturb any OT hardware -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd4BVxAKJgpKIjbhTQQ_cDX9L4s8umtwO1tZO_PgfHdm9-9lrhD3OQGs2CTNKI-6hb4F9WmLRgQYg7NKIE5g5FxBzKVlmRKdW9clniduKOAeiRTaNGqBlF4noATPiuFVA4p3WEj?key=d0Wt3_u_2eD-zkNSivan0Q)

|   |   |
| - | - |
|   |   |

 

Version scan was also performed -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe-_R-Zcd7zJLXDRgPHIKfQfER_beoZ1nMyClK3qQ1n5aUReXo1EIm3YouvOLUKYgJFnVL-e7dtIXeWmYmEpur6molV-R7-foBIwQM3V5brH22RJM4wMp3qaTGpFNrNQJR8OWfk?key=d0Wt3_u_2eD-zkNSivan0Q)

 

 

At port 5000, a login page is seen -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcDmd1TFUXJjrbG345wQn88dZzgfa5A2zx-9HcRgHJ4ATOgg8mJlP5pZIw6ypm5UvVxIPnKNfJrM-1_TjXKrT3ArFZILFjbealfmnc5s7XTbp1OT3YfK5DyutTHSJA3vSUIWVT3oQ?key=d0Wt3_u_2eD-zkNSivan0Q)

 

At port 1881 we see -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXccvsU3w7SidDfVlRP3vpvraLN4vq1zxN9KGrUx5nT9ayQ6rtGLFuQP6uEWID8sT_UOGmPOqHYxoFnkS_yxzXnXnUEfr4Gk-ePaBlHoRep89oh3SXqlqMFO8Z2rq-C8RVqvJOqG?key=d0Wt3_u_2eD-zkNSivan0Q)

 

 

/api endpoint discovered -

 

/api/settings-

{"version":1.1,"language":"en","uiPort":1881,"logDir":"\_logs","dbDir":"\_db","daqEnabled":true,"daqTokenizer":24,"workDir":"/app/\_appdata","appDir":"/usr/local/lib/node\_modules/@frangoteam/fuxa","packageDir":"/usr/local/lib/node\_modules/@frangoteam/fuxa/\_pkg","settingsFile":"/app/\_appdata/settings.js","environment":"prod","uploadFileDir":"/app/\_appdata/\_upload\_files","imagesFileDir":"/usr/local/lib/node\_modules/@frangoteam/fuxa/\_images","reportsDir":"/usr/local/lib/node\_modules/@frangoteam/fuxa/\_reports","userSettingsFile":"/app/\_appdata/mysettings.json","httpUploadFileStatic":"resources","httpStatic":"/usr/local/lib/node\_modules/@frangoteam/fuxa/dist","uiHost":"0.0.0.0","serverPort":1881}

 


Normal users can control everything on the site -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdXsEePuRkRoo7uNRSlmR-stZPDXJ8Ej-L5SH-hfksRpq5ADugi_nIlkWal2GK8m7b6H5KNh9LET0UgkOXptPmCBkssYnLuUe44EkS8QvmMa9sit2RRMepvX9VZvXEBxiNgEjvnHA?key=d0Wt3_u_2eD-zkNSivan0Q)

 

 

A test menu has still been left intact -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdbzb7TCCvvOmt5dLPFsYpHoTN0xE325osdFIljpzyvH9f3aXaNKu2kGSUZl8xz1DOFeKPdxypbk2A-WQ5Sfruz8BCXrxiQNGOhUwW6DqazvgU5PeUe8j_NpgRsh7tA0nMmwyNNpw?key=d0Wt3_u_2eD-zkNSivan0Q)

 

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdqCubVxEPr_yh08uwgtFI7Vyul2Wdj7e97TRH0y33mwlRgOuq9bTozdN7p330V_lfZ0UZaJlSFdKNV6sz8usxGB07te9zpvc_0DO_peY-6ZY6UfreV3TYjtaBu4u0kTv1O2QQc?key=d0Wt3_u_2eD-zkNSivan0Q)

 

From this page, going to Settings -> Connections reveals -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfyf_xlgxND429m9GQtGg9JSjkcalYJvrdyPEH0ShDTE0PhWJeQ5xveQHowiO-VIgrVmP2IysXeja-6gQb7iTunqGT7dRqgZXIonUdO56AP1YiebdzBsgK4JCXiuBWNT7ODTwnB?key=d0Wt3_u_2eD-zkNSivan0Q)

 

Going to Settings --> Users also exposes -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcAKK8dU9XIgLMOkhSa3OT5rHbGZ9uF3-iHy1vt3-mlCB281e8fwvBOgu3RicXO_lCPQLkgSe7jbGqxb-nz8XAUILuk4sMNewoiw6-lf6N16B_iYZYpDgC7F0PtgxjlVo4XGQqWRQ?key=d0Wt3_u_2eD-zkNSivan0Q)

 

 

Server plugins reveal several core processes running -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdwMP70JPzUVUc9DuY3x1eYLZfNCEYMyvzqQThF-NbaQzw71Dz3-Et0eZtZK2phqodL_Mlkm-e0T0pDuIOB0Rf_BzjC-IO7jB_-JGOCj-YjrTcit0Bu4dMOc8hx_SU1pWFusYTc?key=d0Wt3_u_2eD-zkNSivan0Q)

 

 

In the background, fuzzing got some interesting details too -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeznOWOnEo9b6wiK5hMDqldzkTotW3fJyL3xg39rrDhXuzqQ_Y2_MODeXm9HMBgqIji7J_BFmWr58KRwNyLDv52kwhabUtDCA14JLdIrkQCZ76XtUunNSAI9Oh8hL5BpS83bLheEw?key=d0Wt3_u_2eD-zkNSivan0Q)

 

Visiting the /key endpoint we get -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfUrjtfi-INL5Enou6_VAGQGguNzZvuXOOINje0aDWrcik5gDO9u1ezfICDqme03ttq2Svp_kn4mpaj_y5t-PsODYX0MKIuUtNWoV92xJgWNUS55kVcSy8s74frh0BQduh3dZ1r?key=d0Wt3_u_2eD-zkNSivan0Q)

 

 

Sounds like SSRF, tried known payloads, will come back to this if time permits.

 

 

 

In FTP, anonymous login is allowed -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdvDH5Dj927CKjkeEj6SpRjkxrzQ_vbt4e5tGeqA9dMM6-hwdUlbxvQh7_QmSqmQb3VT0gc9i42dOQv2msO2LLbIaWtZRkw5eEch3cPJGx5nFku-dnjXUPtYslVuRRsoGvkPaXxIA?key=d0Wt3_u_2eD-zkNSivan0Q)

 

 

After traversing we got the credentials for the valve system -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXefZZDjAs0cX4TcVtao4BclApIRWNv8Kau1PQIXvVUZJI1Iv6GkP89n603DcBDUKhyM5WestMEhmDfMGsH3I2UUMcARAizIBaF91sZNgvSJKXnBZ4W6a2zyn6RQMHR40E902ysQTQ?key=d0Wt3_u_2eD-zkNSivan0Q)

 

Username: ops

Password:  ops

 

Logging in, we see -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdC1DnznHhO-zfTMFeqQqyZtykcwr3UCKwqKBLPbLRXkP4SczrV74sKUNsmChe0dcKkORgv3XT8c9s01grDVmQ5oBajKzJHvfrRs4cpe_fMw74MEXItx7OF4ZNIWGFCy_kOzdB1Dw?key=d0Wt3_u_2eD-zkNSivan0Q)

 

 
## Fuxa CVE
We also notice that the server on port 1881 is running on fuxa-

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeYYHOs1yrHyrMLmfhOSa0RPKRYAv0RzZ_3WOFP6-wHCIPuUDwEIiAWdqehcRZhOVn2KVSo7XGppSoINHkNFN_u5gG0Zpqpvos45hAiaLqkU1qEaOllbSX8fTNBGasCKF3PubqoqQ?key=d0Wt3_u_2eD-zkNSivan0Q)

 

A quick search reveals that there is an rce for this which may work-

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcTSnY0F2d_b_4jJ_ZgoUgNmlCT21jhxWcQFWGhOukixXIqLzBdDyo8feHkcK0SgT9q3VKsL9LwrltCgBQ8T2KMeph445VypUdjyn5dJ1dvbLMcIiEibzoY1jlhs5Y4bLAx-TDXug?key=d0Wt3_u_2eD-zkNSivan0Q)

 

Tried to run that script multiple times on the target with no result, realized it is likely because the target OT system is running a docker container.

In the meantime, gobuster which was being run on low requests per second so as to not take down the envrionment found /api/settings endpoint -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdBd7Y2lClAhuvHtD3PY1qcCXfqAz2cqNLf8SLsCuj_kNJMCBjAHQsYFrGKDvTar9Gg7vMfQjSHtIwwauUGrDunkAH_579EFzHQNm-YVRuPI2tFPAm5_XVj9eB3dg5sHxbePIJ-oQ?key=d0Wt3_u_2eD-zkNSivan0Q)

This confirms the version to be 1.1 which is vulnerable to the CVE and reveals the app directory, and many other sensitive file locations.

With this knowledge, we are able to tweak the CVE script and get stored command injection as the root user, which is CRITICAL.

We first run the script with this code snippet -

"code": "require('child\_process').exec('whoami > /usr/local/lib/node\_modules/@frangoteam/fuxa/dist/whoami.txt')"

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdAlnXYGDtJh-9lIAslZ_n7cpMyTUQnUZuKVFkjd0sK43AmMSrkaTnvQe1O6qm0mAL2cyG8BQVFIh7p_phkmZxUHX3T3D6LYZI1rr5h6IqGJiy1ZA8hz7glKBo1qi2WdL7Ab8xUZA?key=d0Wt3_u_2eD-zkNSivan0Q)

 

With id -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe73dt1ymSjwOxsnD1jv9SedTApS3WMXG8LoblEzwJnnK3sufAEj2zAVMHCUzqgm96cmEXpGdO-_OwQBHz8c7HGn-VdDRV7_t3dmt3uQmEvfNGCGfZL6wMaU9POs39AXV8UxOhh?key=d0Wt3_u_2eD-zkNSivan0Q)

 

Doing ls -la reveals -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXccnBsLk6aAkCLLI9rIFmAzSPD6d9xIaLfKIJhSuDhxH1HnVpqMTE9CRe2HYsTfqVCTNBLRyfTK5nix4Kr_nxCgW4HMb4ctfIgj1D9GdRPddPbrJKCubOnji19tR1uQnKiukYze4A?key=d0Wt3_u_2eD-zkNSivan0Q)

 

challenge.py seems interesting, so let's take a look at it...

 

And done! We got a flag -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXef3zbJFhf3c2-hr4MLbO7WiJZXKDLo5lBJmp8bpH2dpklwhlEeIWQe6u6pB0fJDt78WBj0xb9Y7tZr8NOHmYRV8EmQoYDcu-RhoN3qmcD4brGQ_PZ918tIuQGF-H-LoptmVonCbg?key=d0Wt3_u_2eD-zkNSivan0Q)

 

FLAG{5y573m\_15\_c0mpr0m153d}

 

 

Alongside sensitive operator and administrator credentials.

The flag would have also been revealed as a security token if activate\_emergency() had been called -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfV7tnsrdVpWTW9pwebAZbzs01RTybyQnhYYCvAF6iObv9VhVAfdapRoaAwgrESaLXZwo2Ubu-g1jPO_R17QSVzQL8tF80Uc6bylfJdn9-fmb3UsnUwPJ5q0iruUk97bVuUAgym6w?key=d0Wt3_u_2eD-zkNSivan0Q)

 

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdfFz7h4GWlL1P6oz6coltgNVCJUppCiLZhck6ksUR5D9vkLQNZTD_BcHK4mtBiaoRKbj6rm5Iw4jLoRNcLqMvBei-bfVix6TYiCbDLNHS_wx8RHZiRQ4d3LBJwqmFoHn2grkrI?key=d0Wt3_u_2eD-zkNSivan0Q)

 

 

 

 

 

 

 

 

 
## OPCUA Nodes
We had also seen opcua running on port 4840 in our nmap scan-

 

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcLmp5kc91IOO_LwOp00JKWAHMz2JfP8B8_WZL_DD0et769a9sirBwYZKsPCqHGlAkB4vDQp4Yho3jLG3Au6bCTdPzEcXo0NoeJFKyL3iO3KqgM161Mr831SxNzop8LYypkDJ8U?key=d0Wt3_u_2eD-zkNSivan0Q)

 

The server running on port 1881 confirms this if you dig enough -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfrRNfqa5Y_V2357QhL49Qa3HSsoZo5Fm3BPdDY5ryfCUYK8TlEkMCIrqzqNL6RytL7WWcyhzmB9RS4VF9wzM6eI9E1r2DhKfJ5mL0OQ8II-IR-yUl1k27vQAEMBAFIImX1GsHXJg?key=d0Wt3_u_2eD-zkNSivan0Q)

 

Ran a python script to see how many nodes there are -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcP1EGYKYJOi_Yp58ypoPpOqA_jFzSOAtka8AA_zFtrZ2PaawHxz0Rd4gmuMX_XXftmJsX48OJRVlzKDPk8JqijQSD0GK5QB240AA3e8WVVNc1bi-dl7Nayd8pQTJIOpcjiyl_i?key=d0Wt3_u_2eD-zkNSivan0Q)

 

There were a lot of them...

After a lot of digging and using different tools, opcua-client from github which is open source worked and we got the flag from the node -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcOTM4rYhJQ8BxRsKG3lT7rkiVI-JwMU9oMM8x_vTMizcd0xki7Lm46uNy3bWdH4Vr0dpxcjK9yST1ml4kLEFVPIQInSnlBUy9vjsb5D-GKrw63IGKldrjG8LLpsfseH5k9Vb8MkQ?key=d0Wt3_u_2eD-zkNSivan0Q)

 

flag{m15c0nf19ur3d\_5tuff\_1n\_cr171c4l\_1nfr45tructur3}

 

Note: This was possible only because we saw OPCUA running without security and encryption -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdwqkyJfdRcFDfpcdzkLj7qqFAm79Qvb4t4RpLcdmK5-i8D959sLTzBw4eHuUYv9nMAMY-usabQ-mskSrSHDcd_EhG95VweVjb8E61ItNVCbaQaSsO8cPLHbBErTvPBepV2oRhq?key=d0Wt3_u_2eD-zkNSivan0Q)

 

However even if it did have a password we could have modified it -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfVB8GPBEEbZhCUYjnZVhWKwk4maewVSebiIM7uDzTY-mAWtHnDLOf_muWt8GPxwC90zUtt5aMFe9RGbAWyn_z0dRO5_PY4JUymQiBVhLMPwXi6QsWI7w2f6tNXIkUDiCT56hG5Kg?key=d0Wt3_u_2eD-zkNSivan0Q)

 

Stating this since the locked hint suggested that we had to get admin access for section 3 which contained the flag -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeLwbDao-tdkzxYPgkvv2Vy-kLysFvbyq3nRNzYdDlA5frz9aUZ3dYyd1bM33UdvBt1GBM1FVyy6EG0X0iC-q8sKfSVTu0Bkpf59sjYZ9sPqAdvtX72pTOhVu1yB_NXZ22lQZeU?key=d0Wt3_u_2eD-zkNSivan0Q)

 

 
## Modbus behind port 6060
We see that anonymous ftp login is allowed and some files and directories are accessible-

 

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe2cFv07HVyIYe-AxPi1wsPasrQNgJj1N_ZRQzUudQXinA3HJDJ0e3KyMvzifhfO2ufXyUFHX4ta1MqgTycru14i8fNIpGoqQDHyyyZ-B_fO547gWidqzbgc5rtgY7XBoFqDu77?key=d0Wt3_u_2eD-zkNSivan0Q)

In the public directory, we see a readme.md file.

 

In the secret directory we see a proxy binary file and a vessel.jpg -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfy0mprakMEmRwwMNVM-gY2OjKPMBJfokqFzdvQPPvkCik0UEB1NI86rHjgETNHx7OtDbzWaLBbFUya9sQjs4OyUi8CiRFu0TgAWCklZXl8IOwPCrXFUR9Jercxic7JS4waBl7E?key=d0Wt3_u_2eD-zkNSivan0Q)

 

The vessel.jpg file when run in steghide to extract any data with no password, reveals an admin.txt file likely containing a password -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdoVbQJ0RrPKwRcSQXNErU9_P3-qrH34DvxSOsjyAMJbwEXYfTZRgS2c5mzZxGG2S3yEgYmBTUGPHfnWn1N-kkkjrSc0x_DwTLlZAsx1y_XzyDmOBB-qx8uL4hoc9JG3QnkiIffGQ?key=d0Wt3_u_2eD-zkNSivan0Q)

 

Reversing the proxy, we are able to find that port 6060 is running it and behind the proxy lies the modbus server. Rodbus client is used to read values from it and the final flag is -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfeKkCHDpFMoDigS0O41QF9PRPAAz0Vht9UOTHVUvI7fQk2u_Os_-HMWaA8SvHjWpPhzUVwcLtSB6U5G7Cz4xN5mBM45WCrNjo9YR6ZwkSHvmbmhm33GmRN5Xs95lk4S5xZiET_?key=d0Wt3_u_2eD-zkNSivan0Q)

 

flag{m0dbu5\_is\_s1mpl3}
