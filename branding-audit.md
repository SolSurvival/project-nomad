Complete audit. Excludes intentional matches inside `admin/inertia/css/app.css` (the design-token file itself) and the two `#731` issue-number mentions in `pages/settings/zim/remote-explorer.tsx:87,120` which are GitHub issue refs in comments, not colors.

## A. Hex color literals (TSX / TS)

| File:line | Value(s) | Context |
|---|---|---|
| `admin/inertia/app/app.tsx:29` | `#f5871f` | `progress: { color: '#f5871f' }` — Inertia progress bar (post-rebrand, ember) |
| `admin/inertia/hooks/useMapMarkers.ts:5` | `#a84a12` | `{ id: 'orange', label: 'Orange', hex: '#a84a12' }` — pin palette |
| `admin/inertia/hooks/useMapMarkers.ts:6` | `#994444` | `{ id: 'red', label: 'Red', hex: '#994444' }` — pin palette |
| `admin/inertia/hooks/useMapMarkers.ts:7` | `#6fa06f` | `{ id: 'green', label: 'Green', hex: '#6fa06f' }` — pin palette (rebranded) |
| `admin/inertia/hooks/useMapMarkers.ts:8` | `#2563eb` | `{ id: 'blue', label: 'Blue', hex: '#2563eb' }` — pin palette (Tailwind blue-600) |
| `admin/inertia/hooks/useMapMarkers.ts:9` | `#7c3aed` | `{ id: 'purple', label: 'Purple', hex: '#7c3aed' }` — pin palette (Tailwind violet-600) |
| `admin/inertia/hooks/useMapMarkers.ts:10` | `#ca8a04` | `{ id: 'yellow', label: 'Yellow', hex: '#ca8a04' }` — pin palette (Tailwind yellow-600) |
| `admin/inertia/components/maps/MapComponent.tsx:115` | `#3a3f47` | `background: scaleUnit === 'metric' ? '#3a3f47' : 'white'` — Metric toggle |
| `admin/inertia/components/maps/MapComponent.tsx:116` | `#666` | `color: scaleUnit === 'metric' ? 'white' : '#666'` — Metric inactive text |
| `admin/inertia/components/maps/MapComponent.tsx:127` | `#3a3f47` | `background: scaleUnit === 'imperial' ? '#3a3f47' : 'white'` — Imperial toggle |
| `admin/inertia/components/maps/MapComponent.tsx:128` | `#666` | `color: scaleUnit === 'imperial' ? 'white' : '#666'` — Imperial inactive text |
| `admin/inertia/components/maps/MapComponent.tsx:224` | `#3a3f47`, `#31363f` | `bg-[#3a3f47] ... hover:bg-[#31363f]` — Save button (arbitrary-value, also see C) |
| `admin/inertia/components/maps/MarkerPin.tsx:8` | `#a84a12` | `function MarkerPin({ color = '#a84a12', ... })` — default prop fallback |
| `admin/inertia/components/maps/MarkerPanel.tsx:88` | `#a84a12` | `style={{ color: PIN_COLORS.find(...)?.hex ?? '#a84a12' }}` — fallback when pin id is unknown |
| `admin/inertia/pages/settings/support.tsx:28` | `#FF5E5B`, `#e54e4b` | `bg-[#FF5E5B] hover:bg-[#e54e4b]` — Buy Me a Coffee brand red (third-party brand, see C) |

## B. `rgb()` / `rgba()` values

| File:line | Value | Context |
|---|---|---|
| `admin/inertia/components/maps/MapComponent.tsx:105` | `rgba(0,0,0,0.1)` | `boxShadow: '0 0 0 2px rgba(0,0,0,0.1)'` — map control wrapper shadow |
| `admin/inertia/components/maps/MarkerPin.tsx:10` | `rgba(0,0,0,0.4)` | `style={{ filter: 'drop-shadow(0 1px 2px rgba(0,0,0,0.4))' }}` — pin shadow |
| `admin/inertia/components/systeminfo/InfoCard.tsx:41` | `rgba(255, 255, 255, 0.1)` | inside a `repeating-linear-gradient(...)` stripe overlay |
| `admin/inertia/components/systeminfo/InfoCard.tsx:42` | `rgba(255, 255, 255, 0.1)` | (continuation of same gradient) |

## C. Tailwind arbitrary-value color classes (`xxx-[#...]`)

