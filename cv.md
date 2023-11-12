# Aslan Aliev

**passionate fullstack developer**

## CONTACTS

web-site: `ortsaslan.dev`  
email: `ortsaslan@gmail.com`  
telegram: `t.me/ortsaslan`  
github: `github.com/ortsaslan`  
discord, twitter and all other platforms: one nickname to rule them all `ortsaslan`.

## ABOUT ME

Confident and well-grounded software developer who make things done. Through training and practice I've gained expertise in fullstack development. My main stack include Angular on frontend, Spring on backend and PostgreSQL for data. I have all required expertise to deliver enterprise-grade web-applications and softskills to effectively communicate within my team.

## EXPERIENCE

- RS School\
  7 months long intensive studing of frontend under supervision of mentors from well-known and globaly recognized software companies (like EPAM). A lot of frontend tasks and mini-projects. I delivered awesome final project with my team and received the complition certificate. One of the top ranked students on my course.

- Personal projects

## SKILLS

My fullstack developer toolbelt are include:

- JavaScript/HTML/CSS
- Angular/TypeScript
- Java
- Spring Boot/Data/Security
- PostgresSQL
- Git
- OOP/REST/SOLID
- CI/CD

## CODE EXAMPLES

My code in Python. For static code analyzer project. Can be found on my github account.

```
blank_lines_counter = 0
lines_with_issues = {}
style_issues = {'S001': 'Too long',
                'S002': 'Indentation is not a multiple of four',
                'S003': 'Unnecessary semicolon',
                'S004': 'At least two spaces required before inline comments',
                'S005': 'TODO found',
                'S006': 'More than two blank lines used before this line'}


def add_line(line, issue_code):
    global lines_with_issues
    try:
        lines_with_issues[line].append(issue_code)
    except KeyError:
        lines_with_issues[line] = [issue_code]


def log_issue(issue_lines_dict):
    for line in issue_lines_dict:
        for issue_code in issue_lines_dict[line]:
            print(f"Line {line}: {issue_code} {style_issues[issue_code]}")


def check_s001(line, line_num):
    if len(line) > 79:
        add_line(line_num, "S001")


def check_s002(line, line_num):
    if (len(line) - len(line.lstrip())) % 4 != 0:
        add_line(line_num, "S002")


def check_s003(line, line_num):
    if ";" in line:
        smcol_indxs = []
        current_index = line.index(';')
        for _ in range(line.count(";")):
            index = line.find(";", current_index)
            smcol_indxs.append(index)
            current_index += 1

        qmark = None
        qmark_first_indx = 0
        qmark_second_indx = 0
        if "'" in line or '"' in line:
            if "'" in line:
                qmark = "'"
            elif '"' in line:
                qmark = '"'
            qmark_first_indx = line.find(qmark)
            qmark_second_indx = line.find(qmark, qmark_first_indx + 1)

        for i in smcol_indxs:
            if "#" in line and qmark:
                if i < line.index("#"):
                    if not qmark_first_indx < i < qmark_second_indx:
                        add_line(line_num, "S003")
                        break
            elif qmark and not qmark_first_indx < i < qmark_second_indx:
                    add_line(line_num, "S003")
                    break
            elif "#" in line and i < line.index("#"):
                add_line(line_num, "S003")
                break
            elif "#" not in line and not qmark:
                add_line(line_num, "S003")
                break


def check_s004(line, line_num):
    if "#" in line and line.index("#") != 0:
        hsign_indx = line.index("#")
        if line[hsign_indx - 2: hsign_indx] != "  ":
            add_line(line_num, "S004")


def check_s005(line, line_num):
    if "todo" in line:
        if "#" in line and line.index("#") < line.index("todo"):
            add_line(line_num, "S005")


def check_s006(line_num):
    global blank_lines_counter
    if blank_lines_counter > 2:
        blank_lines_counter = 0
        add_line(line_num, "S006")


def main():
    global blank_lines_counter
    line_counter = 0

    file = open(input(), "r")

    for line in file:
        line_counter += 1
        if line.isspace():
            blank_lines_counter += 1
        else:
            line = line.lower()
            check_s001(line, line_counter)
            check_s002(line, line_counter)
            check_s003(line, line_counter)
            check_s004(line, line_counter)
            check_s005(line, line_counter)
            check_s006(line_counter)

    file.close()
    log_issue(lines_with_issues)


main()
```

## EDUCATION

I am graduated from College of Statistics, Informatics and Computers in Ufa, Russia. I held Associate degree in Accounting. Completed in 2007.

## LANGUAGES

- Russian (C2)
- English (B1)
- Arabic (B1)
