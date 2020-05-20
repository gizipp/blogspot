---
layout: post
title: "Pengalaman Refund Tagihan Amazon Web Services (AWS)"
shorttitle: "Pengalaman Refund AWS"
category:
description: "Sharing pengalaman open case dan refund tagihan amazon web service free usage tier yang ngagetin membludak."
tags:
  - sharing
  - ngoprek
  - aws
last_modified_at: 2020-05-20
---

Beberapa waktu kemarin, saya tiba-tiba tertarik untuk mencoba [Amazon Web Services (AWS)](https://aws.amazon.com/free/).

<amp-img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1d/AmazonWebservices_Logo.svg/640px-AmazonWebservices_Logo.svg.png" width="640" height="241" layout="responsive" alt="Amazon Web Service Logo"></amp-img>

***

## Apa itu amazon web services?

Amazon Web Service atau lebih sering disebut AWS adalah layanan-layanan dan infrastruktur *cloud coumputing* (red: komputasi awan) yang dimana mereka saling terintegrasi dan kemudahan kostumisasi.

Ya gitu deh.

Baca aja di [sini pengenalan AWS](https://go.gizipp.com/https://www.cloudindonesia.or.id/pengenalan-amazon-web-services.html)

Nah, apalagi dengan adanya *free usage tier*, tanpa ragu-ragu diriku langsung *apply credit card* dan bersegera mengaktifkan promo gratisan satu tahun ini.

***

Dan setelah menunggu sekitar satu bulan, akhirnya CC telah di tangan dan siap dipakai. Langsung aku aktifkan, verifikasi akun, dan tanpa babibu langsung hajar!

Kucoba bikin *instance* EC2, plus bikin volume EBS, lalu kucoba RDS, lalu kucoba DynamoDB, lalu kucoba ElasticBeanstalk, lalu S3... lalu aku ikut tutorial ini itu.. lalu masih banyak lagi.

Keasikan? Iya!

Dan boleh dibilang AWS ini lebih dari cukup memuaskan, kecuali...

...

...

...

bagian tagihan yang tiba-tiba membludak.

Lho, katanya gratis?

***

## Tagihan bikin kaget!

Diriku cuma bisa melongo ketika datang tagihan yang tiba-tiba 72,93 dollar di *bills* AWS dan sekitar 900ribuan di tagihan kartu kredit.

Iya, hampir sejuta, bulat! :cold_sweat:

Usut-usut punya usut, ini adalah kesalahanku yang <del>tidak</del> sengaja tidak membaca batasan penggunaan ini. Ialah gratis dalam waktu tertentu dan batas penggunaan tertentu.

Batas penggunaan inilah yang kurang aku pahami dan sengaja tidak aku pahami di awal. Yang utamanya, batasan itu adalah sekitaran :

- 30 Gb Amazon EBS + 2,000,000 I/Os
- 5 Gb Amazon S3
- 50 Data Transfer Amazon CloudFront

Dan sebagainya silahkan cek di [https://aws.amazon.com/free/](https://aws.amazon.com/free/) semua produk (ternyata!!) dijelaskan di situ.

Namun karena pada dasarnya aku terlalu khilaf serta keasikan coba-coba, ya mau gimana lagi. Tagihan sudah menjadi bubur. :sweat:

***

Tanpa hujan, tanpa mendung, tiba-tiba menggelegar begitu saja. Menatap bagian *bill* dan *invoice*, aku cuma bisa melongo dengan digit yang tertera disitu. Ialah 72,93 dollar!

>
> Hi AWS and teams,
>
> I'm currently eligible on free tier, so I take my time to trying and getting used with AWS environment. I was creating EC2 Instance, S3, RDS, DynamoDB, EBS, etc to try and learn more about AWS. It was great experience and I must say I really grateful.
>
> Unfortunately, yesterday is surprisingly like a storm because the invoice for May. I found out that my invoice for that month is $71.46. Then I trying to figure about this, because simply I can't believe it.
>
> The cause is, My EBS is went crazy because of I create EC2 instance with volume...
$0.072 per IOPS-month provisioned  = 744.220 IOPS-Mo = $53.58
$0.138 per GB-month of PIOPS (SSD) provisioned storage = 129.556 GB-Mo = $17.88
>
> I know it was my fault.
>
> But, I really hope that... Can AWS team support give some consideration?
>
> The fact is, this instance+EBS even not running with no more than 24 hours, that was only 13 Hrs. As you can see on https://console.aws.amazon.com/billing/home?region=ap-southeast-1#/bill?year=2015&month=5  After no more than 24 hours, I delete this EC2 instance + those EBS. I mostly never has real usage. And I think this bills is kind of non sense with the usage. So I really hope, AWS team can give some consideration for newbie like me. The $71.46 too much for noobs that never had real production deployment.
>
> Regard,
>
> Your 'noobs' customer
>
> Attachments:
> Invoice_53791438.pdf
>

Tanpa pengharapan apa-apa, kecuali karena sebal.

> Hi,
>
> My name is David with AWS Billing Support and I will be more than happy to assist you today!
>
> First off, I'm very sorry for any inconvenience these recent charges have caused as I understand it can be frustrating.
>
> I've reviewed your account, and although your account is eligible for the Free Tier, your usage charges were based on activity outside the specifications of the offer.
>
> As you mentioned, majority of the charges were caused by EBS storage below:
>
> $0.072 per IOPS-month provisioned - Asia Pacific (Singapore)  744.220 IOPS-Mo   $53.58
> $0.138 per GB-month of PIOPS (SSD) provisioned storage - Asia Pacific (Singapore)   129.556 GB-Mo   $17.88
>
> The Free Tier only covers 30 GB of Amazon Elastic Block Storage in any combination of General Purpose (SSD) or Magnetic. I can see that the EBS volume is still running in the Asia Pacific (Singapore) region. Please either create a snapshot if the information is needed, or terminate it entirely. You can then launch another EBS volume that is either General Purpose or Magnetic. If this is not configured soon as possible you will continue to be billed normally. Please review our EC2 pricing page for more details on what is covered by the Free Tier here:
>
> https://aws.amazon.com/ec2/pricing/
>
>Regards to DynamoDB, customers get 25 GB of free storage, as well as up to 25 write capacity units and 25 read capacity units of ongoing throughput capacity (enough throughput to handle up to 200 million requests per month) for free. Please review our DynamoDB pricing page for more details here: https://aws.amazon.com/dynamodb/pricing/
>
>Moving onto S3 charges, although minor, you also exceeded the Free Tier terms. You receive 5 GB of Amazon S3 standard storage, 20,000 Get Requests, 2,000 Put Requests, and 15GB of data transfer out each month for one year. Often, S3 usage is generated by:
>
> * background requests made by a program that works with S3
> * empty buckets with public ACLs
>
> Please take a look into our S3 pricing page for further details: https://aws.amazon.com/s3/pricing/
>
> Now, you were also charged for KMS (Key Management Service) from May going into June's billing period. The Free Tier provides 750 requests - 20,000 free of charge, but AWS KMS customer master key is not. You are charged $1.00 per master key. Please also review our KMS pricing page to know what is covered under the Free Tier program here: https://aws.amazon.com/kms/pricing/
>
> As a onetime courtesy I have processed a full refund of $72.93 USD. This may take up to 3-5 business days to appear on your credit card. Before I can consider issuing a credit for this months current KMS charges, please disable your keys by following the steps provided in our documentation here: https://docs.aws.amazon.com/kms/latest/developerguide/enabling-keys.html
>
> Once you have made the necessary changes, please confirm by responding back to this email.
>
> If you have any further questions or concerns, please do not hesitate to contact us back.
>
> We look forward to hearing from you soon!
>
> Best regards,
>
> David B.
> Amazon Web Services


Dan akhirnya.

<amp-img src="/assets/post/refund-amazon-web-service-aws.png" width="623" height="213" layout="responsive" alt="Refund AWS"></amp-img>


Refund penuh didapatkan olehku. Siapa yang menduga? THR tetep jalan. :D

### Kesimpulan

Jika dirimu merasakan kurang *fair* atas sesuatu yang terjadi padamu, (1) coba kau negosiasikan nasibmu dahulu, (2) kau perjuanganlah dirimu dahulu, (3) janganlah pasrah langsung menerimanya tanpa usaha dan upaya.

Karena sesungguhnya, tak akan pernah ada yang berubah nasib dan dirimu, jikalau tanpa sedikit upaya dari dirimu sendiri untuk mengubahnya.

Sebentar, kenapa tiba-tiba jadi bijak begini?
