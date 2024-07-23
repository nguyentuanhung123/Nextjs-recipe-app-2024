This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.js`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

### Các bước chuẩn bị

- B1: Xóa toàn bộ thẻ main trong Home
- B2: Ở global.css xóa toàn bộ css trong thẻ body

### Shadcn : https://ui.shadcn.com/docs/installation/next

- B1: npx shadcn-ui@latest init
- B2: Chọn Default -> Slate -> yes (Nếu tự động thêm được 2 thư mục là components và lib trong thư mục src là thành công)

## Skeleton : https://ui.shadcn.com/docs/components/skeleton

- B1: npx shadcn-ui@latest add skeleton
- B2: Sử dụng trong file loading.js

```jsx
import { Skeleton } from "@/components/ui/skeleton";

export default function Loading() {
    return <div className="w-full min-h-screen">
        <Skeleton />
    </div>
}

```

### Sử dụng Card trong shadcn/ui

- B1: npx shadcn-ui@latest add card

- B2: Import 

```jsx
import {
    Card,
    CardContent,
    CardDescription,
    CardFooter,
    CardHeader,
    CardTitle,
  } from "@/components/ui/card"
```

- B3: Áp dụng

```jsx
<div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
    {
        recipeList && recipeList.length > 0 ?
            recipeList.map((recipe) => <Link key={recipe.id} href={`/recipe-list/${recipe.id}`}>
                <Card>
                    <CardContent className="bg-white rounded-md overflow-hidden shadow-md cursor-pointer hover:scale-[1transiaiton-all">
                        <div className="w-full aspect-w-16 aspect-h-8 lg:h-80">
                            <img 
                                src={recipe.image}
                                alt={recipe.name}
                                className="w-full h-full object-cover object-top"
                            />
                        </div>
                    </CardContent>
                </Card>
            </Link>)
        : null
    }
</div>
```

## Giải thích các css trong Card

- Thẻ Card chính là thẻ div có các css là: 

```jsx
<div className="rounded-lg border bg-card text-card-foreground shadow-sm"></div>
```
- Thẻ CardContent ngoài các css được định nghĩa thêm có thêm các css là: 

```jsx
<div className="p-6 pt-0"></div>
```

