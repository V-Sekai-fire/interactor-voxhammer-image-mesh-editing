# interactor-voxhammer-image-mesh-editing

A container image that edits a masked region of a textured mesh toward a reference image, in a 3D model's latent space.

## What it is for

It inverts a mesh to the model's latent, edits the masked region under the reference image,
pastes the original back outside the mask, and decodes once, so vertices the caller did not
select stay where they were. The step order is a planning domain in `domain.ex`, shared with the
text-conditioned variant, and a hook checks the server's plan against it. The model calls are not
wired into the server yet, so it answers only in stub mode. RFD 1048 owns the packaging.

## Build

The worker stage builds on `weftspun/trellis2-base`, the image
`interactor-trellis2-image-to-textured-mesh` builds, so build that first:

```sh
docker build -t interactor-voxhammer-image-mesh-editing .
```

## Licence

This repository does not state a licence.
