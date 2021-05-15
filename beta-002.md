# InsanityBot 2.0.0-beta.002

This roadmap indicates all planned changes to be included in the second beta release.

## Tickets

2.0.0-beta.002 will ship with a complete ticket system. This includes the classic ticket commands and customizable message reactions, as well as transcripts and ticket metrics, but also the ticket scripting engine Kyuu. Kyuus syntax is largely identical to C++, with differences in how variables and constants are defined and its lack of a main method:

~~~kyuu
#event on_command_sent
#category 584140343558275109
#command supervisor

const &embed = DiscordEmbed(
    "{
        "Color" = 3342362,
        "Description" = "Ticket {0} moved to supervisor"
    }"
);

var &ticketId = Guid(this.ticket_id);

entry:
if(context.executor.isStaff) {
    this.move(584140343558275110);
    &embed.Description.replace_all(&ticketId);
    this.send_embed(&embed);
}
return;
~~~

Kyuu supports if-else statements and switch-case statements for flow control. Functions are not allowed. Keywords are `const`, `var`, `this`, `env`, `if`, `else`, `switch`, `case`, `default`, `entry` and `return`. Allowed data types are `DiscordEmbed`, `DiscordMessage`, `Guid`, `int16`, `int32`, `int64`, `uint16`, `uint32`, `uint64` and `boolean`. Allowed operators are `+`, `-`, `*` and `/`. Kyuu scripts cannot depend on each other. Variables and constants are prefixed with `&`-

## Modlogs

2.0.0-beta.002 will bring significant improvements to the modlog embed: newlines after each line, to improve readability, and a footer including the total amounts of each infraction type, as well as being able to only request an embed of a specific type, using `i.modlog [warn|mute|blacklist|kick|ban] @user`.

## Miscellaneous

2.0.0-beta.002 will largely revamp both `i.say` and `i.embed` for greater customizability and to accept pre-defined embed json.

## Performance

2.0.0-beta.002 will improve performance of temp-mutes and -bans by not loading each file from the file system every iteration and instead keeping them cached.
