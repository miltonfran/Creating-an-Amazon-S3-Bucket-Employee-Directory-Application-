<h1>Creating an Amazon S3 Bucket Employee Directory Application</h1>

<h2>Description</h2>
We will create an S3 bucket and then modify the EC2 instance holding the application to utilize this S3 bucket.
<br />

<h2>Program walk-through:</h2>

<p align="center">
1. Create the S3 bucket that the application will utilize, go ahead and click Create Bucket, and give it a name.
- Make sure that my bucket is in the same region as the rest of the infrastructure, keep this as the Oregon region or US West 2, and then I will keep all of the other defaults
as they are.
- Go ahead and click Create Bucket.
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742233001/Screenshot_2025-03-14_193209_udqvuk.png"/>
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742233014/Screenshot_2025-03-14_193358_zbamzh.png"/>
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742233031/Screenshot_2025-03-14_193418_jmmx9v.png"/>
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742233050/Screenshot_2025-03-14_193516_rqpnyu.png"/>

  <br />
  
2. Now that the bucket has been successfully created, upload an object to make sure that it all works.
-  I'll click on the name of the bucket, and click upload that's in the center of the page.
-  click that upload button
- I'll click Add Files, and I'll go ahead and upload a photo, After I add that file, I can click Upload

<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742235713/Screenshot_2025-03-14_193548_ccegkg.png"/>
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742236470/Screenshot_2025-03-14_193847_mlelti.png"/>
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742236480/Screenshot_2025-03-14_193914_mpxwkx.png"/>
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742236487/Screenshot_2025-03-14_194025_vzsslu.png"/>

  <br />
  
3. For this bucket and the exercises moving on, we don't want this bucket to be just completely open to the world, we want this bucket and these objects to specifically be accessed by the application.
- we need to adjust the permissions for this bucket, specifically the bucket policy.
- I'm going to go to click on this Permissions tab. And I want to adjust the bucket policy for this bucket.
- So I'm going to scroll down to bucket policy and click the edit button, which will take me to a spot where I can create a bucket policy.

<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742238295/Screenshot_2025-03-14_194500_ktp0rr.png"/>
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742238308/Screenshot_2025-03-14_194524_rvkqxw.png"/>

  <br />

4. Create this bucket policy, I'm going to take the policy that is in the exercise instructions and paste it here, but before I move forward, I save this policy, I need to edit a few things.
- The first thing that I need to edit is the account number so that I am utilizing the correct account, that will be done here where it says, to insert the account number, and I will paste my account number there.
- Change this area where it says, insert bucket name, and put my bucket name there.
- Make sure to do that in both locations and make sure that removing the caret brackets.
- Save the changes
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742245577/Screenshot_2025-03-14_194944_oipz0s.png"/>

  <br />

5. Now my account with this specific role will have access to this bucket and the objects within this bucket.
So now that I have tested uploading an object and created the bucket, as well as providing access to the bucket by that role, I need to modify the application to utilize this bucket.
- Go over to EC2 and click on Instances, clone the instance,  launch the same thing and make sure that I maintain those settings.
- Go over to Actions, and down to Image and Templates, and then I can click launch more like this.
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742250873/Screenshot_2025-03-14_200823_ugvllk.png"/>
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742250925/Screenshot_2025-03-14_200937_vcorid.png"/>

  <br />

6. My instance is going to be a clone of the stopped instance that I've already launched, so what I want to do is make sure that I know that this is my updated application instance.
- I will add -s3 to the end of the instance name, And my image and instance type are going to remain the same.
- Make sure that this is going to be accessible, change my auto-assign public IP to enable, and that's just going to make sure that I have a public IP address to access for this instance.
-  I'm going to expand advanced details, with the expanded advanced details, I can see that the role is already associated to this instance.
-  I'm going to scroll all the way down to the user data, and what I need to do is put my bucket name in here so that now my application knows what bucket to utilize, and so with my bucket name there, I can now launch my instance.
- I will select this instance and copy its public IP address, and then in a new tab, I will go ahead and paste that IP address. and as we can see, the application is up and running.

<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742253098/Screenshot_2025-03-14_201050_q2inbo.png"/>
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742253101/Screenshot_2025-03-14_201610_b0h0ar.png"/>
<img src="https://res.cloudinary.com/dk3bkl3ji/image/upload/v1742253107/Screenshot_2025-03-14_201951_jpylnj.png"/>


