
# Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved.
# SPDX-License-Identifier: Apache-2.0


FROM amazon/aws-cli:latest
# OPTIONAL: these configurations are recommeneded for high throughput S3 -> S3 transfer in the same region.

RUN aws configure set default.s3.max_concurrent_requests 64 && aws configure set default.s3.multipart_chunksize 64MB
