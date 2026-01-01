# GEMINI.md - Project Context

## Project Overview
This project, **"koreanfood"**, is a static site/blog built using **Astro**. It is based on the Astro Blog Starter Kit and is configured for high performance, SEO, and content management using Markdown and MDX.

**Key Technologies:**
- **Framework:** [Astro](https://astro.build/) (v5.x)
- **Content:** Markdown (`.md`) and MDX (`.mdx`) via Content Collections.
- **Integrations:**
    - `@astrojs/mdx`: For writing interactive content.
    - `@astrojs/rss`: For generating an RSS feed.
    - `@astrojs/sitemap`: For generating a sitemap.
- **Language:** TypeScript (Strict mode enabled).
- **Styling:** Global CSS (`src/styles/global.css`) with minimal initial styling.

## Directory Structure
- **`src/pages/`**: Route definitions.
    - `index.astro`: The homepage.
    - `blog/[...slug].astro`: Dynamic route for blog posts.
    - `rss.xml.js`: Generates the RSS feed.
- **`src/content/`**: Content collections.
    - `blog/`: Contains the actual blog post files (`.md` and `.mdx`).
- **`src/components/`**: Reusable UI components (Header, Footer, Head, etc.).
- **`src/layouts/`**: Page layouts (e.g., `BlogPost.astro`).
- **`src/consts.ts`**: Global constants for Site Title and Description.
- **`public/`**: Static assets (fonts, images, favicon).
- **`astro.config.mjs`**: Main Astro configuration file.

## Building and Running
The project uses `npm` for dependency management and task execution.

| Command | Description |
| :--- | :--- |
| `npm install` | Install project dependencies. |
| `npm run dev` | Start the local development server (usually at `http://localhost:4321`). |
| `npm run build` | Build the project for production (outputs to `dist/`). |
| `npm run preview` | Preview the production build locally. |
| `npm run astro check` | Run diagnostics and type checking. |

## Development Conventions
- **Content:** Blog posts are added to `src/content/blog/`. Frontmatter schema is likely defined in `src/content.config.ts`.
- **Components:** New components should be placed in `src/components/` and imported into pages or layouts.
- **Styling:** Global styles are managed in `src/styles/global.css`. Component-scoped styling is available via Astro's `<style>` tag.
- **Configuration:** Modify `src/consts.ts` to update the Site Title and Description globally.
- **Routing:** File-based routing is used. To add a new page, create a `.astro` or `.md` file in `src/pages/`.

## Important Files
- `astro.config.mjs`: Configuration for integrations and build options.
- `package.json`: Dependencies and scripts.
- `src/consts.ts`: Site metadata constants.
- `src/content.config.ts`: (Assumed) Configuration for content collections and schemas.

## 블로그 운영 가이드라인 (Blog Operations)

### 1. 운영 목적 및 방향성
- **주제:** 일식 (Japanese Food) 및 관련 음식 문화.
- **목표:** 수익화 블로그 (SEO 최적화 및 체류시간 증대).
- **전략:** 매번 새로운 주제 선정, 깊이 있는 정보 제공.

### 2. 콘텐츠 작성 규칙 (SEO & 품질)
- **분량:** 최소 **5,000자 이상** (단순 나열이 아닌 풍부한 서사, 팁, 유래, 레시피 등을 포함하여 깊이 있게 작성).
- **SEO (검색엔진 최적화):**
    - 검색 의도에 맞는 키워드 자연스럽게 배치.
    - 구조화된 헤더 (`##`, `###`) 사용.
    - 매력적인 Meta Description 작성.
- **톤앤매너:**
    - AI 느낌이 나지 않는, **자연스럽고 감성적인 휴먼 터치**.
    - 독자에게 친근하게 말을 건네는 듯한 대화체.
    - 전문성과 개인적인 견해/경험이 섞인 듯한 서술.
- **이미지:**
    - Unsplash 이미지를 반드시 **1개 이상** 삽입.
    - 문법: `![Alt Text](https://source.unsplash.com/featured/?keyword)` (키워드는 주제에 맞게 영문으로 설정).

### 3. "새글 작성" 워크플로우
사용자가 **"새글 작성"**이라고 명령할 경우, 별도의 질의 없이 즉시 다음 절차를 수행한다.

1.  **주제 선정:** 기존 포스트와 중복되지 않는 흥미로운 일식 주제 자동 선정.
2.  **파일 생성:** `src/content/blog/` 경로에 `.md` 파일 생성.
    - 파일명: `english-slug.md` (예: `sushi-guide.md`)
3.  **Frontmatter 작성:**
    ```yaml
    ---
    title: "클릭을 부르는 한글 제목"
    description: "SEO를 고려한 매력적인 요약문"
    pubDate: "YYYY-MM-DD"
    heroImage: "https://source.unsplash.com/featured/?japanese-food,main-ingredient"
    ---
    ```
4.  **본문 작성:** 위 콘텐츠 작성 규칙(5000자 이상, 자연스러운 말투, 이미지 포함)을 준수하여 작성.

