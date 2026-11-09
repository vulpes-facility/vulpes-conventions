# Design systems

A base design system gives the tokens, the components, the patterns, and the guidelines of a product.\
Each product has one base design system, and changes its tokens for the brand.\
A component library or a CSS framework is not a design system, because it gives no design guidelines.

## Selection

1. When the project names no base design system, ask the user to select one before you design screens.\
   Recommend one, tell the reason, and use the selection of the user.
2. Recommend by the first case in this list that applies:\
   a. The app runs in a host product: the design system of the host.\
   b. The product is a service of a government: the design system of that government.\
   c. The app is a native app for one platform: the guideline of that platform.\
   d. A consumer product with its own brand: a custom design system.\
   e. All other products: select by the kind of product in the table.
3. Write the design system and its major version in `docs/conventions/design.md`.
4. Before you recommend a design system, read the licenses of the system, its fonts, and its icons.\
   Some allow use only in apps for their own product.

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

The user MAY select a design system that is not in the table.

## Use

1. Do not mix the components of two design systems in one app.
2. Change the look for the brand only with the theming of the base design system.\
   Do not change the anatomy or the behavior of its components.
3. Check the contrast of each changed color again ([`color.md`](color.md)).
4. To change to a new major version, use its migration guide.

## Custom design system

1. Start with the tokens ([`tokens.md`](tokens.md)), then the type scale, then the components.
2. Use the platform guidelines for the behavior of each component.
3. Write the accessible behavior of each component in its spec ([`components.md`](components.md)).

## Native platforms

1. On a native platform, the base design system gives the look, and the platform guideline gives the behavior (`SKILL.md`, section 1).
2. When the base design system has no components for a platform, use the native controls of the platform with its tokens.\
   For example, an iOS app on IBM Carbon uses the native iOS controls with the Carbon colors, IBM Plex, and the Carbon icons.
