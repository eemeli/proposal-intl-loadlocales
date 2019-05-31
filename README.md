# Proposal: Intl.loadLocales

### Stage -1

### Motivation & Scope

Locale-specific data is increasing in size as the scope of Intl is increasing along with the number of locales for which localization data is available. Intl.loadLocales is a proposed API for lazy-loading locale-specific data, allowing for implementations to be deployed with an initial limited subset of potentially supported locales. The proposal does not specify how or from where the data should be loaded or cached, leaving it to implementations to define and configure e.g. network paths if fetching them remotely.

### Syntax

```js
Intl.loadLocales(locales[, options])
```

#### Parameters

- **`locales`**: A string with a BCP 47 language tag, or an array of such strings.
- **`options`**: Optional. An object that may have the `localeMatcher` property.

#### Return value

A promise resolving to an array of strings representing a subset of the given locale tags for which locale data is subsequently available in the Intl object. The promise may also be rejected with a network error or otherwise.
