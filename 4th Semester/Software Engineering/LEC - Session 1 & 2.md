# LEC - Session 1 & 2
Class: [[COMP6100001 - Software Engineering]]
Session: 1 & 2
Topics: Introduction to Software Engineering
Date: 2023-02-14
Lecturer: [[D6666 - RISMA YULISTIANI, S.Kom., M.Kom.]]

## AOL Stuff

- Bikin kelompok 3-5 orang
- Panduan ada di forum
- Pilih Tema
- Pertemuan ke 3 (Sesi 4 & 5) presentasi

# Software Engineering

Three critical differences between programming and software engineering: **time**, **scale**, and the **trade-offs** at play

Software engineering leans more towards development, modification, and maintenance. In other words, software engineer concerns more about scale and efficiency. Also creating policies and rules and also do maintenance and testing to produce high-quality and production ready software products.

# Time and Change

When we are developing a product, we need ot assume that the project will live indefinitely. We cannot predict when we won't need  to upgrade our dependencies, language versions, and so on.

Software is not a static entity rather a **dynamic** one that must evolve and adapt to changing user requirements, technological advancements, and business needs.

This enables software to be more **sustainable** and **valuable** asset to organizations, rather than a liability that becomes increasingly complex and costly to maintain over time.

# Life span and Importance of Upgrade

![[Pasted image 20230214121013.png]]

## What happens if not planning upgrades?

There are three main reasons, each of which compounds the others:

- Since we're performing a task that hasn't yet been done, hidden assumptions will arise.
- Engineers need to adapt or need to do more research regarding this transition, especially those with less experience
- Doing upgrades can be costly and might need years worth of upgrades instead of incremental upgrades.

And if we don't do upgrades there can create several issues such as:

- Security vulnerabilities
- Technical debt
- Incompatibility
- Lack of support

# Project sustainability

Project sustainability refers to the ability of a project to continue delivering its intended benefit over time, beyond its initial implementation phase.

We usually achieve project sustanibility largely through trial and error as we gain more experience the less errors we face.

# Hyrum's Law

"With a sufficient number of users of an API, it does not matter what you promise in the contract: all observable behaviours of your system will be depended on by somebody"

# Scale and Efficiency

Scale is one important ability in your organization to create products that can handle an increasing amount of work without creating a negative impact in cost

Efficiency refers to the ability  to achieve goals with the least amount of resources possible, such as time, money, or energy.

# Factors that affect the flexibility of a codebase

**Expertise**
Know how to do. Example: have hundreds of compiler upgrades across many platforms

**Stability**
Less change between releases bby adopting releases more regularly

**Conformity**
Less code that hasn't been through an upgrade already

**Familiarity**
Because of the regularity, redudancies can be spotted easily in the process of performing an upgrade and attempt to automate

**Policy**
The net effect of these processes is that upgrades remain feasible because infrastructure teams do not need to worry about every unknown usage, only the ones that are visible in our CI systems.

# Trade-offs and Costs

Understand how to program, understand the lifetime of the maintained software, and understand how to maintain as scaling up with more engineers producing and maintaining new features.

Decisions impact **costs**

Cost can involve any or all of these facators:
- Financial costs: money
- Resource costs: CPU
- Personnel costs: Engineering effort
- Transaction costs: What does it cost to take action?
- Opportunity costs: What does it cost to not take action?
- Societal costs: What impact will this choice have on society at large?