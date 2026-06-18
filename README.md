# Shooting Project
Unreal Engine 5로 제작한 3인칭 몬스터 슈팅 게임

---

## Overview
플레이어가 필드를 돌아다니며 몬스터를 사격하고, 다양한 기믹(회복·슬로우·점프대 등)을 활용해 전투를 풀어가는 3인칭 슈팅 게임입니다.
몬스터는 Behavior Tree 기반 AI로 플레이어를 탐지·추격·공격합니다.

- **Engine**: Unreal Engine 5.7
- **Genre**: 3인칭 슈팅 / 서바이벌
- **AI**: Behavior Tree (탐지 → 추격 → 공격)

---

## Controls

| 동작 | 입력 |
|:--|:--:|
| 이동 | <kbd>W</kbd> <kbd>A</kbd> <kbd>S</kbd> <kbd>D</kbd> |
| 시점 / 조준 | <kbd>Mouse</kbd> |
| 사격 | <kbd>L-Click</kbd> |
| 점프 | <kbd>Space</kbd> |


---

## Features

---

### Monster Combat 
몬스터가 플레이어를 탐지하면 추격·공격하고, 플레이어는 총으로 쏴 처치할 수 있습니다.

<img width="426" height="240" alt="MonsterCombat" src="https://github.com/user-attachments/assets/b8364ca1-930d-4cfc-bc23-a2bd6dcee3bf" />

---

### HP Up, Reload 

회복 아이템을 획득하면 체력이 차오릅니다. R을 누르면 재장전을 할 수 있습니다.

<img width="426" height="240" alt="HpUp" src="https://github.com/user-attachments/assets/fa40e877-aa63-478e-ad70-abc83e9a1421" />

---

### Slow Down 

특정 구역/기믹에 들어가면 일정 시간 동안 속도가 느려집니다.

<img width="426" height="240" alt="SlowDown" src="https://github.com/user-attachments/assets/ab9e9682-73b7-43ff-954e-ab147b356953" />

---

### Falling Tree
상호작용 시 나무가 쓰러지는 환경 기믹입니다. 쓰러지는 방향에 있을 시 데미지를 입습니다.

<img width="426" height="240" alt="Tree" src="https://github.com/user-attachments/assets/f2d8e0b7-5150-4f64-868a-b9cb53480f37" />

---

### Jump Mushroom (점프 버섯)
버섯 점프대를 밟으면 높이 튕겨 오릅니다.

<img width="426" height="240" alt="Mushroom" src="https://github.com/user-attachments/assets/c3f25525-c583-4c1e-9cd1-4c34648595b2" />

---

## How It Works
- **Player**: `BP_Player`, `BP_PlayerController` — 이동·조준·사격 처리
- **Monster AI**: `BT_Slime`, `BB_Slime`, `BTService_FindPlayer`, `BTTask_Attack`, `BTTask_FindPatrolLocation`, `BTDecorator_IsPlayerInRange` — 순찰 → 탐지 → 추격 → 공격
- **Gimmicks**: `BP_HpUp`, `BP_SlowDown`, `BP_FallingTree`, `BP_JumpMushroom`, `BP_Balloon`
- **System**: `BP_GameMode`, `BP_HUD`, `WBP_UITest`

---

## Assets
- ParagonLtBelica / ParagonMurdock (Epic Paragon)
- Monster For Survival Game
- VRS Low Poly Nature Essentials
- Crosshair Free Pack
