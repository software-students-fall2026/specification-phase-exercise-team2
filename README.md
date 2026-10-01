# Specification Phase Exercise

A little exercise to get started with the specification phase of the software development lifecycle. In this exercise, your team specifies a set of improvements and new features for [The Slide Machine](https://theslidemachine.com) — see the [instructions](instructions.md) for detail, and the [background](background.md) for an introduction to the software product you are tasked with extending.

## Team members

Sai Shettar ([saishettar](https://github.com/saishettar)), Elton Yu ([elbow74](https://github.com/elbow74)), Marco Gulino (MarcoHGulino), Sienna Maguire ([SiennaSSM](https://github.com/SiennaSSM))


## Review of the Current Application

1. **Weakness** — The AI often fails to detect when the speaker switches subjects mid-sentence. Example: "I like cats, some people prefer dogs because they're a 'man's best friend'" gets written as "Cats are a 'man's best friend'."
2. **Gap** — No undo (Ctrl+Z) after the AI refines a slide; there's no way to recover the original wording if the change is worse.
3. **Weakness** — Editing Seed Notes in settings kicks focus out of the text box after about a second of not typing, interrupting the flow of writing notes.
4. **Weakness** — Content sometimes bleeds from one slide into the next, producing a redundant bullet point on the current slide.
5. **Weakness** — The exit-ticket quiz doesn't always translate well from the slide material; some answers don't fit their question, others are too obvious to test anything.
6. **Strength** — Import/export supports multiple file types, including importing slide themes that aren't built into the app by default.
7. **Strength** — The translation feature is fast, easy to find (not buried in settings), and can translate the whole interface, not just the slide content.
8. **Strength** — AI customization is in-depth: users can tune how much the system infers versus sticks to the transcript, how much content lands on one slide, and how layouts adapt to the current topic.
9. **Gap** — Users cannot add their own images; only the AI selects and places images.
10. **Gap** — No direct way to share a single slide via a link.

## Prior Art & Originality

We checked the project's roadmap, Future Work, Open Questions, and open GitHub issues and
pull requests for anything covering manual image or text placement on a slide. The
whiteboard tab currently only supports drawing (pen, highlighter, eraser); adding a user's
own image or typed text there isn't specified, scheduled, or proposed elsewhere. The
closest existing feature, seed images, uploads pictures before a lecture to guide AI
generation, a different mechanism than placing a specific image or text on a specific slide
by hand. Our own testing of the live app confirmed this gap independently. What's original
to our proposal is manual image and text placement in the whiteboard tab; what's reused is
the whiteboard's existing rule that content can't shift under what's already there, we
extend that same guarantee to manually added elements.

## Stakeholders

### Students:

**G.C (Student, Student Gov’t Member)**
1. **Goals & Needs (Before Testing):**\
  a. Clear instructions on assignments\
  b. Appease constituents in student gov’t\
  c. Ensure appropriate work-life balance\
  d. Short but descriptive notes for optimal studying
2. **Problems & Frustrations (Before Testing):**\
  a. Easy access to frequently used tools; currently frustrated with lack of convenience in NYU software\
  b. Slides that include all relevant information professors cover\
  c. Stress with schoolwork\
  d. Not enough time to comfortably complete assignments
3. **Goals & Needs (After Testing, Relating to App):**\
  a. Talk about a topic of choice (fantasy animals), make comparisons to a different topic, and have the slide generate those distinctions properly (successful)\
  b. Highlight specific portions of her speech (successful)
4. **Problems & Frustrations (After Testing, Relating to App):**\
  a. False assumption that playing the recorded audio would start from the beginning, instead of at the slide she’s currently on\
  b. Exit quiz asked questions unrelated to the presentation's content, instead asking about what the lecturer asked the Slide Machine to do (for example, “What photos did the speaker ask for?”)\
  c. Couldn’t add a Venn diagram image or change background color. Wished there was a quicker and easier way of adding these basic features\
  d. Slide bullet points were unspecific and sometimes incorrect\
  e. Slide titles were not always topic specific (for example, presenter began talking about unicorns as the national animal of Ireland, but moved to talking about unicorns/pegasi/leprechauns overall. But the first slide is titled “Facts about Ireland.”)\
  f. Trying to correct the slide as she goes, unsuccessfully, just adds on more information rather than correcting mistakes

**K.W (Student, Vet Assistant)**
1. **Goals & Needs (Before Testing):**
  a. List of things to do during the day / clear instructions\
  b. Knowing what procedures/consultations are happening among her peers\
  c. Become less involved, have less responsibility, feel less overwhelmed\
  d. Work-life balance\
  e. Feel useful and considerate of her teammates
2. **Problems & Frustrations (Before Testing):**\
  a. Difficult to access necessary material or portals, too many hoops to jump through\
  b. Communication is difficult, disconnect between professor and student, disconnect between tiers of roles\
  c. Poor allocation of time for work\
  d. Overpacked schedule, not optimal efficiency
3. **Goals & Needs (After Testing, Relating to App):**\
  a. Drew pictures and highlighted text (successful)\
  b. Switched between unrelated topics smoothly, generated transition slide/title slide (successful)
4. **Problems & Frustrations (After Testing, Relating to App):**\
  a. Was unsure if the audio recording stopped after clicking out of the slide\
  b. Thought she had to ask the slide to add pictures, text, and charts (images). The presenter didn’t realize it was supposed to add them automatically. But her image requests didn’t work either. She couldn’t generate pictures, tables, change fonts, or change colors\
  c. Thought she could add transitions (animations) between slides or onto text. Was assuming Slide Machine had the same options as Google Slides. Shows a functionality gap between competitors.\
  d. Slide Machine generated words she didn’t say. For example, “Genetics Club”, but she only said “Genetics”. Similarly, “3 laws concerning dominance” was not something she said, but it became a bullet point.


### Office Worker:

**H.M (Office Worker, SWE)**
1. **Goals & Needs (Before Testing):**\
  a. Work-life balance\
  b. Clear instructions on tickets\
  c. Having peers be familiar with the codebase, on the same page, for working on tickets\
  d. When cross-checking for PRs, desire for concise and specific presentation of feedback
2. **Problems & Frustrations (Before Testing):**\
  a. Difficulties learning a wide range of tools and becoming familiar with large codebases\
  b. Longer epics can be difficult; having one task for a prolonged period of time becomes uninteresting\
  c. Forgetting information from morning standup, wishes for less vague direction of projects discussed and for notes to look back on. Perhaps a slideshow for review.
3. **Goals & Needs (After Testing, Relating to App):**\
  a. Translate slide into another language (successful)\
  b. View and listen to other people’s slides (successful)\
  c. Presenter wanted to see captions on the screen when replaying his audio, he falsely assumed this was a feature.
4. **Problems & Frustrations (After Testing, Relating to App):**\
  a. Presenter was unsure if he had to prompt the slideshow first, instead of simply beginning the presentation. He thought pre-existing notes (seed material) were required\
  b. Changing language midway through turns off the mic, the user didn’t realize this. He wished he was shown an alert\
  c. Great difficulty adding images, such as pictures, graphs, and diagrams. Without these visuals working, the presenter did not see the point in the Slide Machine compared to just a recorded transcript\
  d. Attempted to drag in an image, frustrated by inability to control visuals

### Instructors:

**R.L (Tutor)**
1. **Goals & Needs (Before Testing):**  
   a. Efficiently create and summarize slide decks for biology lectures and lab sections  
   b. Translate educational materials to accommodate different types of students  
   c. Streamline slide creation through voice input without manual typing or tedious formatting  
   d. Quickly access relevant scientific visuals, diagrams, and external reference data  
2. **Problems & Frustrations (Before Testing):**  
   a. Manual slide preparation and layout design take time away from teaching and research  
   b. Existing presentation software lacks real-time voice integration  
   c. Sourcing and embedding relevant biological graphics is slow and clunky  
3. **Goals & Needs (After Testing, Relating to App):**  
   a. Voice integration ("speak to talk") worked well and allowed the presenter to create content efficiently  
   b. Successfully translated slide content  
   c. Quickly generated accurate summaries for each slide  
   d. Experienced fast overall processing and generation time  
4. **Problems & Frustrations (After Testing, Relating to App):**  
   a. Lacks a real-time visual indicator showing how speech is being processed, creating uncertainty about when to start or stop talking and when a new slide is being created  
   b. Unable to generate novel information or perform web lookups; when the presenter asked a question, the app placed the question directly onto the slide instead of generating an answer  


**K (Professor)**
1. **Goals & Needs (Before Testing):**  
   a. Speed up lecture content creation while retaining quality and important information  
   b. Easily update or correct lecture content without needing follow-up emails or verbal corrections after class  
   c. Maintain universal lecture formatting to help students stay on track and become familiar with the material  
   d. Have the flexibility to sidetrack efficiently during lectures without being restricted by lesson plans or timing  
2. **Problems & Frustrations (Before Testing):**  
   a. Time is wasted focusing on small lecture details and worrying about whether the material is digestible for students  
   b. Unfamiliar applications often do not feel beginner-friendly for less tech-savvy users, discouraging adoption of new teaching methods  
   c. Lectures are not heavily focused on slide text, creating a need for a more streamlined way to organize material for students’ future studying  
   d. Technical difficulties can disrupt the flow of class and negatively affect student attention  
3. **Goals & Needs (After Testing, Relating to App):**  
   a. Website layout was simple to use, allowing the presenter to quickly adapt to the workflow  
   b. Successfully retained important vocabulary and key points from the lecture  
   c. Maintained a steady pace when creating new slides  
4. **Problems & Frustrations (After Testing, Relating to App):**  
   a. Uncertainty arose when the presenter paused; she was unsure whether the app would continue creating content without additional speech and sometimes waited to see what information the AI had captured  
   b. Some generated summaries were too simplistic and did not retain all of the intended takeaways from the topic

## Product Vision Statement

Our proposal adds manual content controls to The Slide Machine’s whiteboard tab, letting instructors and other presenters place their own images and their own typed text directly onto a slide, instead of being limited to what the tool draws or generates on its own.

## User Requirements

### Student:
1. "As a student, I want my professors' anecdotes to appear on lecture notes so that I can have an easier time studying."
2. "As a student, I want to be able to tell which parts of my lecture notes came from my professor's main lecture and which came from an anecdote so that I know what information is most important."
3. "As a student, I want to see corrections my professor made during a lecture reflected in the lecture notes so that I do not study incorrect information."
4. "As a student, I want to receive a notification when my professor corrects something from the lecture so that I know to pay attention to the updated information."
5. "As a student, I want to review the anecdotes and examples from a lecture separately from the main lecture notes so that I can use them as additional study material."
6. "As a student, I want to search my lecture notes for specific words or topics so that I can quickly find the information I need when studying."
7. "As a student, I want to mark important parts of my lecture notes so that I can easily return to them when preparing for an exam."
8. "As a student, I want to receive practice questions based on both the main lecture and my professor's anecdotes so that I can test whether I understand the material."
9. "As a student, I want to see which lecture or section a practice question came from so that I can review that material when I get an answer wrong."
10. "As a student, I want to report an incorrect or confusing lecture note so that the information can be corrected before I use it to study."



### Instructor:
1. "As an instructor, I want a spoken correction like 'actually, scratch that' to replace the wrong text on the current slide instead of adding more text below it, so I don’t end up with a slide that contradicts itself."
2. "As an instructor, I want to mark something I’m saying as a note to myself, not lecture content, so it never becomes a slide bullet or a quiz question."
3. "As an instructor, I want to see which parts of a generated slide came from a correction versus my original wording so I can tell whether the system caught my correction the way I meant it."
4. "As an instructor, I want to undo an automatic correction the system made so I can restore the original wording if it misunderstood me."
5. "As an instructor, I want to review, after the lecture, every moment the system treated as an aside rather than content so I can catch anything it filtered out that should have been on a slide."
6. "As an instructor, I want to be warned in the moment when the system isn’t confident whether I’m correcting a slide or adding new content so I can clarify without losing my train of thought."
7. "As an instructor, I want to turn off automatic correction detection for a lecture, so slides only ever get appended to when I don’t trust the feature to interpret me correctly."
8. "As an instructor, I want to see and remove any quiz question generated from an aside or a comment I made to the tool rather than the class, before I publish the quiz to students."
9. "As an instructor, I want the system to keep capturing my lecture in plain append-only mode if correction detection fails or times out, so a lecture in progress never has to stop."
10. "As an instructor, I want to see a short list of the corrections I made during a lecture after it ends, so I can decide whether any of them need a more careful manual edit."
11. "As an instructor, I want to upload an image from my own device into the whiteboard tab, so I can put a diagram or photo I already have directly onto a slide."
12. "As an instructor, I want to type my own text box onto a slide in the whiteboard tab, so I can add a label, caption, or note the system didn’t generate."

### Employee:
1. "As an employee, I want to seed a project with my team’s internal terminology and project names before a demo, so the generated slides use vocabulary my teammates actually recognize instead of generic phrasing."
2. "As an employee, I want to mark a presentation as company internal only, so the generated deck and quiz can’t be viewed or discovered by anyone outside my organization."
3. "As an employee, I want a spoken correction during a demo, like fixing a wrong metric I just said, to actually replace the wrong slide text, so a teammate skimming the deck later doesn’t see two contradictory numbers."
4. "As an employee, I want any confidential detail I mention out loud, like an unreleased feature name or a customer’s name, excluded from the slide and from any generated quiz question, so I don’t have to worry about oversharing in front of the room."
5. "As an employee, I want to distribute a post-presentation knowledge check to the teammates who attended, so I can confirm the key takeaways actually landed before we move on."
6. "As an employee, I want to see which team or project budget my presentation’s AI usage is billed against, so it isn’t quietly counted against my personal usage cap."
7. "As an employee, I want to export the generated deck into our company’s existing knowledge base or wiki after a talk, so it becomes part of our team’s documentation instead of living only inside the slide machine."
8. "As an employee, I want to set an expiration or review date on a deck that contains confidential project details, so sensitive material doesn’t sit around indefinitely after the project it covers has shipped or been cancelled."
9. "As an employee, I want to restrict who at my company can edit a deck I’ve shared internally, so a teammate can view it without being able to change what I actually presented."
10. "As an employee, I want to be notified if the AI service refuses or fails partway through my demo because it flagged something as sensitive, so I know to keep talking and patch the gap manually afterward instead of assuming the deck is complete."
11. "As an employee, I want to upload a screenshot or diagram from my own work into the whiteboard tab, so I can show something the live-generated slide couldn’t capture, like an architecture diagram or a code snippet."
12. "As an employee, I want to mark an uploaded image as company confidential, so it’s excluded if the deck is ever shared outside my organization."


## Activity Diagrams

As an instructor, I want to upload an image from my own device into the whiteboard tab, so I can put a diagram or photo I already have directly onto a slide.

<img width="798" height="1179" alt="Instructor (Image Upload) drawio" src="https://github.com/user-attachments/assets/a004c1ae-ba3b-441d-9de6-df965196d267" />

As an instructor, I want to type my own text box onto a slide in the whiteboard tab, so I can add a label, caption, or note the system didn’t generate.

<img width="582" height="1004" alt="Instructor (Text Inset) drawio" src="https://github.com/user-attachments/assets/a1fe8532-b29a-4996-bf91-45a695b19059" />

As an employee, I want to upload a screenshot or diagram from my own work into the whiteboard tab, so I can show something the live-generated slide couldn’t capture, like an architecture diagram or a code snippet.

<img width="392" height="1122" alt="Employee (Image Upload) drawio" src="https://github.com/user-attachments/assets/c7bbbf28-b4a4-4527-b59d-3c6eabadbab0" />

As an employee, I want to mark an uploaded image as company confidential, so it’s excluded if the deck is ever shared outside my organization.

<img width="899" height="1046" alt="Employee (Confidentiality Marking) drawio" src="https://github.com/user-attachments/assets/86587ac8-7530-47be-a05a-92559271a7f4" />

<img width="2344" height="3282" alt="Blank diagram_page-0001" src="https://github.com/user-attachments/assets/0dd58bc0-f6ea-4900-bcfa-d71e086ccbc7" />


## Wireframes

<img width="362" height="191" alt="Screenshot 2026-09-30 at 12 15 21 PM" src="https://github.com/user-attachments/assets/c249b67b-9c66-49f2-b8db-6819c70bbcb4" />\
<img width="297" height="336" alt="Screenshot 2026-09-30 at 12 15 07 PM" src="https://github.com/user-attachments/assets/c3088aa5-66bc-4eae-b843-a7ff75133120" />
<img width="300" height="335" alt="Screenshot 2026-09-30 at 12 14 54 PM" src="https://github.com/user-attachments/assets/29a99f12-97a8-45c7-b9ae-7db1f823e2e3" />
<img width="880" height="569" alt="Screenshot 2026-09-30 at 12 14 34 PM" src="https://github.com/user-attachments/assets/6c877f20-2632-4371-8dba-7dfae792df23" />


## Clickable Prototype

https://www.figma.com/design/6GsMji6ODp9vGgwjKXzsph/Project-1---Slide-Machine-Feature?node-id=0-1&t=2sWlwygdTnV0sSS7-1

## Stakeholder Demo

https://theslidemachine.com/d/untitled-583e0c02

## Exit Ticket

See instructions. Delete this line and place a link to the exit-ticket quiz you generated from your demo deck and distributed to the class, along with a short note on what — if anything — you had to correct in the generated questions before publishing.
