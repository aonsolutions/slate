# User

## List User

List all User.

`GET https://api.aonSolutions.es/user`


You can use the filter query parameter to fetch User. See the table below for more information.

### Parameters

| Name |  Type  | Description |
|------|--------|-------------|
| email | string | Email |
| company | string | Company |
| group | string | Group |

## Get a single User

`GET https://api.aonSolutions.es/user/:email`

## Create / Edit a User

`POST https://api.aonSolutions.es/user`

### Parameters

| Name |  Type  | Description |
|------|--------|-------------|
| email | string | User email. |
| alias | string | User alias. |
| password | string | User password. |
| companies | [string] | Array of companies (CIF) |
| groups | [string] | Array of groups |

## Delete a User

`DELETE https://api.aonSolutions.es/user/:email`
