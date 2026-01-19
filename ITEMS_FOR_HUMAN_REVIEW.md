# Items Requiring Human Review

**Date:** 2026-01-19  
**Context:** Documentation cleanup for public release  
**Reviewer:** Repository maintainer

---

## Priority 1: Internal Marketing/Preparation Materials

### 1. ANNOUNCEMENT_MATERIALS.md (14KB)

**Contents:** Social media threads, blog post drafts, LinkedIn posts

**Question:** Should this be part of the public repository?

**Options:**
- [ ] **Keep as-is** - Shows how to communicate technical work to broader audience
- [ ] **Move to .github/examples/** - Keep but indicate it's a template
- [ ] **Remove entirely** - Marketing materials don't belong in technical repo
- [ ] **Keep only technical parts** - Strip social media, keep blog outline

**Recommendation:** Move to `.github/examples/announcement-template.md` or remove

**Rationale:** While it shows communication strategy, it may clutter the repo and become outdated quickly.

---

### 2. DEMO_VIDEO_SCRIPT.md (5.8KB)

**Contents:** Voiceover timing, OBS setup, screen recording instructions

**Question:** Does this provide value for the open-source community?

**Options:**
- [ ] **Keep as-is** - Template for educational video creation
- [ ] **Move to examples/** - Position as "how to create demos"
- [ ] **Remove entirely** - Too specific to one video
- [ ] **Condense to 1-page** - Keep key talking points only

**Recommendation:** Remove or condense to key points

**Rationale:** Very specific to internal video creation, unlikely to be useful for contributors.

---

### 3. PAPER_PREP_SUMMARY.md (11KB)

**Contents:** Checklist of files created for academic submission, progress tracking

**Question:** Is this transparency valuable or just noise?

**Options:**
- [ ] **Keep as-is** - Shows research process transparency
- [ ] **Archive in git history** - Remove but keep in commit history
- [ ] **Condense into README** - Merge key points into main documentation
- [ ] **Move to paper/** - Keep with paper materials

**Recommendation:** Archive (remove from main branch)

**Rationale:** This is a snapshot in time that becomes outdated. Historical value only.

---

### 4. PUBLICATION_READINESS.md (9.3KB)

**Contents:** Release checklist, build verification, internal status updates

**Question:** Is this useful for future releases or just historical?

**Options:**
- [ ] **Keep as-is** - Documents release process
- [ ] **Convert to template** - Make it reusable for v1.2.0, v1.3.0, etc.
- [ ] **Move to .github/workflows/** - Keep with CI/CD materials
- [ ] **Remove entirely** - Information now outdated

**Recommendation:** Convert to release checklist template or archive

**Rationale:** Could be valuable for future releases if generalized.

---

### 5. PUBLISHING_INSTRUCTIONS.md (8.7KB)

**Contents:** Step-by-step PyPI publishing, git tagging, badge updates

**Question:** Should we document our publishing workflow?

**Options:**
- [ ] **Keep as-is** - Useful for maintainers and fork authors ✅ RECOMMENDED
- [ ] **Move to CONTRIBUTING.md** - Merge with contribution guidelines
- [ ] **Keep but rename** - Make it clear it's for maintainers: `MAINTAINER_GUIDE.md`
- [ ] **Remove entirely** - Standard practice, well documented elsewhere

**Recommendation:** **KEEP** - Rename to `MAINTAINER_GUIDE.md`

**Rationale:** Provides value for maintainers and those who want to publish forks. PyPI-specific details are helpful.

---

## Priority 2: Academic Paper Materials

### 6. paper/draft_main.md (27KB) & paper/paper_draft.md (18KB)

**Contents:** Two versions of the academic paper draft

**Question:** Should paper drafts be public before publication?

**Options:**
- [ ] **Keep both** - Shows evolution of ideas
- [ ] **Keep one only** - Choose most recent, delete other
- [ ] **Remove both** - Wait for arXiv publication
- [ ] **Move to private branch** - Accessible to team but not public

**Recommendation:** **REMOVE BOTH** until paper is accepted/published

**Rationale:** Academic convention is to not share drafts publicly before peer review. Wait for arXiv.

**Alternative:** If paper is already on arXiv, replace with link to published version.

---

### 7. paper/PAPER_CHECKLIST.md (9.4KB)

**Contents:** Submission checklist with venue requirements, formatting rules

**Question:** Is this internal process or useful reference?

**Options:**
- [ ] **Keep as-is** - Shows thorough research process
- [ ] **Move to paper/internal/** - Clear separation
- [ ] **Remove entirely** - Internal tracking document
- [ ] **Keep as template** - Useful for others submitting papers

**Recommendation:** Keep as template or move to paper/internal/

**Rationale:** Could help other researchers with submission process. NeurIPS/ICML checklists are useful.

---

## Priority 3: Documentation Organization

### 8. Multiple README files

**Current Structure:**
- `/README.md` (29KB) - Main repository README
- `/datasets/README.md` - Dataset documentation
- `/experiments/README.md` - Experiments guide
- `/paper/README.md` - Paper materials index
- `/reproducibility/README.md` - Reproduction instructions
- `/wiki/README.md` - Wiki navigation

**Question:** Is this well-organized or confusing?

**Options:**
- [ ] **Keep as-is** - Each directory self-documents ✅ RECOMMENDED
- [ ] **Add navigation links** - Cross-reference between READMEs
- [ ] **Consolidate some** - Merge experiments + reproducibility
- [ ] **Create sitemap** - Add `/DOCUMENTATION_MAP.md`

**Recommendation:** **KEEP** but add cross-references

**Rationale:** Standard GitHub pattern. Each README explains its directory well.

---

## Suggested Actions by Priority

### ✅ Do Now (Clear Decisions)

1. **Remove paper drafts** until publication:
   ```bash
   git rm paper/draft_main.md paper/paper_draft.md
   ```

2. **Rename PUBLISHING_INSTRUCTIONS.md**:
   ```bash
   git mv PUBLISHING_INSTRUCTIONS.md MAINTAINER_GUIDE.md
   ```

3. **Archive internal tracking**:
   ```bash
   git rm PAPER_PREP_SUMMARY.md PUBLICATION_READINESS.md
   # Or move to .github/internal/
   mkdir -p .github/internal
   git mv PAPER_PREP_SUMMARY.md .github/internal/
   git mv PUBLICATION_READINESS.md .github/internal/
   ```

### 🤔 Decide Before Release (Requires Judgment)

4. **ANNOUNCEMENT_MATERIALS.md** - Keep, move, or remove?
5. **DEMO_VIDEO_SCRIPT.md** - Remove or condense?
6. **PAPER_CHECKLIST.md** - Keep as reference or remove?

### 🔄 Improve Over Time (Nice to Have)

7. Add cross-references between READMEs
8. Create DOCUMENTATION_MAP.md if structure becomes complex
9. Add "Last Updated" dates to key markdown files

---

## Decision Template

For each flagged file, make a decision:

### ANNOUNCEMENT_MATERIALS.md
- **Decision:** [ ] Keep / [ ] Move / [ ] Remove
- **Action:** (if applicable)
- **Reason:** 

### DEMO_VIDEO_SCRIPT.md
- **Decision:** [ ] Keep / [ ] Move / [ ] Remove
- **Action:** (if applicable)
- **Reason:** 

### PAPER_PREP_SUMMARY.md
- **Decision:** [ ] Keep / [ ] Archive / [ ] Remove
- **Action:** (if applicable)
- **Reason:** 

### PUBLICATION_READINESS.md
- **Decision:** [ ] Keep / [ ] Template / [ ] Remove
- **Action:** (if applicable)
- **Reason:** 

### PUBLISHING_INSTRUCTIONS.md
- **Decision:** [x] Keep (rename to MAINTAINER_GUIDE.md)
- **Action:** `git mv PUBLISHING_INSTRUCTIONS.md MAINTAINER_GUIDE.md`
- **Reason:** Useful for maintainers and fork authors

### paper/draft_main.md & paper/paper_draft.md
- **Decision:** [x] Remove (wait for publication)
- **Action:** `git rm paper/draft_main.md paper/paper_draft.md`
- **Reason:** Academic convention - no drafts before peer review

### paper/PAPER_CHECKLIST.md
- **Decision:** [ ] Keep / [ ] Move / [ ] Remove
- **Action:** (if applicable)
- **Reason:** 

---

## Timeline

**Target Decision Date:** Before public release announcement  
**Who Decides:** Repository owner (@imran-siddique)  
**Implementation:** Automated agent or manual git commands

---

**Next Steps:**
1. Review this document
2. Make decisions for each flagged item
3. Execute actions (git commands provided)
4. Update DOCUMENTATION_CLEANUP_SUMMARY.md with final decisions
5. Proceed with public release
