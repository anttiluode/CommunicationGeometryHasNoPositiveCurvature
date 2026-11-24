# Communication geometry has no positive curvature

[Check it out!](https://anttiluode.github.io/CommunicationGeometryHasNoPositiveCurvature/)

An interactive reading of three pictures in the paper **“VP ≠ VNP over every field”** (Claude, Anthropic, 2026). It is one self-contained page, `index.html`.

## What the page shows

1. **The price of a wire.** A spectral point prices a wire of *q* states between two parties as *q*^d(u,v). That *d* is a distance, and its limits are what the paper calls *prices*.
2. **Rank becomes distance** (Lemma A.3). A table of rank at most *r* across a split can be routed through two hubs joined by one wire of *r* states. Circuit size enters only through that thin wire.
3. **No positive curvature** (Theorem C.1). Every price satisfies the Bruhat–Tits inequality |zm|² ≤ ½|zx|² + ½|zv|² − ¼|xv|². The page takes the same triangle in a sphere, a plane, a hyperbolic plane and a tree, using each geometry's true distance formula. Only the sphere breaks the inequality.
4. **The flat case, by hand** (Section E.6, Proposition E.10).
   - The setup: the complete network on *k* ≤ 12 nodes, with wire ends at the face centres of a *k*-cube, and hubs ±η·w_S/‖w_S‖ for a balanced set *S* you pick by clicking nodes.
   - Every quantity is computed live in *k* dimensions: crossing wires, ‖w_S‖, the hub saving, the worst saving over all balanced sets, and the forced log₂ *L*.
   - The forced log₂ *L* comes from inequality (E.2) with δ → 0, using the worst saving.
5. **Crossing wires** (Proposition B.2). The page builds the paper's 4 × 4 Meixner-type matrix *M*(*X*) for symbols of size one, takes its determinant Σ Ψ_N X^N in exact integer arithmetic (BigInt), and shows each layer Ψ_N as a table split *ad* | *bc* and *ab* | *cd*, with its measured rank. Adding all layers (*X* = 1) gives back the crossing exactly.
6. **A neighbouring picture from physics.** A layered network drawn as a disk (MERA skeleton, Swingle 2012). Pick a boundary arc; max-flow finds the minimal cut. With scale layers the cut grows like log L; with the chain alone it stays 2. This is not part of the paper's argument.

The geometry was checked against an independent Python computation before publishing. For example, at k = 9 with S = {1, 2, 3} the saving is 1.2105; the worst over all balanced sets is 0.6643 at k = 9 and 0.8462 at k = 12. All of these are above the paper's guaranteed 4k/81.

### Crossing identity check

Computed independently in Python (SymPy) and in the page's JavaScript; the two agree layer by layer. Only even layers are nonzero. Ranks are (across *ad* | *bc*, across *ab* | *cd*):

| q | Θ | reconstruction errors at X = 1 | ranks by layer N |
|---:|---:|---:|---|
| 2 | 16 | 0 / 16 | N=0: 1,4 · N=2: 3,4 · N=4–12: 4,4 · N=14: 4,3 · N=16: 4,1 |
| 3 | 24 | 0 / 81 | N=0: 1,9 · 2: 3,9 · 4: 7,9 · 6–18: 9,9 · 20: 9,7 · 22: 9,3 · 24: 9,1 |
| 4 | 32 | 0 / 256 | N=0: 1,16 · 2: 3,16 · 4: 7,16 · 6: 13,16 · 8–24: 16,16 · 26: 16,13 · 28: 16,7 · 30: 16,3 · 32: 16,1 |

Layer N and layer Θ − N have their ranks swapped. At these sizes only the end layers are cheap. The proof's trade-off, r² + r′² ≤ 2(p² + q²) in Proposition B.3, is an asymptotic statement about large classes of symbols and is shown on the page as a formula, not as measured data.

### Min-cut check

Aligned arcs from site 0, cut size by arc length L: 1→1, 2→2, 4→4, 8→6, 16→8, 32→10 (64 sites). An arc and its complement have the same cut. The min cut is an upper bound on entanglement, not the entanglement itself.

## What it does not show

- The contracting case. The paper proves that the flat case or the contracting case holds, and does not know which.
- Prices of real systems. Prices come from a non-constructive argument (Zorn's lemma) and cannot be computed.
- Anything about P vs NP, or about Boolean circuits.

## Status of the paper, in its own words

The proofs were found and written by an AI model and formalized in Lean 4. No human mathematician has checked them, and whether the Lean statements mean what is intended was judged only by AI readers. This page explains two of its pictures; it does not verify them.

## Viewing

Open `index.html` in a browser, or turn on GitHub Pages (Settings → Pages → Deploy from branch → `main` / root). No build step and no external scripts; only fonts load from Google Fonts.
