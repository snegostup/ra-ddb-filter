# ra-ddb-filter

DynamoDB filtering for react-admin getList requests

Install:
```
  npm i git+https://github.com/snegostup/ra-ddb-filter
```

Usage:
```javascript
  const { makeFilterVals } = require('ra-ddb-filter')
  ...
  const filterVals = makeFilterVals(filter) // filter is an object that react-admin dataProvider sends to an endpoint ( {"ids":[["..."],["..."]]} )

  const params = {
    TableName: tableName,
    FilterExpression: `... ${filterVals.expression}`,
    ExpressionAttributeNames: { ..., ...filterVals.attrNames },
    ExpressionAttributeValues: { ..., ...filterVals.attrVals },
  }
  const { Items } = await this.docClient.scan(params).promise()
```


