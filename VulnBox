NCIIPC-AICTE

Pentathon 2025

  

Vulnerability Assessment and Penetration Test Report

  

May 03, 2025

Name: Jay Shah

jayshah-551-SLI13

  
  

Found IP Address of the machine via netdiscover

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXflnSHmqLbmX5XgfREFWne_oT8SYiaequkgoO8Uh3-lIUWaXw66oyYpLq_KrcrlA8uiXt-vPcHD_ORSsNyaRN7D9Gh5P4rWRJ4tIcw6kFmKTnQX1zrBahdWdmkcyNrIjOuU3B_m?key=RUI-tNB8eJsAK66TPJ_TuGwv)

 Image shows before running target VM vs after running it.

Ran an nmap scan -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXciYCKPH3HcXCt-WJj68kQAnS4i5PZwWutlF1NjrAnZ2IrRA_GO4gLccpfug3c8Hsg924dec5EPav1l6Odc6L1x6ncOKHFiitdi2_DzXWANwCyA3nvduPUgm1i8mu4s2nsNpSK3vw?key=RUI-tNB8eJsAK66TPJ_TuGwv)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeQNsFYLUmED7hpok3vWYGSY-KUX_y3-1_GUFrsHEI4BsHzb1bqtNap-SjLq7JZiVIqcgMFzmrFkOTHHOBLeG59nsz6PDuqOumQxQgcOIyXg3fW8Ob7FDQh2Rkeb_CkYaQxN7iQAw?key=RUI-tNB8eJsAK66TPJ_TuGwv)

Found port 80 hosting a web server.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc99iJ4258JaYasjOUzvRNcg3jnb-5-Wj_DrZR2UvIRL7CS2WAX_To6P8bjrvHz2_bw9IBqLHxKLwiNl7vfPesS736RyLU4HRvOdL5qpLNaaQzo32U-MyHIfT3PZASI1ht-rn9C?key=RUI-tNB8eJsAK66TPJ_TuGwv)

Running whatweb on it reveals it is running Apache  2.4.50

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdzXmCZpj9gWzZFbQR_YFWSO5s3anfBdJGNhhAiGWKSwlFukr9JkLZb1doea5jx9dHzqoWTwEuL857TwDJ19e1PGRQ5vXOi6qcXNghwff7cNHFSo_HE4-vdpKHHquJHyxJe8KEvPA?key=RUI-tNB8eJsAK66TPJ_TuGwv)

A google search reveals the vulnerability present in it -

Using the CVE we now have command injection-

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeOh0dk2wRorSKrepGDe1iea4LA1dFsKKOfMQTgTGwuOf389E3HuNPLElBBZwqurhYcWYFA-d2JByoDrlqdUVBqCF8EE5-pchOIXRtH73NBuAfPi0dYTfLafHeUR8NajkV-MCb_0A?key=RUI-tNB8eJsAK66TPJ_TuGwv)

  

And if we dig a bit more we find reverse shell is also possible. 

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfQXfpfIxbViNjmwTedzsjUPuim_clZqbSGsWETqNtshyLEp7xRvcjnHRDV8bryCNdMu2AHb7wlqWGGwHN235HPcrDHHaJVqOYEJr4pI-9Ojeah9bx2rE2Q83S86QpVagOWt5DRxw?key=RUI-tNB8eJsAK66TPJ_TuGwv)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXegqevqLv69Uhu5-lsx_JqGE2iZYWg7SiVUl2lun82JrADgaj0GxSuxQkU5a6q1AL7ekcsx4D34Dt6dHPRUrgQCbd2A8GXCS7GIJqEq80jY0dA0fla1sODtJLkSEGG558NubyZ9lw?key=RUI-tNB8eJsAK66TPJ_TuGwv)

 Webshell is now popped,

And we get the user flag-

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc40P-fHWdrBda34WQojskEZktrAPN9xBR59R_JydLq_6UG04Sbt3ZvZejBMRW8GkOMoxn26tSbQv7_qOu2zJ1dWWg70Ttk2JKxTtbnBmKxwecn5tVhWPt3MnJiMwZ7G74Ko0Xi8Q?key=RUI-tNB8eJsAK66TPJ_TuGwv)

We then go to /tmp to get a file "linpeas.sh" from our attacker machine-

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd2vP6OaMJKSve89Z0OHr1PTTezxU_JVIEINhkVGCRBoyIW1EMKC-LYbSNGhSte6UysQkUVHB6mp-o3WCJRYxRRTaO4_16Eeazp8KgoBMaPvwNMqTUlgdUX1CF1F-SpotAGFGVO?key=RUI-tNB8eJsAK66TPJ_TuGwv)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeCN-bMqMYCZI_97xk0gIy6hkueJc5n17jRdwyu83lLyKMweLkoWwrjwHbhDF5P95-RZYej73oCa84aO1op82LeJ4ZxjQpX8TE5hGVS-TYOlNy8fXF06VRf4srS7PmaMoLoOTQ-TA?key=RUI-tNB8eJsAK66TPJ_TuGwv)

Linpeas.sh is run on the target.

A tmp.sh is located in the root directory that we can write to and is executed by samsingh every now and then. We paste in our shell and escalate to samsingh -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXchHOoVgFn0qZurNSfwaDyK4hxrgq6XuRSMl_jfm9Unn9qtLzgJpFXbyCTwcmb9ePyxadt0c04a0GwG2o0f6Bw2_SJpj-WxpjVl24iNblRFml0e6HnCQvh-dKMBivCtEBKsXJYl8Q?key=RUI-tNB8eJsAK66TPJ_TuGwv)

Now we are the user ‘samsingh’-

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfyRXokhivY6fLGQx4nqNDsHFuPewpPsDMo7a5ZzaD_zSQ96cyT-fCaUHjAT-12O2OGJHZvc3HdoVD0cpUA_xdB1y4m3RG4Af3q06uSpK6H-i-5ivxGutoBs56yh9BZWQ6_ElN6wQ?key=RUI-tNB8eJsAK66TPJ_TuGwv)

  
  
  

And upon running linpeas again we see this-

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdJ9Wjqp2jwabQM07vv6Qar-0MgUiL7E5z-GHynTaO2BnjoWNmAkVCcPjQ-uDCbxf8xjsYirLQYZ-7ic0hwnb7KzYY2gLvF2o_jt25qsfS4D0O9On8n9BakzcquMgJ6lkVvfiXDrg?key=RUI-tNB8eJsAK66TPJ_TuGwv)

As we can run python, we are now able to escalate to root -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf2b4JPJkAvBl2XiEZDRIJizZiTj4FrL6tLzQu8suG1ws4w3MGj_DAdOPxRTlKM6U86VgMJcjwVvLVig7_nseaOkz5d5SXtQCnx7dOukNIoe6vfJNJ87_R1GZgCYaoNdhxChhpAdQ?key=RUI-tNB8eJsAK66TPJ_TuGwv)
