Basic S3 comman line

  aws s3 ls
  aws s3 ls s3://mybucket
  aws s3 ls s3://mybucket --recursive

  aws s3 cp s3://mybucket/test.txt test2.txt
  aws s3 cp s3://mybucket . --recursive 

  aws s3 cp test.txt s3://mybucket/test2.txt
  aws s3 cp myDir s3://mybucket/ --recursive --exclude "*.jpg"
