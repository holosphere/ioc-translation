---
content:
    items: '@self.modular'
    order:
        by: folder
        dir: asc
        custom:
            - _header
            - _mentions
            - _signup
            - _part1
            - _part2
            - _part3
            - _part4
            - _part5
menu: Home
onpage_menu: true
form:
    name: contact
    action: mail.php
    method: GET
    fields:
        -
            name: name
            label: Name
            classes: form-control
            placeholder: 'Dein Name'
            autocomplete: 'on'
            type: text
            position: left
            validate:
                required: true
        -
            name: email
            label: Email
            classes: form-control
            placeholder: 'Deine Email Adresse'
            type: email
            position: left
            validate:
                required: true
        -
            name: message
            label: Message
            placeholder: 'Bitte haltet mich auf dem laufenden! (Oder schreib uns dein Anliegen)'
            type: textarea
            classes: form-control
            position: right
            validate:
                required: true
    buttons:
        -
            type: submit
            classes: 'btn btn-primary btn-lg'
            value: Send
    process:
        -
            email:
                subject: '[Site Contact Form] {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            message: 'Danke für die Anfrage!'
---

