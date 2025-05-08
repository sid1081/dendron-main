
# Implementing auth consent for preferences

## /GET Consent status flow
- if valid `authId` present
    - if `uuidGenerated`
        - get `authMapping(uuid)` by `authId`
        - set the preference `uuid` value in local-storage.
            - If no authMapping
                - we don't neede to call get user consent.
            - Else if authMapping 
                - get the user consent for this  `uuid` since it might have changed on another device.
    - else if a `uuid` was passed and it *wasn't* generated
        - get `authMapping(uuid)` by `authId`
            - if *no* `authMapping` exists for this `authId`, 
                - then *create* the `authMapping` record to store this new mapping between the `authId` and the `uuid`.
                - get the user consent for this `uuid` since it might have changed on some other device.
            - else if `authMapping` exists 
                - if `linkedUuid` is the same
                    - if `localData` is current then short circuit
                    - else if `localData` is *not* current. _Does this happen through the VL?_
                        - get the user consent for this `uuid` since it might have changed on some other device.
                - else if `linkedUuid` is *not* the same
                    - get the user consent for this new `uuid` since it might have changed on another device. We use the linked UUID to fetch the consent data since that is the latest uuid that might have newer changes.
                    - set the preference `uuid` value in local-storage
- else
    - Nothing to do.


## /POST preference flow
- if valid `authId` and `uuid` present, then create `user preference` and `authMapping`.O

## Open Questions
- Why are we checking to see if the uuids are the same for the short circuit?