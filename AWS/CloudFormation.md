<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CloudFormation</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h1 id="what-is-cloudformation">What is CloudFormation</h1>
<p>AWS CloudFormation is a service that allows you to model and provision AWS infrastructure resources in a declarative way, using code templates. With CloudFormation, you can define your infrastructure as code, which makes it easier to manage, replicate, and version your AWS resources. This approach helps in automating the deployment and management of your infrastructure, ensuring consistency and reducing manual intervention.</p>
<p>CloudFormation uses templates written in JSON or YAML format to describe the desired state of your infrastructure. These templates can include various AWS resources like EC2 instances, S3 buckets, RDS databases, networking components, IAM roles, and more.</p>
<p>Here’s a simple example of using CloudFormation to create an AWS S3 bucket:</p>
<p><strong>Create a CloudFormation Template:</strong></p>
<p>Save the following content in a file named <code>s3-bucket-template.yml</code>. This CloudFormation template will create an S3 bucket.</p>
<pre><code>Resources:
  MyS3Bucket:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: s3
</code></pre>
<p><strong>Deploy the CloudFormation Stack:</strong></p>
<p>Use the AWS CLI or AWS Management Console to deploy the CloudFormation stack based on the template.</p>
<p><strong>Using AWS Management Console:</strong></p>
<ul>
<li>
<p>Log in to the AWS Management Console.</p>
</li>
<li>
<p>Navigate to the CloudFormation service</p>
</li>
<li>
<p>Click on “Create stack” and upload the <code>s3-bucket-template.yml</code> file.</p>
</li>
</ul>
<p><img src="https://i.imgur.com/GhoTabJ.png" alt="Imgur"></p>
<p><img src="https://i.imgur.com/IOCdRCe.png" alt="Imgur"></p>
<ul>
<li>Here upload the <code>.yml</code>file and clock on next</li>
</ul>
<p><img src="https://i.imgur.com/pWMu8eh.png" alt="Imgur"></p>
<ul>
<li>Now scroll down click on next</li>
</ul>
<p><img src="https://i.imgur.com/pOCSPJ7.png" alt="Imgur"></p>
<ul>
<li>review your stack click on submit</li>
<li>Now in event sections you can see the running process</li>
</ul>
<p><img src="https://i.imgur.com/fH0UL7n.png" alt="Imgur"></p>
<ul>
<li>Follow the steps to create the stack, providing a stack name and any other required information.</li>
</ul>
<p><strong>Using AWS CLI:</strong></p>
<pre><code>aws cloudformation create-stack --stack-name MyS3BucketStack --template-body file://s3-bucket-template.yml 
</code></pre>
<ol>
<li>
<p><strong>Monitor Stack Creation:</strong></p>
<p>You can monitor the stack creation progress in the CloudFormation console or use the following AWS CLI command:</p>
<pre><code>aws cloudformation describe-stacks --stack-name MyS3BucketStack 
</code></pre>
</li>
<li>
<p><strong>Access the Created S3 Bucket:</strong></p>
<p>Once the stack is created, you can access the newly created S3 bucket using the AWS Management Console or AWS CLI. For example, to list the contents of the bucket using the AWS CLI:</p>
<pre><code>aws s3 ls s3://my-example-bucket 
</code></pre>
</li>
<li>
<p><strong>Cleanup:</strong></p>
<p>To delete the stack and associated resources, you can use the AWS CLI:</p>
<pre><code>aws cloudformation delete-stack --stack-name MyS3BucketStack 
</code></pre>
</li>
</ol>
<p>This is a simple example of how to use AWS CloudFormation to create an S3 bucket. CloudFormation supports more complex templates, including parameters, mappings, conditions, outputs, and more, to model and manage your entire infrastructure.</p>
</div>
</body>

</html>
