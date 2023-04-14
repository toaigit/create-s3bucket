Basic S3 comman line
  AWS bucket name is unique for all aws acounts (not just yours)
  The best practice is to use your organization domain name.
  An empty folder will not be considerred at the destination for both cp and sync operations  

  aws s3 ls
  aws s3 ls s3://mybucket
  aws s3 ls s3://mybucket --recursive

  # remove all objects in the bucket
  aws s3 rm s3://mybucket --recursive
  # remove bucket - bucket must be empty
  aws s3 rb s3://mybucket

  # copy a file to your desktop
  aws s3 cp s3://mybucket/test.txt test2.txt
  # copy a whole bucket to your desktop
  aws s3 cp s3://mybucket . --recursive 
  # copy a whole folder to your desktop
  aws s3 cp s3://mybucket/myfolder/ . --recursive

  aws s3 cp test.txt s3://mybucket/test2.txt
  aws s3 cp test.txt s3://mybucket/  (need the end splash)
  # copy files in folder myDir to mybucket w/o creating the myDIR
  aws s3 cp myDir s3://mybucket/ --recursive --exclude "*.jpg"
  # copy files in folder myDir to mybucket and create folder myDir
  aws s3 cp myDir s3://mybucket/myDir --recursive 
  aws s3 cp newdir2/ s3://mydemo.resourceonline.org/newdir2 --recursive
  aws s3 cp newdir2/ s3://mydemo.resourceonline.org/newdir2/ --recursive

  # sync between local folder and buckets
  aws s3 sync . s3://mybucket
  cd myfolder; aws s3 sync . s3://mybucket
  # sync and delete the destination files
  aws s3 sync --delete . s3://mybucket
  aws s3 sync s3://mybucket . --delete OR aws s3 sync --delete s3://mybucket
