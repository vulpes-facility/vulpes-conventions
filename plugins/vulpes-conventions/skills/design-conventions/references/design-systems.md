# Design systems

A base design system gives the tokens, the components, the patterns, and the guidelines of a product.\
Each product has one base design system.\
The product changes its tokens for the brand, and adds what the base does not have.

A component library or a CSS framework is not a design system.\
It gives code, but no design guidelines.

## Selection

1. When the project names a base design system, use it.\
   When it does not, ask the user to select one before you design screens.\
   Recommend one by the order in rule 2, and tell the reason.\
   Use the selection of the user.
2. Select by the first case in this list that applies to the product:\
   a. The app runs in a host product: use the design system of the host.\
   b. The product is a service of a government: use the design system of that government, when it has one.\
   c. The app is a native app for one platform: use the guideline of that platform.\
   d. All other products: select by the kind of product in the table, or make a custom design system on [`tokens.md`](tokens.md).
3. Write the selected design system and its major version in `docs/conventions/design.md`.
4. Before you select a design system, read its license and the licenses of its fonts and icons.\
   Some design systems allow use only in apps for their own product.\
   Do not use the logos or the brand names of the owner in the product.

| Design system | Owner | Platforms | Select it for |
| --- | --- | --- | --- |
| Apple HIG | Apple | iOS, iPadOS, macOS, watchOS, visionOS | Native apps for Apple platforms |
| Material 3 | Google | Android, web, and apps on more than one platform | Android apps, and apps with one look on all platforms |
| Fluent 2 | Microsoft | Windows, web, iOS, Android | Windows apps, productivity apps, and apps in Microsoft Teams or Microsoft 365 |
| GNOME HIG | GNOME | Linux | Apps for the GNOME desktop |
| IBM Carbon | IBM | Web | Enterprise products, data-heavy screens, and admin consoles |
| Adobe Spectrum | Adobe | Web | Creative tools and editors with dense controls |
| Primer | GitHub | Web | Developer tools, and apps for GitHub |
| Ant Design | Ant Group | Web | Back-office and admin web apps |
| Atlassian Design System | Atlassian | Web | Apps for Jira, Confluence, and other Atlassian products |
| Shopify Polaris | Shopify | Web | Apps in the Shopify admin |
| Salesforce Lightning Design System | Salesforce | Web | Apps in Salesforce |
| KRDS | Ministry of the Interior and Safety, Korea | Web | Services of the Korean government and public institutions |
| GOV.UK Design System | Government Digital Service, UK | Web | Services of the UK government |
| USWDS | General Services Administration, US | Web | Services of the US federal government |

A consumer product with its own brand often fits no row.\
For it, recommend a custom design system (see Custom design system).\
When a different design system fits the product better, the user MAY select it.\
Apply the rules of this file to it.

## Use

1. Use the components of the base design system.\
   Do not make a second component for the same work.
2. Do not mix the components of two design systems in one app.
3. Change the look for the brand only with the theming of the base design system: color, type, radius, and similar tokens.\
   Do not change the anatomy or the behavior of its components.
4. Check the contrast of each changed color again ([`color.md`](color.md)).
5. A case can have no rule in the base design system, or two rules that do not agree.\
   Then use the order of priority in `SKILL.md`, section 1.
6. Use the version of the design system that the project names.\
   To change to a new major version, use its migration guide.

## Custom design system

1. Make a custom design system only when no design system in the table fits the product, or when the user asks for one.
2. Start with the tokens ([`tokens.md`](tokens.md)), then the type scale, then the components.
3. Use the platform guidelines for the behavior of each component.
4. Write the accessible behavior of each component in its spec ([`components.md`](components.md)).

## Native platforms

1. On a native platform, the base design system gives the look: tokens, type, icons, and images.\
   The guideline of the platform gives the behavior (`SKILL.md`, section 1).
2. When the base design system has no components for a platform, use the native controls of the platform.\
   Give them the tokens of the base design system.\
   For example, an iOS app on IBM Carbon uses the native iOS controls.\
   It gives them the Carbon colors, IBM Plex, and the Carbon icons.
3. [`platforms.md`](platforms.md) gives the rules for apps on more than one platform.
