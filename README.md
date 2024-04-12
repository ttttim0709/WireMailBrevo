# WireMailBrevo Module for ProcessWire CMF/CMS

This module allows ProcessWire to send transactional emails via [Brevo](https://www.brevo.com).

## Installation

1. Copy the `WireMailBrevo` directory into your `site/modules/` directory.
2. In the ProcessWire admin, go to Modules > Refresh.
3. Click "Install" next to the WireMailBrevo module.

## Usage

Example usage:

```
$email = $mail->new();
$email->to = 'recipient@somedomain.com';
$email->subject = 'Test #1';
$email->body = 'An example email';
$email->send();
```

Use of Versions:
Check the [Brevo dev section](https://developers.brevo.com/docs/batch-send-transactional-emails) for more information about Message versions

```
$email->version([
    [
        'to' => [
            [
                'email' => 'bob@example.com',
                'name' => 'Bob Anderson'
            ],
            [
                'email' => 'anne@example.com',
                'name' => 'Anne Smith'
            ],
        ],
        'subject' => 'This is my version subject line',
    ],
    [
        'to' => [
            [
                'email' => 'jim@example.com',
                'name' => 'Jim Stevens'
            ]
        ],
        'htmlContent' => "<!DOCTYPE html><html><body><h1>Modified header!</h1><p>This is still a paragraph</p></body></html>",
    ],
]);
```

## Configuration

After installing the module, you can configure it by going to the module settings page. You need to provide the following configuration options:

- Brevo API Key: Obtain this key from your [Brevo account settings](https://app.brevo.com/settings/keys/api).
- Sender Email Address: The email address to be used as the sender.
- Sender Name: The name associated with the sender's email address.
