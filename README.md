# `Refine the Break-Glass`

## `Usage`

```bash
git clone https://github.com/efrikin/refine-the-break-glass.git
git lfs pull
```

### `Preview mode`

#### `Up`

```bash
podman kube play quarto-preview.yaml
```

#### `Down`

```bash
podman kube play quarto-preview.yaml --down
```

#### `Debugging`

```bash
podman pod logs quarto-preview
```

### Export to PDF

```
podman run \
    --name pdf-export \
    -u root \
    --rm \
    -v $(pwd)/pdf:/slides:Z \
    -ti \
    --net host \
    ghcr.io/astefanutti/decktape \
        reveal \
        --fragments=true \
        http://localhost:6411/ \
        refine-the-break-glass.pdf
```

## References

- [Export to PDF](https://github.com/astefanutti/decktape)

## `License`

The code for the website is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/)
(CC BY-SA 4.0).

