---
title: "The AI Problem You Didn’t Know You Had - Excessive Agency (OWASP LLM Top 10)"
description: "Welcome to my series on OWASP LLM Security! Today, let's talk about understanding and mitigating excessice agency in LLM applications."
date: 2025-03-14T11:30:03+00:00
weight: 995
cover:
  image: "/post/llm6.png"
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
---

# Excessive Agency in LLMs: When Giving Too Much Power Goes Wrong

**Description:**  
An LLM-based system is often granted a degree of agency by its developer the ability to call functions or interface with other systems via extensions (sometimes referred to as tools, skills, or plugins by different vendors) to undertake actions in response to a prompt. The decision over which extension to invoke may also be delegated to an LLM 'agent' to dynamically determine based on input prompt or LLM output. Agent based systems will typically make repeated calls to an LLM using output from previous invocations to ground and direct subsequent invocations.

---

We all love our AI assistants, but sometimes they get a little too much freedom. Imagine giving your LLM (Language Learning Model) the power to not just answer questions but also access your bank account, change your passwords, and start an e-commerce business while you're asleep. Sounds like a bad movie, right? Welcome to the world of **Excessive Agency**, where LLMs have too much control and things can go south fast.

### **What’s the Big Deal with Excessive Agency?**

Imagine asking your assistant to write a 3-paragraph essay, but then, oops, it decides to delete your important files because you accidentally told it to. Excessive Agency happens when an LLM has too much power, often due to poorly engineered extensions (aka, AI plugins) that allow it to make dangerous decisions on its own. Triggered by things like hallucinations, prompt injections, or mischievous agents, it’s a hacker’s dream.

### **The Classic Oops Moments:**

1. **Too Many Tools**  
   You need your LLM to fetch documents, but it also has the power to delete them. What could go wrong? (Hint: everything.)
   
2. **The Forgotten Feature**  
   Remember that plugin you tried out but never used again? Yeah, it’s still there, waiting to ruin your day.
   
3. **Open-ended Permissions**  
   Your LLM extension is supposed to run a shell command to, say, list files. But, uh-oh, it can run _any_ shell command like, delete everything!
   
4. **Excessive Permissions**  
   Your LLM plugin is trying to read your emails but has full access to send, delete, and even post embarrassing selfies on your behalf. Yikes!

### **How to Avoid the Chaos (aka, Mitigation Strategies)**

So, how do you stop your LLM from going rogue and turning your digital life into a disaster movie? Here are some practical tips:

1. **Limit Extensions**  
   Only give your LLM what it absolutely needs no extra tools, no extra drama.
   
2. **Cut Down Functionality**  
   If your plugin doesn’t need to delete files, _don’t let it_. Stick to what’s necessary.
   
3. **Avoid Open-ended Extensions**  
   If you want your LLM to write files, let it _only_ write files not run shell commands, delete docs, or start a random YouTube channel.
   
4. **Tighten Permissions**  
   Give extensions the least amount of power. If it only needs to read, don’t let it write, update, or delete.
   
5. **Make Humans the Boss**  
   Let the user approve high-impact actions. Your LLM may be smart, but it still needs a little help from humans.
   
6. **Sanitize Everything**  
   Always double-check what you feed to the LLM and what it spits out. Malicious input can turn your AI buddy into a villain faster than you can say "prompt injection."

### **Bottom Line: Keep Your AI in Check!**

LLMs are cool, but let’s not let them go full "Skynet" on us. By minimizing permissions, limiting extensions, and keeping a human in the loop, you can avoid the chaos of **Excessive Agency** and make sure your LLM stays a helpful assistant, not a rogue agent.