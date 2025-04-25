# 🔐 Secure AWS S3 with IAM Policies and Encryption

This project demonstrates how to securely configure an Amazon S3 bucket using IAM policies, encryption, and access restrictions, as part of a cloud security task for CodTech Internship.

## ✅ What Was Implemented

- **IAM User Setup:**  
  Created a user named `s3readonlyuser` with limited permissions using a custom IAM policy.

- **S3 Bucket Creation:**  
  A bucket named `production-level-bucket` was created with:
  - Public access **fully blocked**
  - **Bucket versioning** optionally enabled
  - **SSE-S3** (AES-256) server-side encryption enabled

- **Custom IAM Policy:**  
  Granted the IAM user only the `s3:ListBucket` permission to allow viewing the bucket, while **denying all object-level actions** (upload/download/delete).

- **Testing IAM User Access:**  
  - ✅ Able to list all buckets.
  - ❌ Access denied for reading or modifying objects inside the bucket.

## 🔒 IAM User Permissions Summary

| Feature            | Permission          | Allowed |
|--------------------|---------------------|---------|
| View Bucket        | `s3:ListBucket`     | ✅ Yes  |
| Download Files     | `s3:GetObject`      | ❌ No   |
| Upload Files       | `s3:PutObject`      | ❌ No   |
| Delete Files       | `s3:DeleteObject`   | ❌ No   |
| Modify Bucket      | `s3:PutBucketPolicy`| ❌ No   |

## 🧪 IAM User Behavior

| Action                        | Status | Remarks                        |
|------------------------------|--------|--------------------------------|
| List all buckets             | ✅ Yes | Allowed by default policy      |
| View objects in the bucket   | ❌ No  | Denied by bucket policy        |
| Download objects             | ❌ No  | Access Denied                  |
| Upload/Delete objects        | ❌ No  | Access Denied                  |
| Modify bucket settings       | ❌ No  | Access Denied                  |

## 📸 Screenshots
Please refer to the Documentation file for supporting images related to IAM setup, bucket creation, and access testing.
