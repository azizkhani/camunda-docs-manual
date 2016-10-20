---

title: 'Get Job Logs (POST)'
category: 'History'

keywords: 'historic post query list job log'

---


Query for historic job logs that fulfill the given parameters.
This method is slightly more powerful than the [GET query](ref:#history-get-job-logs) because it allows filtering by historic job logs values of the different types `String`, `Number` or `Boolean`.


Method
------

POST `/history/job-log`


Parameters
----------

#### Query Parameters

<table class="table table-striped">
  <tr>
    <td>firstResult</td>
    <td>Pagination of results. Specifies the index of the first result to return.</td>
  </tr>
  <tr>
    <td>maxResults</td>
    <td>Pagination of results. Specifies the maximum number of results to return. Will return less results if there are no more results left.</td>
  </tr>
</table>


#### Request body

A JSON object with the following properties:

<table class="table table-striped">
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>logId</td>
    <td>Filter by historic job log id.</td>
  </tr>
  <tr>
    <td>jobId</td>
    <td>Filter by job id.</td>
  </tr>
  <tr>
    <td>jobExceptionMessage</td>
    <td>Filter by job exception message.</td>
  </tr>
  <tr>
    <td>jobDefinitionId</td>
    <td>Filter by job definition id.</td>
  </tr>
  <tr>
    <td>jobDefinitionType</td>
    <td>Filter by job definition type.</td>
  </tr>
  <tr>
    <td>jobDefinitionConfiguration</td>
    <td>Filter by job definition configuration.</td>
  </tr>
  <tr>
    <td>activityIdIn</td>
    <td>Only include historic job logs which belong to one of the passed activity ids.</td>
  </tr>
  <tr>
    <td>executionIdIn</td>
    <td>Only include historic job logs which belong to one of the passed execution ids.</td>
  </tr>
  <tr>
    <td>processInstanceId</td>
    <td>Filter by process instance id.</td>
  </tr>
  <tr>
    <td>processDefinitionId</td>
    <td>Filter by process definition id.</td>
  </tr>
  <tr>
    <td>processDefinitionKey</td>
    <td>Filter by process definition key.</td>
  </tr>
  <tr>
    <td>deploymentId</td>
    <td>Filter by deployment id.</td>
  </tr>
  <tr>
    <td>creationLog</td>
    <td>Only include creation logs. Value may only be <code>true</code>, as <code>false</code> is the default behavior.</td>
  </tr>
  <tr>
    <td>failureLog</td>
    <td>Only include failure logs. Value may only be <code>true</code>, as <code>false</code> is the default behavior.</td>
  </tr>
  <tr>
    <td>successLog</td>
    <td>Only include success logs. Value may only be <code>true</code>, as <code>false</code> is the default behavior.</td>
  </tr>
  <tr>
    <td>deletionLog</td>
    <td>Only include deletion logs. Value may only be <code>true</code>, as <code>false</code> is the default behavior.</td>
  </tr>
  <tr>
    <td>sorting</td>
    <td>
      <p>
        A JSON array of criteria to sort the result by. Each element of the array is a JSON object that specifies one ordering. The position in the array identifies the rank of an ordering, i.e. whether it is primary, secondary, etc. The ordering objects have the following properties:
      </p>
      <table>
        <tr>
          <td>sortBy</td>
          <td><b>Mandatory.</b> Sort the results lexicographically by a given criterion. Valid values are <code>timestamp</code>, <code>jobId</code>, <code>jobDefinitionId</code>, <code>jobDueDate</code>, <code>jobRetries</code>, <code>activityId</code>, <code>executionId</code>, <code>processInstanceId</code>, <code>processDefinitionId</code>, <code>processDefinitionKey</code>, <code>deploymentId</code> and <code>occurrence</code>.</td>
        </tr>
        <tr>
          <td>sortOrder</td>
          <td><b>Mandatory.</b> Sort the results in a given order. Values may be <code>asc</code> for ascending order or <code>desc</code> for descending order.
        </tr>
      </table>
    </td>
  </tr>
</table>


Result
------

A JSON array of historic job log objects.
Each historic job log object has the following properties:

<table class="table table-striped">
  <tr>
    <th>Name</th>
    <th>Value</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>id</td>
    <td>String</td>
    <td>The id of the log entry.</td>
  </tr>
  <tr>
    <td>timestamp</td>
    <td>String</td>
    <td>The time when the log entry has been written.</td>
  </tr>
  <tr>
    <td>jobId</td>
    <td>String</td>
    <td>The id of the associated job.</td>
  </tr>
  <tr>
    <td>jobDueDate</td>
    <td>String</td>
    <td>The date on which the associated job is supposed to be processed.</td>
  </tr>    
  <tr>
    <td>jobRetries</td>
    <td>Number</td>
    <td>The number of retries the associated job has left.</td>
  </tr>
  <tr>
    <td>jobExceptionMessage</td>
    <td>String</td>
    <td>The message of the exception that occurred by executing the associated job.</td>
  </tr>
  <tr>
    <td>jobDefinitionId</td>
    <td>String</td>
    <td>The id of the job definition on which the associated job was created.</td>
  </tr>
  <tr>
    <td>jobDefinitionType</td>
    <td>String</td>
    <td>The job definition type of the associated job.</td>
  </tr>
  <tr>
    <td>jobDefinitionConfiguration</td>
    <td>String</td>
    <td>The job definition configuration type of the associated job.</td>
  </tr>
  <tr>
    <td>activityId</td>
    <td>String</td>
    <td>The id of the activity on which the associated job was created.</td>
  </tr>
  <tr>
    <td>executionId</td>
    <td>String</td>
    <td>The execution id on which the associated job was created.</td>
  </tr>
  <tr>
    <td>processInstanceId</td>
    <td>String</td>
    <td>The id of the process instance on which the associated job was created.</td>
  </tr>
  <tr>
    <td>processDefinitionId</td>
    <td>String</td>
    <td>The id of the process definition which the associated job belongs to.</td>
  </tr>
  <tr>
    <td>processDefinitionKey</td>
    <td>String</td>
    <td>The key of the process definition which the associated job belongs to.</td>
  </tr>
  <tr>
    <td>deploymentId</td>
    <td>String</td>
    <td>The id of the deployment which the associated job belongs to.</td>
  </tr>
  <tr>
    <td>creationLog</td>
    <td>boolean</td>
    <td>A flag indicating whether this log represents the creation of the associated job.</td>
  </tr>
  <tr>
    <td>failureLog</td>
    <td>boolean</td>
    <td>A flag indicating whether this log represents the failed execution of the associated job.</td>
  </tr>
  <tr>
    <td>successLog</td>
    <td>boolean</td>
    <td>A flag indicating whether this log represents the successful execution of the associated job.</td>
  </tr>
  <tr>
    <td>deletionLog</td>
    <td>boolean</td>
    <td>A flag indicating whether this log represents the deletion of the associated job.</td>
  </tr>
</table>


Response codes
--------------

<table class="table table-striped">
  <tr>
    <th>Code</th>
    <th>Media type</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>200</td>
    <td>application/json</td>
    <td>Request successful.</td>
  </tr>
  <tr>
    <td>400</td>
    <td>application/json</td>
    <td>Returned if some of the query parameters are invalid, for example if a <code>sortOrder</code> parameter is supplied, but no <code>sortBy</code>. See the <a href="ref:#overview-introduction">Introduction</a> for the error response format.</td>
  </tr>
</table>


Example
-------

#### Request

POST `/history/job-log`

Request body:

```json
{
  "jobId": "aJobId"
}
```

#### Response

```json
[
  {
    "id" : "someId",
    "timestamp" : "2015-01-15T15:22:20",
    "jobId" : "aJobId",
    "jobDefinitionId" : "aJobDefinitionId",
    "activityId" : "serviceTask",
    "jobType" : "message",
    "jobHandlerType" : "async-continuation",
    "jobDueDate" : null,
    "jobRetries" : 3,
    "jobExceptionMessage" : null,
    "executionId" : "anExecutionId",
    "processInstanceId" : "aProcessInstanceId",
    "processDefinitionId" : "aProcessDefinitionId",
    "processDefinitionKey" : "aProcessDefinitionKey",
    "deploymentId" : "aDeploymentId",
    "creationLog" : true,
    "failureLog" : false,
    "successLog" : fase,
    "deletionLog" : false
  }
]
```