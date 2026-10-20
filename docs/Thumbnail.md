# Thumbnail

The thumbnail resource type represents a thumbnail for an image, video, document, or any item that has a bitmap representation. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**content** | **string** | The content stream for the thumbnail. | [optional] [default to undefined]
**height** | **number** | The height of the thumbnail, in pixels. | [optional] [default to undefined]
**sourceItemId** | **string** | The unique identifier of the item that provided the thumbnail. This is only available when a folder thumbnail is requested. | [optional] [default to undefined]
**url** | **string** | The URL used to fetch the thumbnail content. | [optional] [default to undefined]
**width** | **number** | The width of the thumbnail, in pixels. | [optional] [default to undefined]
**libre_graph_mimeType** | **string** | The mime type the thumbnail is served in, e.g. &#x60;image/png&#x60;. It can differ from the mime type of the item the thumbnail belongs to, for example when the thumbnail is an image taken from inside the item, such as the cover art of an audio file.  | [optional] [default to undefined]

## Example

```typescript
import { Thumbnail } from './api';

const instance: Thumbnail = {
    content,
    height,
    sourceItemId,
    url,
    width,
    libre_graph_mimeType,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
