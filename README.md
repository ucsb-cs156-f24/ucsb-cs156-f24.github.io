# ucsb-cs156-m23.github.io
Default page for organization

# storybook

This repo can serve as a source for mockServiceWorker.js for storybooks in organization github pages

# Instructions

1. Add this repo to your organization
2. In the storybooks, the `frontend/.storybook/preview.js` file should contain this code:
   ```js
    const currentUrl = window.location.href;
    const isLocalhost = currentUrl.startsWith("http://localhost:6006/");
    const mockServiceWorkerUrl = isLocalhost ? "mockServiceWorker.js" : "https://" + window.location.hostname + "/mockServiceWorker.js";
    
    initialize(
      {
        serviceWorker: {
          url: mockServiceWorkerUrl
        }
      }
    );
   ```

   This serves the `mockServiceWorker.js` file from `/` on localhost, while serving it from this repo
   when the pages are hosted on the github pages host associated with the organization.
3. Enable github pages on the main branch of this repo.
