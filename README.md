# cdl-sak

A Claude skill for auditing and rewriting copy. It follows [Content Design London](https://contentdesign.london), the [Readability Guidelines](https://readabilityguidelines.co.uk) and a set of house rules. Every rule it flags carries its source: [CDL], [RG] or [House].

Say "CDL" to Claude with some copy, and it asks whether you want an audit or a rewrite.

## Install in Claude Code

Add this repository as a plugin marketplace, then install the plugin:

```
/plugin marketplace add salmanahadkads-creator/cdl-sak
/plugin install cdl-sak@cdl-sak
```

### Get updates

New versions land whenever this repository changes. To pull them in:

```
/plugin marketplace update cdl-sak
```

To get them automatically, run `/plugin`, open **Marketplaces**, pick **cdl-sak** and turn on auto-update.

## Install in claude.ai or the Claude app

1. Download [cdl-sak.zip](https://github.com/salmanahadkads-creator/cdl-sak/releases/latest/download/cdl-sak.zip).
2. In Claude, go to **Settings > Capabilities > Skills** and upload the zip.

Uploaded skills do not update on their own. Download the zip again and re-upload it to get a newer version. [Watch this repository](https://github.com/salmanahadkads-creator/cdl-sak/subscription) (Custom > Releases) to hear when it changes.

## What is inside

```
.claude-plugin/marketplace.json    the marketplace
plugins/cdl-sak/                   the plugin
  skills/cdl-sak/SKILL.md          the skill itself
```

The house rules are written to one person ("Salman"). They still apply to anyone, so read "Salman" as "you".

## License

MIT. The Content Design London and Readability Guidelines rules are paraphrased from their public pages and credited to them.
