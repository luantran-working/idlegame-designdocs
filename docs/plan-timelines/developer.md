# Công việc Developer (Lập trình)

Chi tiết breakdown công việc cho đội ngũ Developer (2-3 người).

## Phase 1: Foundation (Tháng 2)

| Task ID | Task Name | Duration | Dependencies | Priority |
| :--- | :--- | :--- | :--- | :--- |
| DEV-001 | Setup Unity/Godot project, version control | 2 days | - | Critical |
| DEV-002 | Implement data management system (ScriptableObject/Resource) | 3 days | DEV-001 | Critical |
| DEV-003 | Core combat loop (attack, HP, death) | 4 days | DEV-002 | Critical |
| DEV-004 | Enemy spawning và wave system | 3 days | DEV-003 | Critical |
| DEV-005 | Save/Load system (PlayerPrefs/JSON) | 3 days | DEV-002 | High |
| DEV-006 | Scene management và game flow | 2 days | DEV-003 | High |
| DEV-007 | Build automation script | 1 day | DEV-001 | Medium |

**Total:** ~18 days (4 tuần với buffer)

## Phase 2: Core Systems (Tháng 3)

| Task ID | Task Name | Duration | Dependencies | Priority |
| :--- | :--- | :--- | :--- | :--- |
| DEV-008 | UI framework setup (Canvas, managers) | 3 days | DEV-001 | Critical |
| DEV-009 | Stats system (ATK, HP, CRIT, ASPD) | 4 days | DEV-002 | Critical |
| DEV-010 | Stats upgrade UI với animation | 3 days | DEV-008, DEV-009 | High |
| DEV-011 | Equipment system (slots, equip/unequip) | 4 days | DEV-002 | Critical |
| DEV-012 | Equipment merge system | 3 days | DEV-011 | High |
| DEV-013 | Inventory management | 2 days | DEV-011 | High |
| DEV-014 | AFK calculation system | 3 days | DEV-003 | Critical |
| DEV-015 | Popup system (generic reusable) | 2 days | DEV-008 | Medium |

**Total:** ~24 days

## Phase 3: Content & Depth (Tháng 4)

| Task ID | Task Name | Duration | Dependencies | Priority |
| :--- | :--- | :--- | :--- | :--- |
| DEV-016 | Skill system framework | 4 days | DEV-003 | Critical |
| DEV-017 | Implement 20+ skills | 6 days | DEV-016 | Critical |
| DEV-018 | Skill deck building UI | 3 days | DEV-016, DEV-008 | High |
| DEV-019 | Teammate system (AI, positioning) | 5 days | DEV-003 | Critical |
| DEV-020 | Teammate management UI | 3 days | DEV-019, DEV-008 | High |
| DEV-021 | Bond/Resonance system | 2 days | DEV-019 | Medium |
| DEV-022 | Stage progression system | 2 days | DEV-003 | High |
| DEV-023 | Boss fight mechanics | 3 days | DEV-003 | High |

**Total:** ~28 days

## Phase 4: Economy & Monetization (Tháng 5)

| Task ID | Task Name | Duration | Dependencies | Priority |
| :--- | :--- | :--- | :--- | :--- |
| DEV-024 | Currency system (Gold, Diamond) | 2 days | DEV-002 | Critical |
| DEV-025 | Gacha system (weighted random, pity) | 5 days | DEV-002 | Critical |
| DEV-026 | Gacha UI và animation | 3 days | DEV-025, DEV-008 | High |
| DEV-027 | Shop system implementation | 3 days | DEV-024 | Critical |
| DEV-028 | IAP integration (Google Play/App Store) | 4 days | DEV-024 | Critical |
| DEV-029 | Ads integration (rewarded video) | 3 days | DEV-024 | High |
| DEV-030 | Quest/Achievement system | 4 days | DEV-002 | Medium |
| DEV-031 | Analytics integration (Firebase) | 2 days | DEV-001 | Medium |

**Total:** ~26 days

## Phase 5: Polish & Launch Prep (Tháng 6)

| Task ID | Task Name | Duration | Dependencies | Priority |
| :--- | :--- | :--- | :--- | :--- |
| DEV-032 | Audio integration và sound manager | 3 days | DEV-001 | High |
| DEV-033 | Performance optimization | 5 days | All previous | Critical |
| DEV-034 | Memory optimization | 3 days | DEV-033 | Critical |
| DEV-035 | Bug fixing (sprint 1) | 4 days | All previous | Critical |
| DEV-036 | Bug fixing (sprint 2) | 4 days | DEV-035 | Critical |
| DEV-037 | Build for TestFlight/Internal Testing | 2 days | DEV-035 | Critical |
| DEV-038 | Crash analytics setup | 1 day | DEV-031 | Medium |
| DEV-039 | Final QA fixes | 4 days | DEV-036 | Critical |

**Total:** ~26 days
