Nmap Scan was performed carefully so as to not disturb any OT hardware -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdx4zCjwUpnvmI-hp5l50qfpcYTPLKP8H8HYkjPRPntLI5CpaQqTOvEe65Vqj_XdafPk_aq7QXC7cVQIPGOET8KMcQAQA0TJCO-r5nNJX7pq_NZEnyyAne2_bdJJ3akzeONJd-7wA?key=OvGj73sy7evb3SYjw3i8KMhn)

|   |   |
| - | - |
|   |   |

 

Version scan was also performed -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdKleoee4h4_2aQNA001avmb5NhMbzwWX5y2KsXmrGOmzoQk1NvN9NXRLmHznsmSczCgmkGmn4ZOARyzNWXQ0PZe5cirZqPZ95NyY7bdKkNnvHRg-hJLEtcVNjRRH5da2vnfXBtug?key=OvGj73sy7evb3SYjw3i8KMhn)

 

 

At port 5000, a login page is seen -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcoNf5bV2WdTn21gVQQ-P2zlVdMRE2eGXlfriX4G4Fs3b_-ViTwW7lGEFxewHZwrxTbjQVmzrfKtq7eRJjHczeATWNXL8FUn4_BIdRkB-_ni7ot33_Pyaa1LHEub18eZihhc4xEZw?key=OvGj73sy7evb3SYjw3i8KMhn)

 

At port 1881 we see -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcZ14I0he9COGuHQIr90VdDQ9OTD_XTghi_Ec8zgVq72NYIiXMt1M0iNSUEvyse0XH1x5G9kQgW3b8HwMXfJ244QmHkX_sjt3RfA3trxGLwCRzLMjUMHmqqJ6mp2Uce9M0rW2ollQ?key=OvGj73sy7evb3SYjw3i8KMhn)

 

 

/api endpoint discovered -

 

/api/settings-

{"version":1.1,"language":"en","uiPort":1881,"logDir":"\_logs","dbDir":"\_db","daqEnabled":true,"daqTokenizer":24,"workDir":"/app/\_appdata","appDir":"/usr/local/lib/node\_modules/@frangoteam/fuxa","packageDir":"/usr/local/lib/node\_modules/@frangoteam/fuxa/\_pkg","settingsFile":"/app/\_appdata/settings.js","environment":"prod","uploadFileDir":"/app/\_appdata/\_upload\_files","imagesFileDir":"/usr/local/lib/node\_modules/@frangoteam/fuxa/\_images","reportsDir":"/usr/local/lib/node\_modules/@frangoteam/fuxa/\_reports","userSettingsFile":"/app/\_appdata/mysettings.json","httpUploadFileStatic":"resources","httpStatic":"/usr/local/lib/node\_modules/@frangoteam/fuxa/dist","uiHost":"0.0.0.0","serverPort":1881}

 

From <<http://192.168.230.43:1881/api/settings>>

 

 

Administrator password exposed in responses from server -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcfwrNsPcYhgIhywCJE5t7VKiE0YnXcN7BkjDkqkPTyzSy1AbZxsoEpePKDQQTX6UP-jf1Ry9NwWUZ8y5SoCvVYfSr8nNqyG53QKGp46r_zOBTh4pSWJIQndLA2cCt2096ETW1YGQ?key=OvGj73sy7evb3SYjw3i8KMhn)

 

 

Normal users can control everything on the site -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdnsPcRP0Gzr92LFZlZm2eLaNS9PkFbyHgln-QXQkoaGibDxwazJZuVS1BCq9iGs3M-7TSf5YhZ-NVPB9IboKkEBKhm_r7zk475lf6yaU5i1Ep5QMqhNQQx8zh_A3zk5S1iJdDQ_A?key=OvGj73sy7evb3SYjw3i8KMhn)

 

 

