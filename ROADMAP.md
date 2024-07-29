# Objetive of this document

This document share the public vision for new improvements on this project.

# Roadmap

## 🚧 Active

-   [Add support to Response object](#add-support-to-response-object)

## ⏳ Planned

-   [Migrate scripts `.mts` to `.ts` files](#migrate-scripts-mts-to-ts-files)
-   [Upgrade build service](#add-support-to-response-object)

## Proposals

### Migrate scripts `.mts` to `.ts` files

> This is a change connected with [Upgrade build service](#Upgrade-build-service).

This change able to upgrade the builder app.

### Upgrade build service

Change rollup per typescript builder.

Prefer folders `/esm`, `/cjs` and `/types`.

## Add support to Response object

Able to receive a [Response](https://developer.mozilla.org/en-US/docs/Web/API/Response) object when is calling the `ICalendar.from` function.

**Sample**

```ts
const res = new Response(
    "BEGIN:VCALENDAR\n" +
        "FOO:20230319\n" +
        "BEGIN:EVENT\n" +
        "END:EVENT\n" +
        "END:VCALENDAR\n",
    {
        headers: {
            "Content-Type": "text/calendar",
        },
    }
);

const payload = await ICalendar.from(res);
```
