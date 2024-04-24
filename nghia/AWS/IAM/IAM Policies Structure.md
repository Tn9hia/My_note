Consist of:
- **Version**: policy language version, always include "2012-10-17"
- **Id**: an identifier for the policies (optional)
- **Statement**: one or more individual statement (required)
Statement consists of
- Sid: identifier
- Effect: allow or deny access (Allow, Deny)
- Principal: account/user/role which the policies apply to 
- Action: list of action
- Resources: list of resources
- Condition: when the polices apply to 
```
{
	"Version": "2012-10-17",
	"Id": "S3-Account-Permissions",
	"Statement": [
		{
			"Sid": "1",
			"Effect": "Allow",
			"Principal": {
				"AWS": ["arn:aws:iam::142rqfs:root"]
			},
			"Action": [
				"s3:GetObject",
				"s3: PutObject"
			],
			"Resource": ["arn:aws:s3::bucket/*"]
		}
	]
}
```

