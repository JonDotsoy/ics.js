## Objective of this document

This document serves as a public declaration of the improvements that will be made to our project. It outlines the key milestones, goals, and timelines for the development and delivery of these enhancements.

## Roadmap

The following roadmap provides an overview of the planned features, their expected release dates, and the current status:

### 🚧 Active

| Feature                                                           | Expected Release Date |
| ----------------------------------------------------------------- | --------------------- |
| [Add support to Response object](#add-support-to-response-object) | Ago, 2024             |

### ⏳ Planned

| Feature                                                                   | Status      | Expected Completion Date |
| ------------------------------------------------------------------------- | ----------- | ------------------------ |
| [Migrate scripts `.mts` to `.ts` files](#migrate-scripts-mts-to-ts-files) | In progress | -                        |
| [Upgrade build service](#add-support-to-response-object)                  | In progress | -                        |

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
