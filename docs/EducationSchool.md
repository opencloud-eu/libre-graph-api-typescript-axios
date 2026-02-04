# EducationSchool

Represents a school

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | The unique identifier for an entity. Read-only. | [optional] [readonly] [default to undefined]
**displayName** | **string** | The organization name | [optional] [default to undefined]
**schoolNumber** | **string** | School number | [optional] [default to undefined]
**externalId** | **string** | External identifier of the school | [optional] [default to undefined]
**terminationDate** | **string** | Date and time at which the service for this organization is scheduled to be terminated | [optional] [default to undefined]

## Example

```typescript
import { EducationSchool } from './api';

const instance: EducationSchool = {
    id,
    displayName,
    schoolNumber,
    externalId,
    terminationDate,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
