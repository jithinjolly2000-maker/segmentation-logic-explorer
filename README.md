<div align="center">

# 🧩 Segmentation & Rules Logic Explorer

### Rule cheat sheet · live rule tester · segment distribution · conflict & overlap check

[![View Live Demo](https://img.shields.io/badge/▶_View_Live_Demo-3b3796?style=for-the-badge&logoColor=white)](https://jithinjolly2000-maker.github.io/segmentation-logic-explorer/)

![Built with](https://img.shields.io/badge/Built_with-Vanilla_JS-f7df1e?style=flat-square&logo=javascript&logoColor=black)
![No dependencies](https://img.shields.io/badge/Dependencies-none-0a7a52?style=flat-square)
![Hosting](https://img.shields.io/badge/Hosted_on-GitHub_Pages-222?style=flat-square&logo=github)
![Data](https://img.shields.io/badge/Data-synthetic_demo-b5841f?style=flat-square)

</div>

---

> ⚠️ **Portfolio demonstration — synthetic data.** Nothing here comes from any employer or real system. This is a self-built learning demo: the 52 codes and their rules are invented for illustration and are **not** any company's actual segmentation or personalisation codes. The 500 customers are generated in the browser from a fixed seed, so the numbers are the same on every visit.

## ✨ What it shows

| Feature | Description |
|---------|-------------|
| 📖 **Rule cheat sheet** | 52 synthetic codes (SEG, VAL, RSK, PZN, RET, CHN) with plain-English logic, eligibility conditions and a risk note. Searchable and filterable by category |
| 🧪 **Rule tester** | Edit a customer profile (tenure, spend band, risk tier, region, products, recent activity) and see which codes match and which conditions passed or failed |
| 📊 **Segment distribution** | How many of the 500 synthetic customers fall in each segment. Inline SVG with a data-table view |
| ⚠️ **Conflict & overlap check** | Flags customers who match two or more codes in a mutually exclusive group, shows the most common overlapping pair, and opens samples in the tester |

## 💡 How it works

Every rule is defined once, as data:

```js
R("PZN-02", "Credit-line increase",
  [["prd","has","CARD"], ["spd","gte",3], ["rsk","lte",3], ["ten","gte",12]],
  "credit", "Proactive limit increase for engaged cardholders.",
  "Allows tier 3, so it collides with RSK-05. Fix: cap at tier 2.")
```

The same definitions drive all three views. The cheat sheet turns conditions into plain English, the tester evaluates them against your profile, and the population analysis counts matches and checks the exclusivity groups. A few rules have deliberate logic defects (overlapping boundaries, a missing risk condition) so the conflict check has something real to catch.

## 💡 Why I built it

I've maintained reference sheets of segmentation and personalisation logic and used them to check
that rules are applied correctly. This demo rebuilds that idea from scratch with invented rules
and synthetic customers, so you can see the method (rules as data, explainable matching, overlap
checks) without any confidential data.

## 🧰 Tech

- **Vanilla HTML / CSS / JavaScript**. No frameworks, no build step, no dependencies
- Seeded random generator (mulberry32) for reproducible synthetic data
- Hand-rendered inline SVG chart; the whole app is a single `index.html`
- Keyboard-usable, labelled controls; pass/fail shown with text and icons, not colour alone
- Hosted free on **GitHub Pages**

## ▶️ Run locally

```bash
start index.html      # Windows — no build step
```

<div align="center">

---

**Built by Jithin J** · [GitHub](https://github.com/jithinjolly2000-maker) · [LinkedIn](https://www.linkedin.com/in/jithin2k)

</div>