| File:line | Class(es) | Context |
|---|---|---|
| `admin/inertia/components/maps/MapComponent.tsx:224` | `bg-[#3a3f47]`, `hover:bg-[#31363f]` | Save-marker button (post-rebrand) |
| `admin/inertia/pages/settings/support.tsx:28` | `bg-[#FF5E5B]`, `hover:bg-[#e54e4b]` | Support/donate CTA button (Buy Me a Coffee brand) |

*(Other arbitrary-value classes exist — `border-[3px]`, `text-[0.875em]`, `text-[11px]`, `drop-shadow-[0_0_1px_currentColor]` — but they are sizing/effect, not color, so excluded per scope.)*

## D. `'white'` / `'black'` as style values

### D1. Inline JSX `style={{}}` string literals

| File:line | Property | Context |
|---|---|---|
| `admin/inertia/components/maps/MapComponent.tsx:115` | `background` | `scaleUnit === 'metric' ? '#3a3f47' : 'white'` |
| `admin/inertia/components/maps/MapComponent.tsx:116` | `color` | `scaleUnit === 'metric' ? 'white' : '#666'` |
| `admin/inertia/components/maps/MapComponent.tsx:127` | `background` | `scaleUnit === 'imperial' ? '#3a3f47' : 'white'` |
| `admin/inertia/components/maps/MapComponent.tsx:128` | `color` | `scaleUnit === 'imperial' ? 'white' : '#666'` |

### D2. Tailwind `*-white` / `*-black` utility classes

