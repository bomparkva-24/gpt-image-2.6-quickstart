# GPT Image 2.6 Quickstart

> **Status: awaiting verified API documentation**

This repository is intended to provide cURL, Python, and Node.js examples for GPT Image 2.6 when its API details can be confirmed from current OpenAI and CometAPI documentation.

As of November 18, 2026, the official OpenAI model URL for `gpt-image-2.6` returns “Page not found,” and the CometAPI listing does not currently expose enough model-specific information to verify the draft examples.

The repository therefore does not yet claim that the proposed model IDs, prices, parameters, features, or response formats are production-ready.

## Verification Checklist

Before publishing runnable examples, confirm:

- Exact model IDs
- API availability
- Supported generation and editing endpoints
- Authentication format
- Valid quality and complexity parameters
- Base64 and URL response behavior
- Supported PNG, JPEG, WebP, SVG, and GIF outputs
- Markup-guided editing support
- Current input and output pricing
- Timeout and retry billing behavior
- Rate limits and maximum image sizes

## Planned Examples

After verification, this repository will include:

```text
examples/
├── generate.sh
├── quickstart.py
└── quickstart.mjs
```

The examples will demonstrate:

- Text-to-image generation
- Safe handling of base64 image responses
- Validated handling of provider-hosted image URLs
- Explicit output formats
- Configurable timeouts
- Error handling without automatic duplicate generation
- Provider-specific parameter validation

## Safe Response Handling

Image APIs may return either base64 data or a hosted URL. Implementations should not assume that `b64_json` is always present.

Before downloading a returned URL:

- Require HTTPS
- Validate the expected provider host
- Limit redirects
- Set a maximum download size
- Verify the response content type
- Use a request timeout
- Avoid overwriting existing files

Automatic retries should be disabled or handled carefully because a timed-out request may still have generated a billable image.

## Documentation

- [OpenAI image-generation documentation](https://developers.openai.com/api/docs/guides/image-generation)
- [GPT Image 2.6 on CometAPI](https://www.cometapi.com/models/openai/gpt-image-2-6/?utm_source=github&utm_medium=distribution&utm_campaign=bom&utm_content=gpt-image-2-6)
- [CometAPI API documentation](https://apidoc.cometapi.com)

## License

MIT
