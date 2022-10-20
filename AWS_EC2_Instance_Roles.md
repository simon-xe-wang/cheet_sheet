# get nodes within a EKS cluster
kcs get nodes -yaml

# pick a instance from the list above and describe it to get the instance profile id 
aws ec2 describe-instances --instance-ids i-0a0d6878c6f4733e4 --region us-gov-west-1 --profile 023804207645-administrator

# list all instance profiles
aws iam list-instance-profiles --profile 023804207645-administrator --region us-gov-west-1

# get a instance profile to see what instance role the profile contains.
aws iam get-instance-profile --instance-profile-name eks-78c1545e-3ccc-2540-8f15-9dab26c4aa64 --profile 023804207645-administrator --region us-gov-west-1
