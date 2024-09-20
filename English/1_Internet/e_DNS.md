# What is DNS?

Imagine the Internet as a large city, and domain names (like `google.com`) are like house addresses. The **DNS** (Domain Name System) acts as a phone book that converts these "easy-to-remember" addresses into IP addresses, which are like the exact coordinates of houses. So, instead of memorizing the coordinates (like `192.168.1.1`), you just need to remember the street name (like `google.com`), and DNS handles the translation.

When you type `example.com` in your browser, DNS translates that name to an IP address so you can access the correct website, just as if you were asking a GPS to take you to a specific address.

---

## How does DNS work?

The DNS process is like sending a messenger to look for an address. Several steps and players are involved to ensure you reach the correct site.

### DNS Resolution Components:

1. **DNS Recursor (The Librarian)**:  
   It’s the "messenger" that receives your request and searches in various "libraries" until it finds the information you need. When you type `example.com`, the recursor takes that request and queries different servers until it finds the associated IP address.

2. **Root Name Server (The Library Index)**:  
   The root server is like a library's index. It doesn’t have the complete information, but it tells you which shelf or section to look in for what you need. In this case, it directs you to where to find the top-level domain (TLD) server.

3. **TLD Name Server (The Library Shelf)**:  
   This server is like a specific bookshelf in the library. If you're looking for a book in the "Fiction" section, the TLD server will guide you to the location where the ".com" domain, for example, is found.

4. **Authoritative Name Server (The Dictionary)**:  
   Finally, this server is like a dictionary that translates "example.com" into its exact IP address. It's the server with the "definitive answer," returning the IP address to the recursor, who then delivers it to you.

---

## Differences between Recursive DNS Resolver and Authoritative DNS Server

- **Recursive DNS Resolver (The Messenger)**:  
  This server does the searching, requesting information from other servers until it gets the final answer.

- **Authoritative DNS Server (The Dictionary)**:  
  This is the server that stores the definitive information, meaning the correct IP address for the domain you requested.

### Example of a DNS lookup:

1. You type `example.com` in your browser.
2. Your computer sends that request to the **DNS recursor**.
3. The recursor first asks the **root server** to find out where to locate the ".com" domain's server.
4. The root server responds with the location of the **TLD server** that handles ".com".
5. The recursor queries the TLD server and asks for the IP address of `example.com`.
6. The TLD server responds with the address of the **authoritative server** for `example.com`.
7. The recursor asks the authoritative server for the exact IP address.
8. The authoritative server responds with the IP address for `example.com`, and the recursor delivers it to you, allowing your browser to load the website.

---

## Types of DNS queries

- **Recursive Query**:  
  Like asking someone to do all the work for you and not giving any answer until they find the exact address.

- **Iterative Query**:  
  Like when someone gives you a clue but leaves part of the work to you. If they don't have the answer, they tell you where else to ask.

- **Non-Recursive Query**:  
  This happens when you already have the answer stored in your "memory" (cache) and don't need to search further.

---

## What is DNS caching?

Caching is like saving the address of a place you frequently visit in your contact book. If you already know where `example.com` is, you don't need to ask again, making your journey (or the page load) much faster.

### Places where cache is stored:

1. **In the browser**:  
   Your browser saves the information of sites you've already visited.

2. **In your operating system**:  
   If it's not in the browser, your computer has a place where it stores DNS information.

3. **On DNS servers**:  
   The Internet servers themselves also store this information to avoid asking the same questions repeatedly.

In this way, the DNS system simplifies your browsing experience, making everything faster without needing to memorize complex IP addresses.

---

# What is DNS and how do DNS records work?

In this section, we will explore **DNS records** (Domain Name System), a fundamental aspect in managing websites and domains. If you're a web designer, work in IT, or manage websites, this article is for you.

## What is DNS?

The **DNS** acts as the "phone book" of the Internet. Just as you look up a number in a phone book to call someone, when you type a domain (like `google.com`) into your browser, DNS looks up the IP address of the server where that website is hosted.

### Analogy: The phone book

Imagine you want to call your friend John. You don’t remember his number by heart, so you look it up in a phone book. DNS does exactly that: it translates a friendly name like `google.com` into an IP address (like `172.217.0.0`).

---

## What are DNS records?

**DNS records** are like the entries in that phone book. For each domain, there are several records that indicate different aspects of that domain, like where the website or email is located.

### Most important types of DNS records

- **NS Record (Name Server)**:  
  This is the server where all the DNS records for your domain live.

  - **Analogy**:  
    The NS record is like a post office managing all navigation and email requests.

- **A Record (Address Record)**:  
  Links your domain to the IP address of the server where your website is hosted.

  - **Analogy**:  
    The A record is like the postal address of a physical place.

- **MX Record (Mail Exchange)**:  
  Manages where emails for your domain are directed.

  - **Analogy**:  
    The MX record is like a mailman delivering the mail to the correct address.

- **CNAME Record (Canonical Name)**:  
  Redirects a subdomain to another domain.

  - **Analogy**:  
    A CNAME is like a nickname, where even if you refer to "Johnny," everyone knows you're talking about "John."

---

## Useful tools for managing your DNS

- **[MX Toolbox](https://mxtoolbox.com)**:  
  Allows you to look up DNS records for any domain and verify everything is in order.

### Tip: Test before changing

It's always a good idea to launch your website and test that everything works before changing your DNS records.

---

# DNS Basics and Email

Imagine you have a restaurant and need different addresses so people can find you. **DNS records** work similarly, helping direct visitors to the correct parts of your website or service.

---

## What are CNAME records?

**CNAME records** function like a sign directing visitors where to go.

- **Technical Example**:  
  If you set up `mail.yourdomain.com`, you can use a CNAME to redirect that subdomain to another domain or service, like Exchange.

### The wildcard of CNAME records

You can use a **wildcard** (*) to redirect unknown subdomains to your domain's main page.

---

## What are TXT records?

**TXT records** are like notes or additional instructions left by domain owners.

- **Technical Example**:  
  A **TXT** record might say `v=spf1 include:mail.yourdomain.com`, meaning that domain is authorized to send emails.

---

## Mistakes to avoid

A common mistake is not having all the DNS records ready before changing providers. It's like moving your restaurant without taking the signs that show where each important area is located.