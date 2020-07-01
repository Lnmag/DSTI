
First log into AWS account management console, and choose the proper S3 service

![Capture1](https://user-images.githubusercontent.com/66074580/86168640-c8c22f80-bb18-11ea-9704-2f89a81fba4f.PNG)

Then you can change the console type to the new one
![Capture2](https://user-images.githubusercontent.com/66074580/86170101-edb7a200-bb1a-11ea-8533-b99502dcad29.PNG)

Once you're on the new console, Start by "Create bucket"
![Capture3_new_console](https://user-images.githubusercontent.com/66074580/86170137-f90acd80-bb1a-11ea-97e5-31a9e24f9a10.PNG)

Choose a proper name with no capital letter, no space, no special signs.
We also choose to stay in US East Virginia, as the test did not work out for Ireland!

![Capture4_name_zone_access](https://user-images.githubusercontent.com/66074580/86170141-fad49100-bb1a-11ea-9efe-974a68a4fd8c.PNG)

Then, no change, just Create Bucket button!
![Capture5_access_create](https://user-images.githubusercontent.com/66074580/86170148-fc9e5480-bb1a-11ea-9b76-d525935851ab.PNG)

Then w ecome back, and select the square "Static Website hosting", and choose "Use this bucket to host a website". 
Typing the name of our file, and save.
![Capture7_properties](https://user-images.githubusercontent.com/66074580/86170170-01fb9f00-bb1b-11ea-9205-28a0c8be6ae7.PNG)

Coming back to the bucket settings, we go into Permissions > Block public Access, to authorize it all.
![Capture8_static_website_hosting](https://user-images.githubusercontent.com/66074580/86170196-09bb4380-bb1b-11ea-9979-c0c1ad0c90ac.PNG)

We see the warning now, it is all public. We go into Bucket Policy to type precoded info to allow public access to our bucket, and save.
____________________________
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::dsti20200630s20hhm/*"
        }
    ]
}
_________________________________________
![Capture9_full_public_access](https://user-images.githubusercontent.com/66074580/86170200-0c1d9d80-bb1b-11ea-8414-4ab8334ab15f.PNG)

Finally we come back to the bucket root menu, and add files : out DSTI.html short file, and the picture contained in the html file:
![Capture10_bucket_policy_full_public_access](https://user-images.githubusercontent.com/66074580/86170204-0de76100-bb1b-11ea-80a4-f0b7e01782a1.PNG)

We only authorize Read object permission, no write
![Capture11_add_web_site_and_pictures](https://user-images.githubusercontent.com/66074580/86170210-1049bb00-bb1b-11ea-980b-26b12ba5f87a.PNG)

We choose the standard storage class for our objects
![Capture12_object_permission_read](https://user-images.githubusercontent.com/66074580/86170215-12137e80-bb1b-11ea-86d0-d0a046aa64d2.PNG)

Both objects are now uploaded
![Capture13_standard_storage_class](https://user-images.githubusercontent.com/66074580/86170220-1475d880-bb1b-11ea-9770-22b99a933a76.PNG)

We click on the dsti.html file, and then on the object url to check the beautiful result : 👍 
![Capture14_uploaded](https://user-images.githubusercontent.com/66074580/86170228-163f9c00-bb1b-11ea-8388-84526549d5f7.PNG)

Then, time to clean up, we come back to the bucket, select the 2 objects, and.. delete.
![Capture15_beautiful_dsti_page](https://user-images.githubusercontent.com/66074580/86170233-18095f80-bb1b-11ea-9e0c-6d3c4fd486b5.PNG)

Then, we keep on cleaning, and delete the bucket!
![Capture16_clean_up_the_mess](https://user-images.githubusercontent.com/66074580/86170239-19d32300-bb1b-11ea-83ba-97b89b1cb347.PNG)

Last step to clean up : type the name to confirm, and it is done!
![Capture17_full_clean_up_bucket](https://user-images.githubusercontent.com/66074580/86170246-1d66aa00-bb1b-11ea-87a4-a47a04d34eec.PNG)
![Capture18_really_full_clean_up_bucket](https://user-images.githubusercontent.com/66074580/86170253-1f306d80-bb1b-11ea-9107-8a052ad1012a.PNG)
