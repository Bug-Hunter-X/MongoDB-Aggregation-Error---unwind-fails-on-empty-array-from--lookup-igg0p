# MongoDB Aggregation Error: Handling Empty Arrays in $unwind

This repository demonstrates a common error in MongoDB aggregation pipelines involving `$lookup` and `$unwind`. The error occurs when `$unwind` is used on an empty array resulting from a `$lookup` where no matching documents were found. The detailed explanation and a solution are provided below.

## Problem Description
When using MongoDB's aggregation framework with `$lookup` followed by `$unwind`, an error can occur if the `$lookup` stage does not find any matching documents and results in an empty array. The `$unwind` stage will not handle an empty array gracefully.

## Solution
To address this issue we need to handle the empty array that is returned from the `$lookup` operator using the `$ifNull` operator. The `$ifNull` will check the value of `results` and will replace this with an empty array if the `results` is null.

## Code Example
The files `bug.js` shows how to reproduce the problem and `bugSolution.js` shows the corrected pipeline.
