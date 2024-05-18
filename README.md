[Check Out the Audoly Public Web App](https://www.audoly.com)

```
Note: The code really has to be private, but I wanted to share how
I structured the project and why I made certain decisions! I can
always show you the code if you're interested 😊
```

# 🎵 Audoly: Playlisting and Music Intelligence Platform

Audoly is a music intelligence platform designed to assist artists and producers in getting their music discovered, playlisted, and charted. The primary tool currently is a Spotify playlist search engine that allows users to search for playlists based on specific criteria and retrieve relevant playlist information, including the playlist creator's contact details.

## 🛠️ Key Features

Audoly includes the following core features:

| Feature                     | Description                                                                                                                                                        |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Spotify Playlist Search** | Users can search for playlists on Spotify based on specific criteria and retrieve relevant playlist information, including the playlist creator's contact details. |
| **User Authentication**     | Secure user authentication using NextAuth, integrating Google and Spotify accounts.                                                                                |
| **Subscription Management** | Stripe integration allows users to upgrade to premium subscriptions for enhanced features and unlimited credits.                                                   |
| **User Profile**            | Users can manage their profile information, subscription details, and track their usage statistics.                                                                |

## 🧩 Technical Implementation

Audoly is built using the following technologies:

- **Next.js**: Utilized for server-side rendering and efficient route management, enhancing performance and search engine optimization. The file-based routing system facilitated straightforward route creation and management.

- **TypeScript**: Employed across the codebase to improve code quality and maintainability through static typing. Interfaces and types were used to ensure clear documentation and robust code.

- **Tailwind CSS**: Applied for rapid UI development with its utility-first approach, enabling consistent styling and promoting component reusability while maintaining a minimal CSS bundle size.

- **DynamoDB**: Chosen for its scalability and performance to store user data and authentication information, supporting flexible data modeling and seamless application integration.

- **Stripe**: Integrated for subscription management and payment processing, leveraging its APIs for secure payment handling and efficient billing processes.

- **Spotify Web API**: Used to fetch detailed playlist data, enabling users to access comprehensive music-related information directly from Spotify.

- **Vercel**: Deployed on Vercel for streamlined deployment and automatic scaling, ensuring high availability and performance through its serverless functions.

## 🌐 Deployment and Monitoring

To maintain optimal performance and gain insights into user behavior, Audoly employs:

- **Google Analytics**: Implemented to track user interactions and page views, providing data to inform user behavior analysis and decision-making processes.
- **Microsoft Clarity**: Utilized for session recording and heatmap analysis to identify areas for UI improvements, enhancing user interaction understanding and guiding interface optimizations.

## Project Structure

The project is organized to promote maintainability and scalability:

- The `app` directory contains the main application components and pages.
- The `components` directory houses reusable UI components.
- The `lib` directory includes utility functions and helper modules.
- The `public` directory stores static assets.
- The `cdk` directory contains the AWS Cloud Development Kit (CDK) infrastructure code for DynamoDB table creation.

## 🌟 Conclusion

Audoly is a robust platform developed using Next.js, TypeScript, and various third-party services to support musicians in their careers. Its scalable architecture and thoughtful design ensure it meets the needs of a growing user base while providing valuable insights through data analytics.

For any further information or inquiries about Audoly, please reach out to the team. 🎧🎵

## 📁 Full Project Structure

```
📂 audoly/
├── 📂 @types/
│   └── 📄 next-auth.d.ts
├── 📂 app/
│   ├── 📂 api/
│   │   ├── 📂 auth/
│   │   │   └── 📂 [...nextauth]/
│   │   │       ├── 📄 authoptions.ts
│   │   │       └── 📄 route.ts
│   │   ├── 📄 dynamodb.tsx
│   │   ├── 📂 spotify/
│   │   │   ├── 📂 search/
│   │   │   │   └── 📄 route.ts
│   │   │   └── 📄 spotify.tsx
│   │   ├── 📂 stripe/
│   │   │   ├── 📂 createcheckoutsession/
│   │   │   │   └── 📄 route.ts
│   │   │   ├── 📂 getbillingportal/
│   │   │   │   └── 📄 route.ts
│   │   │   ├── 📂 subscriptionWebhook/
│   │   │   │   └── 📄 route.ts
│   │   │   └── 📄 types.ts
│   │   └── 📂 user/
│   │       ├── 📄 route.ts
│   │       └── 📂 updatename/
│   │           └── 📄 route.ts
│   ├── 📂 contact/
│   │   ├── 📄 layout.tsx
│   │   └── 📄 page.tsx
│   ├── 📂 dashboard/
│   │   ├── 📄 layout.tsx
│   │   ├── 📄 page.tsx
│   │   └── 📂 spotifyplaylistsearch/
│   │       ├── 📄 layout.tsx
│   │       ├── 📄 page.tsx
│   │       └── 📂 [query]/
│   │           └── 📂 [market]/
│   │               └── 📂 [magicsearch]/
│   │                   └── 📂 [offset]/
│   │                       ├── 📄 loading.tsx
│   │                       └── 📄 page.tsx
│   ├── 📂 (homepage)/
│   │   ├── 📄 layout.tsx
│   │   └── 📄 page.tsx
│   ├── 📄 layout.tsx
│   ├── 📂 login/
│   │   ├── 📄 layout.tsx
│   │   └── 📄 page.tsx
│   ├── 📂 privacypolicy/
│   │   ├── 📄 layout.tsx
│   │   └── 📄 page.tsx
│   ├── 📂 profile/
│   │   ├── 📂 billing/
│   │   │   ├── 📄 loading.tsx
│   │   │   └── 📄 page.tsx
│   │   ├── 📄 layout.tsx
│   │   └── 📂 myinformation/
│   │       └── 📄 page.tsx
│   ├── 📂 success/
│   │   ├── 📄 layout.tsx
│   │   └── 📄 page.tsx
│   └── 📂 termsofservice/
│       ├── 📄 layout.tsx
│       └── 📄 page.tsx
├── 📂 cdk/
│   ├── 📂 bin/
│   │   └── 📄 cdk.ts
│   ├── 📄 cdk.json
│   ├── 📂 cdk.out/
│   │   ├── 📄 cdk.out
│   │   ├── 📄 DynamoDBStack.assets.json
│   │   ├── 📄 DynamoDBStack.template.json
│   │   ├── 📄 manifest.json
│   │   └── 📄 tree.json
│   ├── 📄 jest.config.js
│   ├── 📂 lib/
│   │   └── 📄 dynamodb-stack.ts
│   ├── 📄 package.json
│   ├── 📄 README.md
│   ├── 📂 test/
│   │   └── 📄 cdk.test.ts
│   ├── 📄 tsconfig.json
│   └── 📄 yarn.lock
├── 📂 components/
│   ├── 📂 custom/
│   │   ├── 📂 buttons/
│   │   │   ├── 📄 dynamic-redirect-button.tsx
│   │   │   └── 📄 static-redirect-button.tsx
│   │   ├── 📂 cards/
│   │   │   └── 📄 upgrade-card.tsx
│   │   ├── 📄 center-column.tsx
│   │   ├── 📄 login-signup.tsx
│   │   ├── 📂 pages/
│   │   │   ├── 📂 dashboard/
│   │   │   │   ├── 📄 credit-counter.tsx
│   │   │   │   ├── 📄 dashboard-redirect.tsx
│   │   │   │   └── 📂 spotifyplaylistsearch/
│   │   │   │       ├── 📄 pagination-controls.tsx
│   │   │   │       ├── 📄 playlist-table.tsx
│   │   │   │       ├── 📄 search-form.tsx
│   │   │   │       └── 📄 search-helpers.ts
│   │   │   ├── 📂 login/
│   │   │   │   ├── 📄 login-buttons.tsx
│   │   │   │   └── 📄 login-redirect.tsx
│   │   │   ├── 📂 profile/
│   │   │   │   └── 📄 profile-sidebar.tsx
│   │   │   └── 📂 tl_layout/
│   │   │       ├── 📄 footer.tsx
│   │   │       ├── 📄 mode-toggle.tsx
│   │   │       ├── 📄 nav-bar.tsx
│   │   │       ├── 📄 next-auth-provider.tsx
│   │   │       ├── 📄 side-navigation.tsx
│   │   │       ├── 📄 theme-provider.tsx
│   │   │       └── 📄 top-navigation.tsx
│   │   └── 📄 scroll-to.tsx
│   └── 📂 ui/
│       ├── 📄 accordion.tsx
│       ├── 📄 alert-dialog.tsx
│       ├── 📄 badge.tsx
│       ├── 📄 button.tsx
│       ├── 📄 card.tsx
│       ├── 📄 command.tsx
│       ├── 📄 dialog.tsx
│       ├── 📄 dropdown-menu.tsx
│       ├── 📄 input.tsx
│       ├── 📄 label.tsx
│       ├── 📄 navigation-menu.tsx
│       ├── 📄 pagination.tsx
│       ├── 📄 popover.tsx
│       ├── 📄 scroll-area.tsx
│       ├── 📄 select.tsx
│       ├── 📄 separator.tsx
│       ├── 📄 sheet.tsx
│       ├── 📄 skeleton.tsx
│       ├── 📄 table.tsx
│       ├── 📄 textarea.tsx
│       ├── 📄 toast.tsx
│       ├── 📄 toaster.tsx
│       └── 📄 use-toast.ts
├── 📄 components.json
├── 📄 DISPLAY.md
├── 📂 lib/
│   └── 📄 utils.ts
├── 📄 next.config.mjs
├── 📄 next-env.d.ts
├── 📄 package.json
├── 📄 postcss.config.mjs
├── 📂 public/
│   ├── 📄 favicon.png
│   ├── 📄 googlefc25c951d7703d50.html
│   ├── 📂 pngs/
│   │   ├── 📄 auth-portrait.png
│   │   └── 📄 spotify-album-cover.png
│   ├── 📂 screenshots/
│   │   ├── 📄 audoly-screenshot-0.png
│   │   ├── 📄 audoly-screenshot-1.png
│   │   └── 📄 audoly-screenshot-2.png
│   └── 📂 svgs/
│       ├── 📄 google-logo.svg
│       └── 📄 spotify-logo.svg
├── 📄 README.md
├── 📂 styles/
│   └── 📄 globals.css
├── 📄 tailwind.config.ts
├── 📄 tsconfig.json
└── 📄 yarn.lock
```
