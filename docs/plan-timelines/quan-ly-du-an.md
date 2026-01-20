# Quản lý & Vận hành dự án

Thông tin về quy trình quản lý, milestones và vận hành dự án.

## 1. Milestones & Quality Gates

### Milestone 1: First Playable (28/02/2026)
**Criteria:**
- [ ] Combat loop working
- [ ] Can kill enemies and progress
- [ ] Save/Load functional
- [ ] Main character visible

**QA Checklist:**
- Combat feels responsive
- No critical bugs
- Build runs on target devices

### Milestone 2: Vertical Slice (31/03/2026)
**Criteria:**
- [ ] Full UI implemented
- [ ] Stats upgrade working
- [ ] Equipment can be equipped
- [ ] AFK rewards functional

**QA Checklist:**
- Core loop is fun
- Progression feels rewarding
- No game-breaking bugs

### Milestone 3: Content Complete (30/04/2026)
**Criteria:**
- [ ] 20+ skills implemented
- [ ] 5 teammates playable
- [ ] 4 bosses functional
- [ ] Chapter 1-2 art done

**QA Checklist:**
- All systems integrated
- Content variety sufficient
- Performance acceptable

### Milestone 4: Feature Complete (31/05/2026)
**Criteria:**
- [ ] Gacha working
- [ ] Shop functional
- [ ] IAP integrated
- [ ] Economy balanced

**QA Checklist:**
- Monetization tested
- No IAP bugs
- Economy feels fair

### Milestone 5: Launch Ready (30/06/2026)
**Criteria:**
- [ ] All audio implemented
- [ ] All VFX polished
- [ ] Performance optimized
- [ ] Zero critical bugs

**QA Checklist:**
- Stable build
- Passed certification
- Ready for soft launch

---

## 2. Risk Management

### High Risk Items

| Risk | Impact | Probability | Mitigation Strategy |
| :--- | :--- | :--- | :--- |
| Scope creep | High | High | Strict feature freeze sau Phase 3 |
| Art pipeline bottleneck | High | Medium | Có 2 artists, prioritize critical assets |
| Performance issues mobile | High | Medium | Weekly performance testing từ Phase 2 |
| IAP integration complexity | Medium | Medium | Allocate buffer time, test early |
| Team member unavailability | High | Low | Cross-training, documentation |

### Mitigation Actions

1. **Weekly Sprint Reviews:** Mỗi thứ 6, review progress và adjust timeline
2. **Buffer Time:** Mỗi phase có ~10% buffer cho unexpected issues
3. **Parallel Workflows:** Art và Dev làm song song khi có thể
4. **Early Testing:** QA join từ Phase 2
5. **Prototype First:** Test risky features sớm (Gacha, IAP)

---

## 3. Communication & Meetings

### Daily
- **Daily Standup:** 15 phút, 9:00 AM
  - What did you do yesterday?
  - What will you do today?
  - Any blockers?

### Weekly
- **Sprint Review:** Thứ 6, 10:00 AM, 1 tiếng
  - Demo deliverables
  - Review milestone progress

- **Sprint Planning:** Thứ 2, 10:00 AM, 1 tiếng
  - Plan tasks for the week
  - Assign responsibilities

### Bi-Weekly
- **Playtest Session:** Thứ 4, 2:00 PM, 2 tiếng
  - Team plays build
  - Collect feedback
  - Prioritize improvements

### Monthly
- **Milestone Review:** Cuối mỗi tháng, 3 tiếng
  - Evaluate phase completion
  - Adjust roadmap if needed
  - Celebrate wins

---

## 4. Tools & Infrastructure

### Development Tools
- **Engine:** Unity 2022 LTS hoặc Godot 4.2
- **Version Control:** Git + GitHub/GitLab
- **Project Management:** Jira, Trello, hoặc Notion
- **Communication:** Slack/Discord
- **Design Docs:** Google Docs, Figma

### Art Tools
- **2D Art:** Adobe Photoshop, Clip Studio Paint
- **Animation:** Spine hoặc Unity Animator
- **UI Design:** Figma

### Audio Tools
- **DAW:** FL Studio, Ableton Live
- **SFX:** Audacity, Adobe Audition
- **Middleware:** FMOD hoặc Wwise (optional)

### QA Tools
- **Bug Tracking:** Jira
- **Test Devices:** Min 5 devices (iOS + Android)
- **Analytics:** Firebase, Unity Analytics

---

## 5. Success Metrics

### Development KPIs

| Metric | Target | How to Measure |
| :--- | :--- | :--- |
| **Sprint Velocity** | 80% tasks completed | Weekly sprint review |
| **Bug Count** | < 20 critical bugs by M4 | Bug tracker |
| **Build Stability** | 0 crashes per 100 sessions | Analytics |
| **Performance** | 60 FPS on mid-range devices | Profiler |
| **Asset Delivery** | 90% on schedule | Project tracker |

### Quality KPIs

| Metric | Target | How to Measure |
| :--- | :--- | :--- |
| **Code Coverage** | > 60% | Unit tests |
| **Art Consistency** | 100% follows style guide | Art review |
| **Audio Quality** | No clipping, balanced mix | Audio review |
| **UX Flow** | Tutorial completion > 80% | Playtest |

---

## 6. Post-Launch Plan (Preview)

Sau 30/06/2026, team sẽ chuyển sang:

1. **Soft Launch** (Tháng 7): Test ở 1-2 thị trường nhỏ
2. **Live Ops** (Tháng 8+): Events, updates, balancing
3. **Content Updates:** New chapters, characters, skills

**Cadence:**
- Weekly: Bug fixes, balancing
- Bi-weekly: Small content drops
- Monthly: Major content updates

---

## 7. Appendix: Task Assignment Template

### Weekly Task Assignment (Example)

**Week của:** [Date] - [Date]
**Sprint Theme:** [e.g., "Combat Polish"]

| Team Member | Tasks This Week | Estimated Hours | Status |
| :--- | :--- | :--- | :--- |
| Developer A | DEV-003, DEV-004 | 32h | In Progress |
| Developer B | DEV-005, DEV-006 | 28h | Not Started |
| Artist A | ART-003, ART-004 | 30h | In Progress |
| Artist B | ART-005, ART-006 | 35h | Not Started |
| VFX Artist | VFX-002, VFX-003 | 20h | In Progress |
| Sound Designer | SND-001, SND-002 | 24h | Not Started |
| Game Designer | GD-001, GD-006 | 16h + playtesting | In Progress |

---

**Document Version:** 1.0
**Last Updated:** 20/01/2026
**Next Review:** 01/02/2026 (Kickoff meeting)
