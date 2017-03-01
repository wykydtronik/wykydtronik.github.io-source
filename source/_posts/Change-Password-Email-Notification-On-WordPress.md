---
title: Change Password Email Notification On WordPress
date: 2017-03-01 10:37:23
tags: WordPress
---
Below is an example on how to alter the password notification email that WordPress sends users when their password changes. This simply uses the password_change_email hook and passes the $new_message_txt to it.

{% codeblock %}
add_filter(
  'password_change_email',
  'wpse207879_change_password_mail_message',
  10,
  3
);
function wpse207879_change_password_mail_message(
  $pass_change_mail,
  $user,
  $userdata
) {
  $new_message_txt = __( 'Some text ###USERNAME### more text
    even more text ###EMAIL### more text after more text
    last bit of text ###SITENAME###' );
  $pass_change_mail[ 'message' ] = $new_message_txt;
  return $pass_change_mail;
}
{% endcodeblock %}

I will likely just throw this into a [Must Use plugin](https://codex.wordpress.org/Must_Use_Plugins/ "dafuq") just so that the message is covered across the network.
