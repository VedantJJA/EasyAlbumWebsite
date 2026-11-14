# EasyAlbum App Domain site

This is one static site. Serve this folder over HTTPS on a public domain you control.

## Host with Cloudflare Pages

1. In Cloudflare, open **Workers & Pages → Create application → Get started → Drag and drop your files**. Choose a project name and upload this folder. Make sure `index.html` sits at the deployment root, next to `privacy.html`, `terms.html`, and `assets/`. The `pages.dev` URL lets you check the upload. [Direct Upload](https://developers.cloudflare.com/pages/get-started/direct-upload/)
2. Open the Pages project’s **Custom domains** tab and select **Set up a custom domain**. Use a subdomain you control, such as `albums.your-domain.example`. Follow the dashboard’s DNS instructions. With an external DNS provider, add the CNAME Cloudflare supplies after adding the hostname in Pages. [Custom domains](https://developers.cloudflare.com/pages/configuration/custom-domains/)
3. Once HTTPS works, open all three pages using that custom hostname. Verify domain ownership in Google Search Console with an account that owns or edits the Google Cloud project. Enter the live URLs in **Google Auth Platform → Branding**. [OAuth branding requirements](https://support.google.com/cloud/answer/15549049)

| Google Auth Platform → Branding field | URL |
| --- | --- |
| Application home page | https://your-domain.example/ |
| Application privacy policy link | https://your-domain.example/privacy.html |
| Application terms of service link | https://your-domain.example/terms.html |
| Authorized domains | your-domain.example |

The domain above is an example. Add your actual domain and verify ownership using Google Search Console. Use the same privacy policy URL on the homepage and in the OAuth settings.

Cloudflare Pages serves the two policy pages at `/privacy` and `/terms`. If Cloudflare redirects the `.html` URLs, enter the final URLs shown in the browser. [Cloudflare route matching](https://developers.cloudflare.com/pages/configuration/serving-pages/#route-matching)

The policy and terms point readers to the support email on the app's consent screen. Review the copy and confirm that the support address is monitored before publishing. The Android app and backend are separate from this informational site.

The homepage uses EasyAlbum's existing sample album imagery.
