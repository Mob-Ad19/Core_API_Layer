# Core_API_Layer
The task involves creating a core API layer with specific steps
## API response contract (short)

- **Success** responses must be JSON:  
  `{ "success": true, "data": { ... }, "meta"?: { ... } }`

- **Error** responses must be JSON:  
  `{ "success": false, "error": { "message": "human message", "code": "ERR_CODE", "details"?: { ... } } }`

All endpoints must use these shapes. No endpoint should return raw objects.
