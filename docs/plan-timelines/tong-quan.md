# Tổng quan Kế hoạch sản xuất

Tài liệu này mô tả chi tiết kế hoạch sản xuất game "Bảo vệ khu phố" từ **01/02/2026 đến 30/06/2026** (5 tháng).

## 1. Tổng quan Timeline

| Thông tin | Chi tiết |
| :--- | :--- |
| **Ngày bắt đầu** | 01/02/2026 |
| **Ngày kết thúc** | 30/06/2026 |
| **Tổng thời gian** | 21 tuần (150 ngày) |
| **Milestone chính** | 5 phases |
| **Team size (dự kiến)** | 8-10 người |

### 1.1. Team Structure

| Role | Số lượng | Trách nhiệm chính |
| :--- | :--- | :--- |
| **Game Designer** | 1 | Game design, balancing, documentation |
| **Developer** | 2-3 | Core gameplay, systems, UI implementation |
| **2D Artist** | 2 | Character, environment, UI art |
| **VFX Artist** | 1 | Particle effects, combat effects, UI animations |
| **Sound Designer** | 1 | SFX, BGM, audio implementation |
| **QA Tester** | 1 | Testing, bug reporting |
| **Project Manager** | 1 (part-time) | Coordination, timeline tracking |

---

## 2. Phase Breakdown (5 Phases)

### Phase 1: Foundation (Tháng 2 - Tuần 1-4)
**Timeline:** 01/02 - 28/02 (4 tuần)

**Mục tiêu:** Setup dự án, core combat, data structure

**Deliverables:**
- Project setup hoàn chỉnh (Unity/Godot)
- Core combat system working
- Data management system
- First playable build

### Phase 2: Core Systems (Tháng 3 - Tuần 5-8)
**Timeline:** 01/03 - 31/03 (4.5 tuần)

**Mục tiêu:** UI framework, stats, equipment, AFK

**Deliverables:**
- UI framework hoàn chỉnh
- Stats và progression system
- Equipment system với merge
- AFK calculation working

### Phase 3: Content & Depth (Tháng 4 - Tuần 9-13)
**Timeline:** 01/04 - 30/04 (4 tuần)

**Mục tiêu:** Skills, teammates, complete art assets

**Deliverables:**
- Skill system với 20+ skills
- Teammate system với 5 characters
- Art assets cho Chapter 1-2
- VFX cho combat

### Phase 4: Economy & Monetization (Tháng 5 - Tuần 14-17)
**Timeline:** 01/05 - 31/05 (4 tuần)

**Mục tiêu:** Gacha, shop, economy balancing

**Deliverables:**
- Gacha system hoàn chỉnh
- Shop implementation
- IAP integration
- Economy balanced

### Phase 5: Polish & Launch Prep (Tháng 6 - Tuần 18-21)
**Timeline:** 01/06 - 30/06 (4 tuần)

**Mục tiêu:** Audio, VFX polish, testing, optimization

**Deliverables:**
- Full audio (BGM + SFX)
- All VFX polished
- Performance optimized
- Beta build ready

---

## 3. Gantt Chart Timeline

```mermaid
gantt
    title Production Timeline (01/02/2026 - 30/06/2026)
    dateFormat YYYY-MM-DD

    section Phase 1: Foundation
    Project Setup           :p1a, 2026-02-01, 2d
    Data System             :p1b, after p1a, 3d
    Core Combat             :p1c, after p1b, 4d
    Enemy Spawning          :p1d, after p1c, 3d
    Save/Load               :p1e, after p1b, 3d
    Main Character Art      :p1f, 2026-02-01, 8d
    Enemy Art               :p1g, after p1f, 9d

    section Phase 2: Core Systems
    UI Framework            :p2a, 2026-03-01, 3d
    Stats System            :p2b, after p2a, 4d
    Equipment System        :p2c, after p2b, 7d
    AFK System              :p2d, after p2c, 3d
    Equipment Art           :p2e, 2026-03-01, 10d
    UI Design               :p2f, after p2e, 6d

    section Phase 3: Content
    Skill System            :p3a, 2026-04-01, 10d
    Teammate System         :p3b, after p3a, 8d
    Boss Mechanics          :p3c, after p3b, 3d
    Teammate Art            :p3d, 2026-04-01, 17d
    Boss Art                :p3e, after p3d, 8d
    Skill VFX               :p3f, 2026-04-01, 16d

    section Phase 4: Economy
    Currency System         :p4a, 2026-05-01, 2d
    Gacha System            :p4b, after p4a, 8d
    Shop System             :p4c, after p4b, 3d
    IAP Integration         :p4d, after p4c, 4d
    Gacha Art & VFX         :p4e, 2026-05-01, 9d
    Skill SFX               :p4f, 2026-05-01, 10d

    section Phase 5: Polish
    Audio Integration       :p5a, 2026-06-01, 3d
    Performance Opt         :p5b, after p5a, 5d
    Bug Fixing Sprint 1     :p5c, after p5b, 4d
    Bug Fixing Sprint 2     :p5d, after p5c, 4d
    BGM Production          :p5e, 2026-06-01, 10d
    Final Polish            :p5f, after p5e, 5d
    QA Final                :p5g, after p5f, 4d
```

---

## 4. Dependencies Map

### Critical Path

```mermaid
flowchart LR
    A[Project Setup] --> B[Data System]
    B --> C[Core Combat]
    C --> D[UI Framework]
    D --> E[Stats System]
    E --> F[Equipment System]
    F --> G[Skill System]
    G --> H[Gacha System]
    H --> I[Final Polish]
    I --> J[Launch Ready]

    style A fill:#ffcdd2,stroke:#c62828
    style J fill:#c8e6c9,stroke:#2e7d32
```

### Cross-Team Dependencies

| Dev Task | Depends On (Art) | Depends On (VFX) | Depends On (Sound) |
| :--- | :--- | :--- | :--- |
| Core Combat | Main character sprite | Hit effects | Combat SFX |
| Equipment System | Equipment icons | Upgrade effects | Upgrade SFX |
| Skill System | Skill icons | Skill VFX | Skill SFX |
| Gacha System | Gacha box art | Reveal effects | Gacha SFX |
| Final Build | All art assets | All VFX | All audio |
