# Troubleshooting Service Issues with Insight

This article serves as a guide on using Insight to identify and analyze abnormal components in DCE 5.0 and determine the root causes of component exceptions.

Please note that this post assumes you have a basic understanding of Insight's product features or vision.

## Service Map - Identifying Abnormalities on a Macro Level

In enterprise microservice architectures, managing a large number of services with complex interdependencies can be challenging. Insight offers service map monitoring, allowing us to gain a high-level overview of the running microservices in the system.

In the example below, we observe that the node `Insight-Server` is highlighted in red on the service map. By hovering over the node, we can see the error rate associated with it. To investigate further and understand why the error rate is not `0`, we can explore more detailed information:

![01](https://docs.daocloud.io/daocloud-docs-images/docs/en/docs/insight/images/root01.png)

Alternatively, clicking on the service name at the top will take us to the service's overview UI:

![02](https://docs.daocloud.io/daocloud-docs-images/docs/en/docs/insight/images/root02.png)

## Service Overview - Delving into Detailed Analysis

When it becomes necessary to analyze inbound and outbound traffic separately, we can use the filter in the upper right corner to refine the data. After applying the filter, we can observe that the service has multiple `operations` corresponding to a non-zero error rate. To investigate further, we can inspect the traces generated by these `operations` during a specific time period by clicking on "View Traces":

![03](https://docs.daocloud.io/daocloud-docs-images/docs/en/docs/insight/images/find_root_cause/03.png)

![04](https://docs.daocloud.io/daocloud-docs-images/docs/en/docs/insight/images/find_root_cause/04.png)

## Trace Details - Identifying and Eliminating Root Causes of Errors

In the trace list, we can easily identify traces marked as `error` (circled in red in the figure above) and examine their details by clicking on the corresponding trace. The following figure illustrates the trace details:

![05](https://docs.daocloud.io/daocloud-docs-images/docs/en/docs/insight/images/find_root_cause/05.png)

Within the trace diagram, we can quickly locate the last piece of data in an `error` state. Expanding the associated `logs` section reveals the cause of the request error:

![06](https://docs.daocloud.io/daocloud-docs-images/docs/en/docs/insight/images/find_root_cause/06.png)

Following the above analysis method, we can also identify traces related to other `operation` errors:

![08](https://docs.daocloud.io/daocloud-docs-images/docs/en/docs/insight/images/find_root_cause/08.png)
![09](https://docs.daocloud.io/daocloud-docs-images/docs/en/docs/insight/images/find_root_cause/09.png)

## Let's Get Started with Your Analysis!
