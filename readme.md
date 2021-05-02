# Instagram Backup

The easiest way I've found to programmatically backup Instagram data.

1. Go to [`https://developers.facebook.com/apps`](https://developers.facebook.com/apps)
2. Click **Create App**
3. Select **Consumer**
4. Fill in any **App Display Name**
5. Leave **App Contact Email** and **Do you have a Business Manager account?** at defaults
6. Go to your app's **Settings** > **Basic**
7. Click **Add Platform** > **Website** and fill in any **Site URL** (required but unused)
8. Scroll down to **Add Products to Your App**
9. Find **Instagram Basic Display** and click **Set Up**
10. Go to **Instagram Basic Display** > **Basic Display**
11. Scroll down to **User Token Generator** and click **Add or Remove Instagram Testers**
12. Click **Add Instagram Testers** and invite your account
13. Go to [`https://www.instagram.com/accounts/manage_access`](https://www.instagram.com/accounts/manage_access)
14. Switch to **Tester Invites** and accept the invite
15. Go back to the **User Token Generator** and click **Generate Token**
16. Store the token safely, treat it as a personal access token

The token should be valid for **60 days** and can either be refreshed using the
API or a new one may be generated.

## Get the list of your account's media

`https://graph.instagram.com/me?fields=media_count,media&access_token=…`

I've not found a way to return more results on one page, the `limit` parameter
in [this Stack Overflow question](https://stackoverflow.com/a/59830350/2715716)
does not appear to work (for me). The pagination is straightforward though.

## Get individual media by IF

`https://graph.instagram.com/${id}?fields=caption,media_type,media_url,permalink,thumbnail_url,timestamp&access_token=…`

## Instagram Data Takeout

Instagram offers a data takeout feature, but it may take a long time to be ready
and it comes to your mailbox, it doesn't appear to have an API.
