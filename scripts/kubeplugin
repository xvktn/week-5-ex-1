#!/bin/bash

# Define command-line arguments

RESOURCE_TYPE=$1
NAMESPACE=$2

# Retrieve resource usage statistics from Kubernetes
kubectl top $RESOURCE_TYPE -n $NAMESPACE --no-headers | while IFS= read -r line;
do
  # Extract CPU and memory usage from the output
  read NAME CPU MEMORY <<< "$line"

  # Output the statistics to the console
  # "Resource, Namespace, Name, CPU, Memory"
  echo -e "$RESOURCE_TYPE\t$NAMESPACE\t$NAME\t$CPU\t$MEMORY"
done