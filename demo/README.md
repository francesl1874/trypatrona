# Patrona Demo

A working prototype of the Patrona geriatric care management platform. React 18 + Babel Standalone, no build step.

## Running locally

```
ANTHROPIC_API_KEY=sk-ant-... node server.js
# open http://localhost:8080
```

Without an API key the app runs entirely on mock data.

## AI generation

The visit note flow on **Harold Jensen's Notes tab** calls real Claude (via a hosted proxy at Railway) both locally and in production. All other clients and flows use mock data.

To test it: click Harold Jensen → Notes tab → paste observations below → Generate case note & to-dos.

## Sample visit notes

**Routine visit**
```
Visited Harold at home this afternoon. He was up and moving around the kitchen when I arrived, seemed in decent spirits. BP was 128/76, good for him. Went through his medication organizer together — all slots filled through Friday. He mentioned his right hip has been stiff in the mornings but eases up by midday. Talked about the PT exercises he's supposed to be doing; admitted he's been skipping the afternoon set. Daughter called during the visit, I was able to speak with her briefly — she's coming to town next weekend. Fridge looked well-stocked, house tidy.
```

**Concern flagged**
```
Home visit with Harold this morning. He answered the door in his pajamas at 11am, said he'd had trouble sleeping. Seemed a bit foggy at first but cleared up after we talked for a few minutes. Noted he hadn't eaten breakfast yet — said he "didn't feel hungry." Checked medications, Wednesday's evening dose still in the organizer, unclear if he took it or not. Mentioned some mild shortness of breath when walking to the mailbox yesterday but brushed it off. I encouraged him to call Dr. Khalil if it happens again. House was in order, nothing else alarming.
```
