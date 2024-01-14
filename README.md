Next.js Commerce
A Next.js ^13.4.19

Next.js App Router
Optimized for SEO using Next.js's Metadata
React Server Components (RSCs) and Suspense
Server Actions for mutations
Edge Runtime
New fetching and caching paradigms
Dynamic OG images
Styling with Tailwind CSS
Note

Important Feature

Pagination
Fetch product by query
Automatic light/dark mode based on system settings
Checkout and payments with stripe
Running locally
You will need to use the environment variables defined in .env.example to run Next.js Commerce. It's recommended you use Vercel Environment Variables for this, but a .env file is all that is necessary.

npm install

npm run dev

How to use tokens?
Using permanent token:
// install client: yarn add boundless-api-client

import {BoundlessClient} from 'boundless-api-client';
const apiClient = new BoundlessClient('<YOUR PERMANENT TOKEN>');
apiClient.setInstanceId('<YOUR INSTANCE ID>');

//fetch products:
apiClient.catalog.getProducts().then(data => console.log(data));
Generate token (for server-side requests - more secure way):
// install client: yarn add boundless-api-client jsonwebtoken

import {BoundlessClient} from 'boundless-api-client';
import {generateBoundlessToken} from 'boundless-api-client/token';

const token = generateBoundlessToken('<YOUR CLIENT ID>', '<YOUR SECRET>', '<YOUR INSTANCE ID>');
const apiClient = new BoundlessClient(token);
apiClient.setInstanceId('<YOUR INSTANCE ID>');

//fetch products:
apiClient.catalog.getProducts().then(data => console.log(data));
