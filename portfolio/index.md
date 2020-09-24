---
works_index: true
hero_text: I'm Palina, UX/UI designer with great coding skills.
title: Portfolio | Palina Kolas
hero_a_text: text a
hero_b_text: text b

---
<Hero :text="$page.frontmatter.hero_text" />
<Hero :text="$page.frontmatter.hero_a_text" />
<Hero :text="$page.frontmatter.hero_b_text" />
<WorksList />