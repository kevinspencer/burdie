# burdie

Lots of people have written their own twitter clients, this one is mine.


### Installation

Copy burdie to a directory of your choice.

You'll need the following modules installed, all available from the CPAN:

```File::HomeDir
IO::Prompt
Twitter::API```

### Usage

`./burdie "you know the other day I ate some really rather nice burritos"`

### Configuration & OAuth

Starting August 2010, twitter no longer allows basic auth and forces OAuth.
burdie already has the necessary app consumer_key and consumer_secret but
still requires an access_token and access_token_secret.

On first run, burdie will attempt to authorize with twitter to obtain
those token values.  It does this in a couple of steps:

- prints the twitter auth URL to screen, you will have to visit that URL
  in your browser.

- twitter will ask to authorize burdie, if you choose yes, you will be
  given PIN number.  You must give that PIN number to burdie.

- burdie will then, using the PIN number, obtain the necessary access_token
  and access_token_secret from twitter and store those to a file for all future
  runs.

burdie stores the access tokens in ~/.burdie_tokens
