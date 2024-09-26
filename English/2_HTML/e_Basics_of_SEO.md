# SEO Starter Guide

When you created your website, you likely did so with your users' convenience in mind, aiming to make it easy for them to search and explore your content. One of those users is a search engine, which helps others discover your content. SEO (Search Engine Optimization) is about helping search engines understand your content and making it easier for users to find your site and decide whether to visit it through a search engine.

## How Google Search Works

Imagine Google as a great librarian who constantly roams a massive library looking for new books and articles. Instead of reading each book, Google uses "crawlers" (bots) that examine every corner of the web to find new pages and add them to its gigantic index. Just as a librarian categorizes books, Google categorizes and organizes pages so users can find them easily.

### What to Do if Google Can't Find Your Site

If Google can't find your site, it's like the librarian not knowing your book exists. Before making major changes, check if your site is already indexed using the `site:` search operator. For example, if you search for `site:yourwebsite.com`, and see results, it means Google has found your site. If you don't see results, there might be technical issues preventing Google from accessing your content.

## How Google Sees Your Page

Think of Google as a visitor in your store. If your store is messy and important items are hidden, the visitor (or in this case, Google's bot) might not find what they're looking for. Ensure that your content is accessible to Google in the same way it is to users. Use tools like the URL Inspection Tool in Search Console to check how Google sees your page.

### Avoid Hiding Important Elements

If important parts of your site, such as styles (CSS) or functionalities (JavaScript), are hidden or load slowly, Google might have trouble understanding your site's content. Ensure that all necessary elements are available to crawlers.

## How to Block Access to Certain Pages

Sometimes, you might want certain parts of your site not to appear in search results, such as sensitive information or temporary pages. It's like putting a "Do Not Enter" sign on certain areas of your store. You can do this using `robots.txt` files or `noindex` meta tags to indicate to search engines not to index those pages.

## Organize Your Site

Imagine your website as a well-organized library. If you group similar books in the same section (or directory), it will be easier for visitors (and Google) to find what they're looking for. A clear and logical structure helps search engines understand how pages relate to each other.

### Use Descriptive URLs

URLs are like signs on the shelves in your library. Descriptive URLs help users and Google understand the content of the page before clicking on it. For example, `https://www.example.com/pets/cats.html` is more informative than `https://www.example.com/2/6772756D707920636174`.

## Group Similar Topic Pages

If you have many pages on your site, grouping them into thematic directories can help Google understand how sections of your site are organized. For example, `https://www.example.com/policies/return-policy.html` vs. `https://www.example.com/promotions/new-promos.html`. Google will crawl pages in high-frequency directories more regularly.

## Reduce Duplicate Content

Duplicate content is like having multiple copies of the same book in a library, which can confuse visitors. Use redirects or `rel="canonical"` tags to tell Google which version of the content is the primary one, thus avoiding wasting resources on duplicate pages.

## Make Your Site Interesting and Useful

The content on your site should be like a good book: engaging, well-written, and relevant. Ensure that the text is easy to read, well-organized, and up-to-date. Creating unique and useful content is the best way to attract users and improve your search rankings.

### Think About Search Terms

Imagine your users as readers looking for books. They might use different terms to describe the same topic. For example, "charcuterie" and "cheese platter". Anticipating these variations in search behavior and using related terms in your content can help improve your visibility in search results.

## Avoid Annoying Ads

Ads should be like shelves in a bookstore: visible but not intrusive. Excessive ads or interstitials that block content can frustrate users. Maintain a smooth user experience to prevent ads from being too distracting.

## Build Links to Relevant Resources

Links are like recommendations from other librarians about which books to read. Internal links help connect different parts of your site, while external links can add credibility. Ensure that links are relevant and high-quality.

### Write Quality Anchor Text

The anchor text of a link should be informative, like a clear chapter title in a book. This helps users and search engines understand what the linked page is about before clicking on it.

### Build Links When Necessary

Links should add value and context to your content. If you link to external pages, ensure they are reliable resources. Use the `nofollow` attribute if you don’t want search engines to consider those links for your page's ranking.

## Influence How Your Site Appears in Google Search

When thinking about how Google displays your site in search results, imagine you are setting up a storefront display for your store. The display is the first impression customers get of your business. In this section, we will focus on two key elements: the title link and the snippet, which are like the signs and descriptions in your storefront display.

### Influence Title Links

The title link is like the sign for your store in the display window. This sign should be clear, attractive, and tell people what your store is about. In web development terms, the title link is generated from the content within the `<title>` tag in the HTML, as well as from other headings on the page.

**Analogy:** Think of `<title>` as the name of your store and headings as promotional signs you place around. A good title should be unique, clear, and descriptive. For example, if you have a bakery, a good title might be "Ana's Bakery - Artisan Cakes in Buenos Aires."

If you use a CMS (Content Management System), like WordPress, this system often handles the `<title>` tag automatically for you. Just make sure the title you write is attractive and relevant.

### How to Control Snippets

The search snippet is like the text on a business card you place in your display window. It's a brief description that helps visitors decide whether to enter your store. Google extracts this snippet from your page’s content or from the meta description tag in the HTML.

**Analogy:** Imagine the snippet as the message on a business card briefly describing what you offer. A good meta description is short, specific, and relevant to the page. For example, if your bakery offers a guide on making cupcakes, a good meta description might be: "Discover our complete guide to making delicious cupcakes, with easy-to-follow recipes and tips."

### Add and Optimize Images on Your Site

Images on your site are like the products in your store window. If you’re selling cakes, your photos should be attractive and clearly show the products you offer.

**Analogy:** Adding high-quality images near relevant text is like placing the most eye-catching products in the center of the window to attract customers. Ensure images are clear and accompanied by descriptions that help Google understand what each image is about.

**Alt Text:** Alt text is like a label that describes the product in the display window. It’s a brief text that explains what is shown in the image and is crucial for search engines to understand the content of your photos. Add it using the `alt` attribute in the `<img>` tag.

### Optimize Your Videos

If your site features videos, it’s like having a live demonstration in your store. Videos should be well-produced and accompanied by clear descriptions to attract visitors.

**Analogy:** Think of the video as a live demo of how to do something. Ensure that the video title and description are informative and relevant so that users and search engines understand the content of the video.

### Promote Your Site

Promoting your website is like advertising for your store. The more effectively you promote your store, the more visitors you will attract.

**Analogy:** You can use various methods to promote your store, such as social media, online advertising, and word of mouth. Each method has its role, but the most lasting is usually word of mouth, where satisfied customers recommend your store to others.

### Aspects We Believe You Should Not Focus On

As SEO evolves, some practices that used to be important no longer have the same impact. Here’s what you should not focus on:

- **Meta Keywords:** They are not used for ranking in Google.
- **Keyword Stuffing:** Overusing keywords can annoy users and is considered spammy.
- **Keywords in Domain Name or URL:** The domain name should be relevant to your business, but keywords themselves have less impact on ranking.
- **Content Length:** There is no magic number of words; quality is what matters.
- **Subdomains vs. Subdirectories:** Use the structure that best suits your business.
- **PageRank:** While important, Google uses many other factors to rank pages.
- **Duplicate Content:** Having content accessible from multiple URLs is not problematic, but copying content from others is a bad practice.
- **Number and Order of Headings:** Not crucial for ranking but useful for accessibility.