| File:line | Class | Context |
|---|---|---|
| `admin/inertia/components/ActiveDownloads.tsx:219` | `text-white` | progress bar inner label |
| `admin/inertia/components/ActiveModelDownloads.tsx:192` | `text-white` | progress bar inner label |
| `admin/inertia/components/Alert.tsx:45` | `text-white` | solid-variant returns |
| `admin/inertia/components/Alert.tsx:83` | `text-white` | `bg-desert-orange text-white border border-desert-orange-dark` |
| `admin/inertia/components/Alert.tsx:85` | `text-white` | `bg-desert-red text-white ...` |
| `admin/inertia/components/Alert.tsx:87` | `text-white` | `bg-desert-olive text-white ...` |
| `admin/inertia/components/Alert.tsx:89` | `text-white` | `bg-desert-green text-white ...` |
| `admin/inertia/components/Alert.tsx:91` | `text-white` | `bg-desert-tan text-white ...` |
| `admin/inertia/components/Alert.tsx:114` | `text-white` | icon container, solid variant |
| `admin/inertia/components/Alert.tsx:133` | `text-white text-opacity-90` | message text, solid variant |
| `admin/inertia/components/Alert.tsx:151` | `text-white`, `hover:bg-black hover:bg-opacity-20` | close button hover |
| `admin/inertia/components/CategoryCard.tsx:38` | `text-white` | `bg-desert-green ... text-white ...` card |
| `admin/inertia/components/CategoryCard.tsx:55` | `text-white` | chevron icon |
| `admin/inertia/components/CategoryCard.tsx:62` | `border-white/20` | inner divider |
| `admin/inertia/components/CategoryCard.tsx:79` | `bg-white/10` | tag pill background |
| `admin/inertia/components/CuratedCollectionCard.tsx:21` | `text-white` | `bg-desert-green ... text-white ...` |
| `admin/inertia/components/DebugInfoModal.tsx:70` | `text-black` | textarea — `text-black bg-gray-50` |
| `admin/inertia/components/DebugInfoModal.tsx:77` | `text-white` | submit button — `bg-desert-green ... text-white` |
| `admin/inertia/components/HorizontalBarChart.tsx:97` | `text-white` | inside-bar label |
| `admin/inertia/components/InfoTooltip.tsx:27` | `text-white` | tooltip — `bg-desert-stone-dark text-white` |
| `admin/inertia/components/LoadingSpinner.tsx:20` | `border-white` | `light ? 'border-white' : 'border-text-muted'` |
| `admin/inertia/components/LoadingSpinner.tsx:23` | `text-white` | `light ? 'text-white mt-2' : 'text-text-primary mt-2'` |
| `admin/inertia/components/StorageProjectionBar.tsx:84` | `text-white` | inside-bar label |
| `admin/inertia/components/StyledButton.tsx:59` | `text-white` | green variant |
| `admin/inertia/components/StyledButton.tsx:69` | `text-white` | tan variant |
| `admin/inertia/components/StyledButton.tsx:79` | `text-white` | red variant |
| `admin/inertia/components/StyledButton.tsx:89` | `text-white` | orange variant |
| `admin/inertia/components/StyledButton.tsx:99` | `text-white` | olive variant |
| `admin/inertia/components/StyledButton.tsx:119` | `hover:text-white` | outline variant hover |
| `admin/inertia/components/StyledModal.tsx:51` | `bg-black/50` | modal backdrop |
| `admin/inertia/components/StyledSidebar.tsx:37` | `text-white` | active nav item — `bg-desert-green text-white` |
| `admin/inertia/components/StyledSidebar.tsx:38` | `hover:text-white` | inactive nav hover |
| `admin/inertia/components/StyledSidebar.tsx:64` | `ring-white/5` | sidebar ring |
| `admin/inertia/components/StyledSidebar.tsx:117` | `bg-black/10` | mobile-menu backdrop |
| `admin/inertia/components/StyledSidebar.tsx:133` | `text-white` | close icon |
| `admin/inertia/components/TierSelectionModal.tsx:78` | `bg-black/50` | modal backdrop |
| `admin/inertia/components/TierSelectionModal.tsx:99` | `text-white` | header icon |
| `admin/inertia/components/TierSelectionModal.tsx:102` | `text-white` | dialog title |
| `admin/inertia/components/TierSelectionModal.tsx:110` | `text-white/70`, `hover:text-white` | close button |
| `admin/inertia/components/TierSelectionModal.tsx:197` | `text-white` | selected check icon |
| `admin/inertia/components/WikipediaSelector.tsx:40` | `bg-white` | flag/icon circle |
| `admin/inertia/components/WikipediaSelector.tsx:102` | `text-white` | `bg-desert-green text-white` pill |
| `admin/inertia/components/WikipediaSelector.tsx:108` | `text-white` | `bg-lime-500 text-white` pill |
| `admin/inertia/components/WikipediaSelector.tsx:113` | `text-white` | `bg-blue-500 text-white` pill |
| `admin/inertia/components/WikipediaSelector.tsx:119` | `text-white` | `bg-red-500 text-white` pill |
| `admin/inertia/components/WikipediaSelector.tsx:142` | `text-white` | check icon |
| `admin/inertia/components/chat/ChatAssistantAvatar.tsx:7` | `text-white` | avatar icon |
| `admin/inertia/components/chat/ChatButton.tsx:11` | `text-white` | floating chat button |
| `admin/inertia/components/chat/ChatInterface.tsx:179` | `text-white` | send button |
| `admin/inertia/components/chat/ChatInterface.tsx:183` | `border-white` | spinner — `border-2 border-white border-t-transparent` |
| `admin/inertia/components/chat/ChatMessageBubble.tsx:15` | `text-white` | user message bubble |
| `admin/inertia/components/chat/ChatMessageBubble.tsx:108` | `text-white/70` | user message timestamp |
| `admin/inertia/components/chat/ChatModal.tsx:20` | `bg-black/30` | modal backdrop |
| `admin/inertia/components/chat/ChatSidebar.tsx:61` | `text-white` | active session — `bg-desert-green text-white` |
| `admin/inertia/components/chat/ChatSidebar.tsx:69` | `text-white` | session title (active) |
| `admin/inertia/components/chat/ChatSidebar.tsx:78` | `text-white/80` | session metadata (active) |
| `admin/inertia/components/chat/KnowledgeBaseModal.tsx:140` | `bg-black/30` | modal backdrop |
| `admin/inertia/components/chat/KnowledgeBaseModal.tsx:181` | `text-white` | numbered bullet — `bg-desert-green text-white` |
| `admin/inertia/components/chat/KnowledgeBaseModal.tsx:198` | `text-white` | numbered bullet |
| `admin/inertia/components/chat/KnowledgeBaseModal.tsx:214` | `text-white` | numbered bullet |
| `admin/inertia/components/inputs/Switch.tsx:54` | `bg-white` | switch thumb |
| `admin/inertia/components/maps/MapComponent.tsx:224` | `text-white` | Save button |
| `admin/inertia/components/maps/MarkerPanel.tsx:33` | `text-white` | badge — `bg-desert-orange ... text-white` |
| `admin/inertia/components/maps/MarkerPanel.tsx:51` | `text-white` | badge — `bg-desert-orange ... text-white` |
| `admin/inertia/components/markdoc/Table.tsx:25` | `text-white` | table `<th>` |
| `admin/inertia/components/systeminfo/InfoCard.tsx:48` | `text-white` | card icon |
| `admin/inertia/components/systeminfo/InfoCard.tsx:49` | `text-white` | card title |
| `admin/inertia/pages/easy-setup/index.tsx:452` | `text-white` | step check icon |
| `admin/inertia/pages/easy-setup/index.tsx:463` | `text-white` | step number text |
| `admin/inertia/pages/easy-setup/index.tsx:574` | `text-white` | label (selected variant) |
| `admin/inertia/pages/easy-setup/index.tsx:580` | `text-white` | `bg-desert-green text-white` selected pill |
| `admin/inertia/pages/easy-setup/index.tsx:596` | `text-white` | label (selected variant) |
| `admin/inertia/pages/easy-setup/index.tsx:605` | `text-white` | label (selected variant) |
| `admin/inertia/pages/easy-setup/index.tsx:616` | `text-white` | description (selected variant) |
| `admin/inertia/pages/easy-setup/index.tsx:634` | `border-white bg-white` | unselected checkbox |
| `admin/inertia/pages/easy-setup/index.tsx:639` | `text-white` | check glyph (installed variant) |
| `admin/inertia/pages/easy-setup/index.tsx:799` | `text-white` | success check |
| `admin/inertia/pages/easy-setup/index.tsx:877` | `text-white` | AI model label (selected) |
| `admin/inertia/pages/easy-setup/index.tsx:885` | `text-white` | AI model description (selected) |
| `admin/inertia/pages/easy-setup/index.tsx:907` | `border-white bg-white` | unselected checkbox |
| `admin/inertia/pages/home.tsx:161` | `text-white` | tile — `bg-desert-green ... text-white` |
| `admin/inertia/pages/home.tsx:168` | `text-white` | "NEW" badge — `bg-desert-orange-light ... text-white` |
| `admin/inertia/pages/settings/support.tsx:28` | `text-white` | with `bg-[#FF5E5B]` Buy-Me-Coffee CTA |
| `admin/inertia/pages/settings/system.tsx:282` | `text-white` | drop-shadow label overlay |
| `admin/inertia/pages/settings/update.tsx:541` | `text-white` | step bullet — `bg-desert-green text-white` |
| `admin/inertia/pages/settings/update.tsx:552` | `text-white` | step bullet |
| `admin/inertia/pages/settings/update.tsx:563` | `text-white` | step bullet |
| `admin/inertia/pages/settings/update.tsx:656` | `bg-black bg-opacity-50` | modal backdrop |
| `admin/inertia/pages/settings/update.tsx:675` | `bg-black text-green-400` | terminal-style log view |

