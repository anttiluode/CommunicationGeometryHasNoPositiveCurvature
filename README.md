# Communication geometry has no positive curvature

[Check it out!](https://anttiluode.github.io/CommunicationGeometryHasNoPositiveCurvature/)

An interactive reading of two pictures in the paper **“VP ≠ VNP over every field”** (Claude, Anthropic, 2026). It is one self-contained page, `index.html`.

## What the page shows

1. **The price of a wire.** A spectral point prices a wire of *q* states between two parties as *q*^d(u,v). That *d* is a distance, and its limits are what the paper calls *prices*.
2. **Rank becomes distance** (Lemma A.3). A table of rank at most *r* across a split can be routed through two hubs joined by one wire of *r* states. Circuit size enters only through that thin wire.
3. **No positive curvature** (Theorem C.1). Every price satisfies the Bruhat–Tits inequality |zm|² ≤ ½|zx|² + ½|zv|² − ¼|xv|². The page takes the same triangle in a sphere, a plane, a hyperbolic plane and a tree, using each geometry's true distance formula. Only the sphere breaks the inequality.
4. **The flat case, by hand** (Section E.6, Proposition E.10).
   - The setup: the complete network on *k* ≤ 12 nodes, with wire ends at the face centres of a *k*-cube, and hubs ±η·w_S/‖w_S‖ for a balanced set *S* you pick by clicking nodes.
   - Every quantity is computed live in *k* dimensions: crossing wires, ‖w_S‖, the hub saving, the worst saving over all balanced sets, and the forced log₂ *L*.
   - The forced log₂ *L* comes from inequality (E.2) with δ → 0, using the worst saving.

The geometry was checked against an independent Python computation before publishing. For example, at k = 9 with S = {1, 2, 3} the saving is 1.2105; the worst over all balanced sets is 0.6643 at k = 9 and 0.8462 at k = 12. All of these are above the paper's guaranteed 4k/81.

## What it does not show

- The contracting case. The paper proves that the flat case or the contracting case holds, and does not know which.
- Prices of real systems. Prices come from a non-constructive argument (Zorn's lemma) and cannot be computed.
- Anything about P vs NP, or about Boolean circuits.

## Status of the paper, in its own words

The proofs were found and written by an AI model and formalized in Lean 4. No human mathematician has checked them, and whether the Lean statements mean what is intended was judged only by AI readers. This page explains two of its pictures; it does not verify them.

## Viewing

Open `index.html` in a browser, or turn on GitHub Pages (Settings → Pages → Deploy from branch → `main` / root). No build step and no external scripts; only fonts load from Google Fonts.
