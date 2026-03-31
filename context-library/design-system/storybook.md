# Storybook Reference

This is the **production source of truth** for UI components. When suggesting UI solutions, check here first. If a component exists in Storybook, use it. Don't propose custom patterns for covered cases.

---

## Access

**Storybook URL:**
<!-- Add your team's Storybook URL here. Example: https://design.yourcompany.com -->
_[Fill in: your Storybook URL]_

**Status:** <!-- Public / VPN-only / Auth-gated -->
_[Fill in]_

**Version / sync cadence:**
<!-- e.g., Deployed on every merge to main. Version shown in Storybook footer. -->
_[Fill in]_

---

## Component Naming Conventions

Component names in code match Storybook story names exactly. When referencing in specs or docs:
- Use PascalCase: `Button`, `TextInput`, `DataTable`, `Modal`
- Use the story path for specific variants: `Button > Primary`, `TextInput > With Error`
- Props use camelCase: `isDisabled`, `helperText`, `onValueChange`

**Design token prefix:**
<!-- e.g., All color tokens prefixed with `color-`, spacing with `space-`. Figma variables match token names. -->
_[Fill in]_

---

## Component Index

Update this list as your library grows. Group by category.

### Form Controls
<!-- List form components and key variants -->
| Component | Key Variants / Props | Storybook Path | Notes |
|-----------|----------------------|----------------|-------|
| `TextInput` | `default`, `with-label`, `with-error`, `disabled` | Forms > TextInput | |
| `Select` | `single`, `multi`, `searchable` | Forms > Select | |
| `Checkbox` | `single`, `group`, `indeterminate` | Forms > Checkbox | |
| `RadioGroup` | `vertical`, `horizontal` | Forms > RadioGroup | |
| `FormField` | Wraps any input with label + helper text | Forms > FormField | Use this wrapper, not bare inputs |

### Buttons and Actions
| Component | Key Variants / Props | Storybook Path | Notes |
|-----------|----------------------|----------------|-------|
| `Button` | `primary`, `secondary`, `ghost`, `destructive`, `icon-only` | Actions > Button | |
| `IconButton` | `default`, `ghost` | Actions > IconButton | |
| `LinkButton` | | Actions > LinkButton | |

### Layout and Containers
| Component | Key Variants / Props | Storybook Path | Notes |
|-----------|----------------------|----------------|-------|
| `Card` | `default`, `clickable`, `with-header` | Layout > Card | |
| `Modal` | `sm`, `md`, `lg`, `fullscreen` | Overlay > Modal | |
| `Drawer` | `right`, `left` | Overlay > Drawer | |
| `Tooltip` | `dark`, `light` | Overlay > Tooltip | |

### Data Display
| Component | Key Variants / Props | Storybook Path | Notes |
|-----------|----------------------|----------------|-------|
| `DataTable` | `basic`, `sortable`, `selectable`, `paginated` | Data > DataTable | |
| `Badge` | `neutral`, `success`, `warning`, `error`, `info` | Data > Badge | |
| `Tag` | `default`, `removable` | Data > Tag | |
| `EmptyState` | `default`, `with-action` | Data > EmptyState | Always use this, not custom empty states |

### Feedback and Status
| Component | Key Variants / Props | Storybook Path | Notes |
|-----------|----------------------|----------------|-------|
| `Alert` | `info`, `success`, `warning`, `error` | Feedback > Alert | |
| `Toast` | `info`, `success`, `warning`, `error` | Feedback > Toast | |
| `Spinner` | `sm`, `md`, `lg` | Feedback > Spinner | |
| `ProgressBar` | `determinate`, `indeterminate` | Feedback > ProgressBar | |

### Navigation
| Component | Key Variants / Props | Storybook Path | Notes |
|-----------|----------------------|----------------|-------|
| `NavBar` | | Navigation > NavBar | |
| `SideNav` | | Navigation > SideNav | |
| `Tabs` | `default`, `pill` | Navigation > Tabs | |
| `Breadcrumb` | | Navigation > Breadcrumb | |

---

## Contribution Process

To add a new component to the design system:
1. Check there isn't an existing component that covers the case
2. Get design review from the design system owner
3. Document the component using `templates/component-ux-template.md`
4. Add an entry to `context-library/design-system/component-ux/`
5. Open a Storybook PR with the component + stories

**Who owns the design system:**
_[Fill in: name and Slack handle]_

---

## Known Gaps and Workarounds

Note patterns that are commonly needed but not yet in Storybook. Update this list so the copilot knows when to flag "new pattern needed."

| Pattern | Status | Notes |
|---------|--------|-------|
| _[example: Multi-step form wizard]_ | Backlog | Use `Stepper` + `FormField` for now |
| | | |

---

## Changelog

Keep a brief log of significant component additions or breaking changes:

| Date | Change | Migration |
|------|--------|-----------|
| | | |