---

### Notes (no action implied)

1. **`text-white` paired with `bg-desert-*`** (Alert.tsx, StyledButton.tsx, ChatMessageBubble.tsx, easy-setup/index.tsx, KnowledgeBaseModal.tsx, update.tsx, home.tsx, MarkerPanel.tsx, WikipediaSelector.tsx, ChatSidebar.tsx, CategoryCard.tsx, CuratedCollectionCard.tsx, StyledSidebar.tsx) — these are pairings against your `desert-green`/`desert-orange`/`desert-red`/`desert-tan`/`desert-olive` brand colors. White-on-charcoal still passes legibility under Prometheus, so contrast is fine, but they bypass the theme. A `--color-text-on-brand` token would centralize them.
2. **`bg-black/N` backdrops** (StyledModal.tsx:51, TierSelectionModal.tsx:78, ChatModal.tsx:20, KnowledgeBaseModal.tsx:140, StyledSidebar.tsx:117, update.tsx:656) — standard scrim pattern; black-with-alpha is the conventional choice regardless of theme.
3. **`#666`** in `MapComponent.tsx:116,128` and the literal `'white'` background on the same lines — the inactive Metric/Imperial toggle state. Will look glaring against the charcoal page until rebranded.
4. **`bg-gray-*`, `bg-lime-500`, `bg-blue-500`, `bg-red-500`, `text-green-400`** etc. (generic Tailwind named palettes) also bypass the theme but are outside your audit scope — say the word if you want me to pull those too.
5. `useMapMarkers.ts:8-10` — the blue/purple/yellow pin colors are Tailwind hexes (`#2563eb`, `#7c3aed`, `#ca8a04`) hardcoded for the user-pickable pin palette; similar question to the rebrand call you already made on the green pin.
