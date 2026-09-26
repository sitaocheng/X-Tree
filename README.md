# X-Tree: Tokenizing Reusable Experience for Efficient Agent Generalization

**Sitao Cheng**<sup>1</sup>, **Xunjian Yin**<sup>2</sup>, **Zhiyuan Sun**<sup>1</sup>, **Yuxuan Li**<sup>1</sup>, **Ruiwen Zhou**<sup>3</sup>, **Xiangru Jian**<sup>1</sup>, **Victor Zhong**<sup>1</sup>

<sup>1</sup>University of Waterloo · <sup>2</sup>Duke University · <sup>3</sup>National University of Singapore

[**Project page**](https://sitaocheng.github.io/xtree/) · [**Paper**](#) · [**Blog**](https://sitaocheng.github.io/xtree/blog.html)

> **Status: project in progress.** The code, mined trees and training recipes will be released in this repository. Watch the repository to be notified.

## Overview

X-Tree mines the routines that recur across agent trajectories into a tree of reusable skills, with no LLM calls, and trains on that tree. Each action becomes a typed token `verb⟨role⟩`; adjacent symbols merge by X-Score (recurrence × length × success) while the merge compresses the corpus, and the merges form a hierarchy. The tree enters training in three ways:

- **Offline RL:** each X-Tree node is one RL instance, rewarded for step matching and a depth-scaled completion bonus.
- **Online RLVR:** an adaptive bonus for every mined skill a rollout executes, strongest when the verifier signal is scarce.
- **On-policy self-distillation:** the rendered X-Tree is the self-teacher's privileged context, in place of an LLM-written skill bank.

Experiments cover WebArena, ScienceWorld and WebShop at 1.5B, 3B and 7B.

## Planned release

- The X-Tree miner: canonicalization, X-Score merging and tree construction.
- The mined trees for WebArena, ScienceWorld and WebShop.
- Training and evaluation recipes for offline RL, online RLVR and on-policy self-distillation.

## Citation

```bibtex
@article{cheng2026xtree,
  title   = {X-Tree: Tokenizing Reusable Experience for Efficient Agent Generalization},
  author  = {Cheng, Sitao and Yin, Xunjian and Sun, Zhiyuan and Li, Yuxuan and Zhou, Ruiwen and Jian, Xiangru and Zhong, Victor},
  journal = {arXiv preprint},
  year    = {2026}
}
```

## Contact

Sitao Cheng (sitao.cheng@uwaterloo.ca) and Victor Zhong (victor.zhong@uwaterloo.ca).

## License

Apache-2.0.
