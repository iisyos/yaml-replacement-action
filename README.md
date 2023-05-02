# YAML Replacement action

This action replace specific value in YAML file.

## Motivation & Description

If you want to update file cached in browser, you change the file's url like

```js
<script src="production.min.js?ver=1"></script>
```
to
```js
<script src="production.min.js?ver=2"></script>
```

The tails of url is often managed in YAML file.
So when you deploy application, you need update the phrase `1` to `2`.
This action update the phrase to current date formatted `YYYYMMDDhhmm`.


## Inputs

### `yaml-file-path`

**Required** Path of your YAML file which need replacement.

### `target-key`

**Required** The key of value need replacement in YAML file.

### `need-push`

If you need push this this changes, set `true`, default `false`


## Example usage

```yaml
uses: iisyos/yaml-replacement-action@v1
with:
  yaml-file-path: 'setting.yaml'
  target-key: 'step.revision'
  need-push: true
```

If above specification, setteng.yaml like under format

```yaml
step:
  revision: '202301011200' # <- replace
```