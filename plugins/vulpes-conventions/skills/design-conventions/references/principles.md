# Principles

Use these principles for decisions that the rules do not cover, and to review a design.\
When you use one, name it, so that the user can see the reason.

1. The principles of the project in `docs/conventions/design.md` have priority over this file ([`design-brief.md`](design-brief.md)).
2. When a principle does not agree with a rule, use the order in `SKILL.md`, section 1.

## Less, but better

Dieter Rams: "Weniger, aber besser."\
This is the first principle of this skill (`SKILL.md`, section 2).\
Remove what does not help a main task, then make what remains better.

Rams gives ten principles. Good design:

1. Is innovative.
2. Makes a product useful.
3. Is aesthetic.
4. Makes a product understandable.
5. Is unobtrusive.
6. Is honest.
7. Is long-lasting.
8. Is thorough down to the last detail.
9. Is environmentally friendly.
10. Is as little design as possible.

## Usability heuristics

Jakob Nielsen gives ten heuristics.\
Use them as the checklist of each design review, and name the heuristic in each finding.

1. Visibility of system status.
2. Match between the system and the real world.
3. User control and freedom.
4. Consistency and standards.
5. Error prevention.
6. Recognition rather than recall.
7. Flexibility and efficiency of use.
8. Aesthetic and minimalist design.
9. Help users recognize, diagnose, and recover from errors.
10. Help and documentation.

## Interaction principles

Don Norman, "The Design of Everyday Things":

| Principle | What it means |
| --- | --- |
| Affordance | What the user can do with an element |
| Signifier | The visible sign that tells the user what to do, for example a button shape |
| Mapping | The relation between a control and its result, for example a slider and a volume |
| Constraint | A limit that stops a wrong action |
| Feedback | The result of each action is shown immediately |
| Conceptual model | The model of the system that the user makes from the UI |

## Gestalt principles

The eye groups elements by these principles.\
Use them for layout and grouping ([`layout.md`](layout.md)).

| Principle | The eye groups elements that |
| --- | --- |
| Proximity | Are near each other |
| Similarity | Have the same shape, color, or size |
| Common region | Are in the same area with a border or a background |
| Continuity | Are on a line or a curve |
| Closure | Make an incomplete shape that the eye completes |
| Figure and ground | Are in front of a background |
| Common fate | Move together |
| Uniform connectedness | Are connected by a line |

## Laws of UX

Jon Yablonski collects these laws at lawsofux.com.

| Law | What it says | Apply it as |
| --- | --- | --- |
| Fitts's law | The time to reach a target depends on its distance and its size | Make frequent targets large, and put them near the last action |
| Hick's law | The time to decide increases with the number and the complexity of the choices | Give fewer choices, give a default, and show advanced options only on request |
| Jakob's law | Users spend most of their time in other products, and expect yours to work the same | Use the patterns of the platform and the base design system |
| Tesler's law | Each system has complexity that nobody can remove | Let the system carry the complexity, not the user, for example with smart defaults |
| Doherty threshold | Users work faster when the system responds in less than 400 ms | Respond in less than 400 ms, or show progress ([`components.md`](components.md)) |
| Aesthetic-usability effect | Users think that attractive designs are easier to use | Make the design attractive, but test its usability, because the look can hide problems |
| Miller's law | Working memory holds about 7 (± 2) items | Group information into chunks. Do not use the number as a limit for menus |
| Postel's law | Accept much, and send exactly | Accept the different forms of an input, and show one clear form |
| Peak-end rule | Users judge an experience by its strongest moment and its end | Design the end of a flow and its errors with care |
| Von Restorff effect | Users remember the item that is different | Make only the most important item different, for example the primary action |
| Serial position effect | Users remember the first and the last items best | Put important items at the start and the end of a list |
| Goal-gradient effect | Users work harder when they are near a goal | Show the progress in flows with steps |

## Other principle sets

| Name | Author | Main idea |
| --- | --- | --- |
| Eight golden rules of interface design | Ben Shneiderman | Consistency, universal usability, informative feedback, dialogs that close, error prevention, easy reversal, user control, less short-term memory load |
| Government design principles (selected) | GOV.UK | Start with user needs, do less, do the hard work to make it simple, be consistent but not uniform, this is for everyone |
| Don't make me think | Steve Krug | Each screen tells what it is and what to do, with no thought from the user |
| Calm technology | Mark Weiser and John Seely Brown | Technology informs without a demand for attention |
