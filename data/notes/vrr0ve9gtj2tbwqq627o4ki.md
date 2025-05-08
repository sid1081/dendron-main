
Comment: All of the user consent updates happen through the `/consent-status` endpoint.

### Add a new vendor
We pull in all of the categories that the user has consented to and populate all of the vendors for those categories.

### Add a new Opt-Out(DNS or Sensitive Data) IAB or Custom category
- We opt the user in to *any* of these categories.

### Add a new Opt-In IAB or Custom Category
- We don't need to update the user's consent
- _Requires Reconsent_?

### Reconsent flow
- Returning user has a consent record with dateCreated - `2025-03-01`
- Opt-Out IAB Category, Opt-In IAB Category, Opt-In Custom Category were added with additionsChangeDate - `2025-03-04`

#### Date Created holistic or / Category
- This is what we do for GDPR. *Not* an option because consent record needs to be updated if an opt-out category is added which will cause the reconsent flow to break after page refresh.

#### Shown Categories
- Diff between shown opt-in categories and vendor list categories and pass down `reconsent` flag.

#### Rejected Categories
- Store rejected categories 
- Not backwards compatible
