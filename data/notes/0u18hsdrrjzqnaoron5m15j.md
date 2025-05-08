
### Schema changes

- Add `status` - `'LIVE' | 'PREV_LIVE' | 'DRAFT'`
- Add `publishedAt` - `Date`
- Remove goLiveDate

### API Changes

- Change the query for fetching the latest doc for a container by leveraging the `status` instead of the `goLiveDate`.

- Update ALL Legal Doc APIs to conform with new schema.

- Update relevant Legal Doc APIs to account for new features - 
    - New PUT `/publish` endpoint that publishes a new legal doc:
        - Only a doc in `DRAFT` mode can be published.
        - Need to mark currently `LIVE` doc as `PREV_LIVE`.
        - Need to update `publishedAt` date.
    - POST endpoint should set the status of the legal doc to `DRAFT`.

