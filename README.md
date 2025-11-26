## Takes' CISSP Study
Material and Resources for CISSP Certification | Last Update: 25/11/2025 |

## Intro
This repository contains the study materials, references, and notes I used while preparing for the CISSP exam. I continue to refine and expand the content to keep it useful for anyone working toward certification.
The volume of available material can make it difficult to know where to start or what deserves focused attention. This collection is not exhaustive, but it is designed to highlight resources, practice material, and references that provide real value.
The study guides included here are updated for 2025 and aligned with the latest (ISC)² objectives and the 10th edition of the Official Study Guide.
If you find this repository helpful, share it. If you notice errors or have improvements to suggest, let me know. Connect with me on [LinkedIn](https://www.linkedin.com/nicktakes).

## CISSP Exam Overview
The CISSP exam has a huge amount of available study material: the Official Study Guide, third-party books, instructor content, and community notes. For a structured start, the Sybex Study Guide combined with the Official Practice Tests is still the most complete foundation.

## Exam Structure
The English exam is a 3 hour Computer Adaptive Test (CAT) with 100-150 questions.  
You may pass or fail at question 100. The exam stops the moment the system is confident you are above or below the passing threshold.  
All eight domains contribute roughly 10-16 percent.

## Who qualifies for CISSP
You need five years of paid, cumulative experience across two or more CISSP domains. A four-year degree or an ISC2-approved credential waives one year. If you lack the required experience, you can pass the exam and become an Associate of ISC2 until you meet the requirement.

## Table of contents
- [Intro](#intro)
- [CISSP Exam Overview](#cissp-exam-overview)
- [Exam Structure](#exam-structure)
- [Who Qualifies for CISSP](#who-qualifies-for-cissp)
- [My Study Approach](#my-study-approach)
- [Study Timeline Table](#study-timeline-table)
- [How to Think for This Exam](#how-to-think-for-this-exam)
- [PPT and RGLE (Short Exam Version)](#ppt-and-rgle-short-exam-version)
- [Core Mindset Rules](#core-mindset-rules)
- [Test Taking Process](#test-taking-process)
- [Coverage and Study Strategy](#coverage-and-study-strategy)
- [Memorization](#memorization)
- [Resources](#resources)

## My Study Approach
Use the (ISC)² Official Study Guide (OSG) once to build the baseline, then shift entirely to Destination CISSP textbook as your core. Treat the OSG only as a reference when something needs clarification. Lock in PPT and RGLE early and start practice questions by day 7. 

- Use a minimal resource set: OSG practice tests, the 50 CISSP YouTube questions, and Gwen Bettwy's approach videos (not her trap-heavy mocks).
- The CAT runs 100-150 questions in 3 hours, which gives you about 72 seconds per question. Set a timer in every session and hold the pace.
- Run a weekly full block of 150 timed questions to build rhythm.
- Build memory tricks for formulas and models in week 1-2. Add no new sources after week 3.
- Follow one tight cycle: questions, identify gaps, read only for those gaps, update notes, retest.
- Close each domain with the Destination CISSP Mind Map. Use [Pete Zerger's CISSP Exam Cram](https://github.com/pzerger/cisspexamcram/blob/main/Resources.md) only in the final week.

> [!NOTE]
> You're ready once you can remove two answers instantly using PPT and RGLE, even on material you haven't seen.

## Study Timeline Table
| Start | Finish | Activity | Notes |
|--------|---------|----------|--------|
| 01/11/25 | 03/11/25 | Bought ISC2 CISSP Study Guide 10th Edition | You've got to start somewhere |
| 04/11/25 | 07/11/25 | Finished index labeling the book | Labeled each chapter and domain |
| 08/11/25 | 11/11/25 | Planning learning approach | Time estimates and study strategy |
| 12/11/25 | 14/11/25 | Overall difficulty assessment | Source review and expectations |
| 15/11/25 | 16/11/25 | Phase 1 Plan | Set for reading 1 domain per week |
| 17/11/25 | 23/11/25 | Domain 1 | OSG 10th - Slow, 1 week completion  |
| 24/11/25 | 26/11/25 | Domain 2 | OSG 10th - Completed in 2 days |
| 25/11/25 | 25/11/25 | GitHub repository creation | Helps me structure tremendously |
| 25/11/25 | continuous | Started exam questions | Suggested starting this after reading Domain 1 |
| 25/11/25 | continuous | Started Thor Teaches' [QOTD](https://thorteaches.com/qotd/) | Suggested starting this after reading Domain 1  |
| 26/11/25 | ? | Domain 3 | OSG 10th - In progress |

## How to Think for This Exam
CISSP is a management-level test. Not technical. You answer as the person accountable for risk, governance, cost, and people.  
How to Think Like a Manager reinforces this: managers choose options that reduce organizational risk with the broadest positive impact, not the option that is technically elegant.

## PPT and RGLE (Short Exam Version)
### PPT - People > Process > Technology
1. **People first** - Safety, reporting, management, legal.
2. **Process next** - Policies, assessments, documentation, governance.
3. **Technology last** - Only if the question makes you the technician.

### RGLE - Role > Goal > Lifecycle > Eliminate
1. **Role** - Answer only what *your job* is allowed to do.
2. **Goal** - What is the question trying to protect?
3. **Lifecycle** - Stay in order (detect → contain → eradicate → recover).
4. **Eliminate** - Remove tech answers unless you *are* the tech.

## Core Mindset Rules
Drawn from Destination CISSP, Gwen Bettwy, Study Notes and Theory.
These rules describe the mental lens you need during the CISSP exam. They define how you should think by default: like a manager who prioritizes people, risk reduction, and high-level business impact rather than technical detail.
- **People first.** Keep humans safe before anything else. If an answer protects people, it wins.
- **Integrity vs confidentiality vs availability.** Figure out what the question is really about: keeping data correct, keeping it secret, or keeping it usable. Choose the answer that matches that one thing.
- **Manager, not engineer.** Think like the boss of the company, not the person fixing computers. Pick the answer that saves money, lowers risk, and supports the big goals.
- **Choose prevention first.** CISSP favors preventing risk over detecting or correcting it, unless the question forces another lifecycle point (Stopping a problem before it happens is almost always the best choice.).
- **Avoid technician answers.** If the answer sounds like technical/hands-on work (patching, configuring, running tools), it's probably a trick unless the question clearly puts you in an operational role.
- **Pick the answer that covers the others.** Broadest impact wins. Choose the option that solves the whole problem, not just a small piece of it. Narrow, purely techical answers don't win.
- **If stuck: which answer is not like the others.** When a question is confusing, don't focus on the question first. Look at the four answer choices and find the one that doesn't fit with the others.


## Test Taking Process
These steps describe the method you use to solve each question. They explain the practical workflow: how to read, classify, eliminate, and choose answers using a structured manager-focused approach.
- **Read the question before the answers** - First understand what the question is really asking. Figure out who you are supposed to be (manager, responder, auditor), which part of the security lifecycle you're in, and what the core problem is.
- **Classify the question** - Decide whether the question is about confidentiality, integrity, availability, safety, governance, risk, or compliance. This tells you what type of answer will fit.
- **Eliminate tech answers unless the question is explicitly technical** - Hands-on actions like patching, configuring, or running tools are usually the wrong path in management-style questions.
- **Select the preventive or governance aligned control first** - In CISSP logic, preventing problems (with policies, training, and leadership decisions) is usually more valuable than detecting or fixing them later.
- **Use business language logic** - Choose the answer senior management would expect: something that reduces risk, protects the organization, and supports long-term goals.
- **If everything looks right, choose the most comprehensive control** - Prefer the answer that solves the whole problem across the organization, not just a small slice of it.
- **When lost, pick the answer that is "different"** - If the question is confusing, look at all the answer choices and find the one that doesn't match the pattern of the others. This "odd one out" trick helps you avoid being misled by answers that all look equally correct.

## Coverage and Study Strategy
CISSP isn't about memorizing facts. You have to actually understand how things work.  
Some topics are big ideas you must know, and others are details you're likely to be tested on.  
The exam mixes topics together on purpose, so questions often pull pieces from different domains at the same time.

### Common prep challenges
- Knowing whether you are studying the right depth  
- Understanding the managerial viewpoint  
- Maintaining pace and consistency over months  

### Ways to correct this
- Use different books and sources so you see the same idea explained in different ways. This helps the hard parts make more sense.
- Use lots of practice questions to find the areas you didn't realize you were weak in.
- Connect ideas across domains instead of studying each one alone, because the exam mixes topics together.

## Memorization
- Acronyms, visual memory, mindmaps, and cross-domain diagrams help retain structural relationships.
- Verbalizing answers, using flashcards, and re-explaining concepts out loud improves recall.  
- Use diagrams for CIA, AAA, access control models, and risk formulas.

## Resources
- [Gwen Bettwy's CISSP Playlist](https://www.youtube.com/watch?v=NdsP0yM1yTo&list=PLrjhjv3vQi5DZ3FO0Eb-iMJoI4RzoANOw)
- [Best CISSP Books To Read To Crack The Exam - Free Download (PDF) - Tech Hyme](https://techhyme.com/best-cissp-books-to-read-to-crack-the-exam-free-download-pdf)

### Others' Experiences
- https://www.reddit.com/r/cissp/comments/18m9zrx/realistic_view_of_the_exam_from_someone_who_just/
- https://www.reddit.com/r/cissp/comments/1bwha75/passed_cissp_1st_attempt_with_10_weeks_of_prep_my/

### Others' GitHub
- [GitHub - alios7/CISSP](https://github.com/alios7/CISSP/tree/main)
- [GitHub - jefferywmoore/CISSP-Study-Resources: CISSP Study Resources](https://github.com/jefferywmoore/CISSP-Study-Resources?tab=readme-ov-file)
