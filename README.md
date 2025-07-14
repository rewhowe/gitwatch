# Gitwatch

## About

Command-line tool for polling Git activity. Gives periodic updates on new PRs, comments, etc within the terminal.

Useful for polling activity within a single respository when email and other notifications are disabled due to a large volume of "noise".

## Usage

1. `cd` to the directory with your git repository

2. Run `gitwatch` (it will automatically detect the repo config, including your username)

3. Enter your token (Manage account > Personal access tokens > Create a token)※

※ Alternatively, enter your password. Please note that this is NOT secure, the username / password are base64 encoded and are visible from the process list and local network and whatnot.

## Notes

* Update period is 10 minutes

* "Too old threshold" is 30 days

* Mostly formatted for 80-char width

## Example

```
$ gitwatch
-------------------------------- 80 chars width --------------------------------
Start watching example_project/example_repo
Access Token for andrew.howe (empty for basic auth): ****

# Open Pull Requests:
 * #697 "[EXAMPLE-10001] Add test code" → "feature/EXAMPLE-10000_project-base" (
fname.lname) (approved)
 * #696 "[EXAMPLE-10002] Add new API" → "feature/HRPRJ-10000_project-base" (fnam
e.lname)
 * #709 "Feature/EXAMPLE-10003 Fix bug in API GET" → "feature/HRPRJ-10002_api-get
-impl" (fname.lname)
 * #431 "Feature/EXAMPLE-9987 Refactor old UT" → "master" (fname.lname) (approved
)
   (#431 is too old and will be skipped)

Activity for #696 "[EXAMPLE-10002] Add new API" → "feature/EXAMPLE-10000_project-
base"
https://git.example.com/projects/example_project/repos/example_repo/pull-requests
/696/overview
 * Original comment by You:
    Maybe we could try reusing this section above?
   > fname.lname replied
      Yes this could work.
 * You made a comment:
    I think this could be improved.
    We should be able to make use of the decorator pattern here, this way we can
    add the required functionality without modifying the inner class's implement
    ation.

Updated at 09:51:37
```

## TODO:

* Allow changing config via command line options

* Nicer links that go directly to comments

* Clean up the monolithic code...
