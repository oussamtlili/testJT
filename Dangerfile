
# Make it more obvious that a PR is a work in progress and shouldn't be merged yet
warn("PR is classed as Work in Progress") if github.pr_title.include? "[WIP]"

# Warn when there is a big PR
warn("Big PR") if git.lines_of_code > 500

# Fail when developer forget // TODO somewhere in the code
fail("Your forget // TODO in code") if (git.added_files + git.modified_files).any?{ | file| File.readlines(file).grep(/TODO/).size > 0 }

# Warn when PR don't contains unit tests
fail("Unit Tests are very important") if (git.added_files + git.modified_files).all?{ | file| file.include? "test" == false }


