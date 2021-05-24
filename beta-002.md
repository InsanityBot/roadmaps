# InsanityBot 2.0.0-beta.002

This roadmap indicates all planned changes to be included in the second beta release.

## Tickets

2.0.0-beta.002 will ship with a complete ticket system. This includes the classic ticket commands and customizable message reactions, as well as transcripts and ticket metrics.

## Modlogs

2.0.0-beta.002 will bring significant improvements to the modlog embed: newlines after each line, to improve readability, and a footer including the total amounts of each infraction type, as well as being able to only request an embed of a specific type, using `i.modlog [warn|mute|blacklist|kick|ban] @user`.

## Miscellaneous

2.0.0-beta.002 will largely revamp both `i.say` and `i.embed` for greater customizability and to accept pre-defined embed json.

## Performance

2.0.0-beta.002 will improve performance of temp-mutes and -bans by not loading each file from the file system every iteration and instead keeping them cached.

## Notes

Kyuu, originally scheduled for this release, will be merged into the wider scripting API.
