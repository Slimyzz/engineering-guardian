# Esam Day 3: Codex Stop-hook Capture Findings

## Scope

These are Codex fixtures for learning and supplemental test data only.
Engineering Guardian v1 remains a Claude Code Stop-hook project.

## Capture result

Seven real Codex Stop payloads were captured.
Six scrubbed fixtures are saved in `tests/fixtures/codex/`.

## Seven questions

1. **What top-level keys does the Stop payload have?**

   `session_id`, `turn_id`, `transcript_path`, `cwd`,
   `hook_event_name`, `model`, `permission_mode`,
   `stop_hook_active`, and `last_assistant_message`.

2. **Does it contain the conversation, or a path to it?**

   It contains `transcript_path`, which points to the conversation
   transcript. The Stop payload does not itself contain the full
   conversation.

3. **What format is the transcript file?**

   The transcript is a JSON Lines file with a `.jsonl` filename.
   The inspected transcript contained 152 records.

4. **How do you tell an assistant turn from a user turn?**

   Transcript records have a top-level `type` and a nested `payload`.
   `response_item` records expose roles including `assistant`, `user`,
   and `developer`.

5. **Where are tool calls recorded?**

   `event_msg` records include command-related fields such as `cmd`,
   `command`, `parsed_cmd`, `output`, `aggregated_output`,
   `formatted_output`, `exit_code`, and `status`.

6. **Is there a timestamp on each entry?**

   Yes. Transcript records use a top-level `timestamp` field, allowing
   events to be ordered.

7. **What is `stop_hook_active`, and when is it true?**

   It was `false` in all seven ordinary Stop payloads captured here.
   A `true` case was not observed, so its exact repeat-hook behaviour
   is not inferred from these fixtures. Future live hook logic must
   treat it as a loop-protection condition and fail open until tested.

## Privacy

Fixtures were scrubbed successfully. They contain no `/home/` path
or `esam2005` username.