A test menu has still been left intact -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdfP34hLt7IAIiwNr1a4alYayqOGcnSCrEm20JykPNXoxqG7EMQPeivfLclcIGlu0A38pSvTNvpCMMCQJw2_tlU6uNfWtWU7s6L5sHoPERPOHMNbf1aF_gN160Pa3afmXeBE2oD2A?key=OvGj73sy7evb3SYjw3i8KMhn)

 

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfchHGfnsehWT1-CbJXR1n8cyDfNfGj0vHgXQ_5MvGkfZRW_1lAWgNlG_VU7iO45M2oowIO_Ookp0yrcDR07590WhpgtvX6GDVoINWuj9SHe2hX4awKaxFlo7x-WkE796F0lHhr-A?key=OvGj73sy7evb3SYjw3i8KMhn)

 

From this page, going to Settings -> Connections reveals -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXct18kZXkuNz-H2iSkGWSLA3JdT4CPv1-nBZm_08iyCyd3Ec33ll5eWSNYIzg2N7wvsS9B81A0Cc2h6ERBIK6qzptKbUUMfdCBxVlz-L56406OkoZr9vM1lUpgqmk4Qhk_xMGEd?key=OvGj73sy7evb3SYjw3i8KMhn)

 

Going to Settings --> Users also exposes -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcjc9jyYCg6CjhSy2qv1IHjmizYNKjbhmdBUUu1bZQf2GQchcbd3xUi-8tuBxv0Z35ocT3zlMKUUVIURSPt5vAmUvxiWM_v_jIVtZqb50R22ITOE3AE4a62s5H3vkvS6MrEIFcK?key=OvGj73sy7evb3SYjw3i8KMhn)

 

 

Server plugins reveal several core processes running -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXehFzJpa2UrmH3CsDKi76ZqPrfUjmHYzFaOJNBmXZFrGHWXgVuteiWNhhFNawE-UrOoaqPQBezc_TEqBMZRMmRSi6ni5sXmI34WGmVRZ4pSVeok0fHshhRfFKjmnnY7rA0_kmkv_g?key=OvGj73sy7evb3SYjw3i8KMhn)

 

 

In the background, fuzzing got some interesting details too -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcugD97RqVWAvJlSVagmejR33qFdaTs1KNMzdKQV9CuzcbFF4utOiH-J99AmcGQMqib4PRkbQU6l3HPxwSnGIK0YEwl5vxrofmwksHATePsq9ziOflo4V94t7IfbaTIHofe8Wb8hg?key=OvGj73sy7evb3SYjw3i8KMhn)

 

Visiting the /key endpoint we get -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcjtH56Dt7fgvJJ1cCh6c3cAgIla-oDombOqUze4FvkN1xoZmeB_gsZzAQ-iy7CyLPzjnJ3Ya2pryfEo4Zh4NhGZp2f-9JVAZma6ArQ-eJKrtLmrgbJhiK50eAt8v6CSeEsxDht8w?key=OvGj73sy7evb3SYjw3i8KMhn)

 

 

Sounds like SSRF, tried known payloads, will come back to this if time permits.

 

 

 

In FTP, anonymous login is allowed -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfNxwZVsLhS2A1YjMO17D6KaE0bE-SRZ54aVXxjRVdAyPLqaxjlqQhMFvHKyiv_API5KvbljMtXiDtGUYgyBUpDg-BZzHOnYpJ1bfk-3DedbFgR4F851ZTZHYE2F79qdYU5Rx4c-A?key=OvGj73sy7evb3SYjw3i8KMhn)

 

 

After traversing we got the credentials for the valve system -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcx8KyLX3Xm2ATYUmm6l_kMg-MX5eYm3TNMwPZtsj-3fZwMcnmXdcyf9AAm6PihkSoCqRsm7pzRFwi--3N4tUXW3n9kcaACugurWcggsGBRe9HXEo2cJ3zIAmV01GR6Tq1IMInoZA?key=OvGj73sy7evb3SYjw3i8KMhn)

 

Username: ops

Password:  ops

 

Logging in, we see -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe9IUDTwqmVRhmxYCF1Q-UPm2mGr06gN7GQ0kXYfxoiYRHeLd2is5yLZJqkyMdA6aM4ofAejFPRYayxPQaeDymZ8FF113qBsjh5Panq-1OHrzFJCZeZFcACKSieF3IxR7tSsRbNwA?key=OvGj73sy7evb3SYjw3i8KMhn)

 

 
