# analytics.js-integration-wishpond [![Build Status][ci-badge]][ci-link]

Wishpond integration for [Analytics.js][].

This integration is maintained by Anderson Saunders.

Our Wishpond integration code is open sourced on Github. Feel free to check it out: [JavaScript (browser) Integration](https://github.com/wishpond-dev/analytics.js-integration-wishpond "Wishpond Segment Integration").

## Getting Started

Wishpond works with our client-side javascript library: Analytics.js.

From your Segment Integrations page click on Wishpond. Drop in your API keys from Wishpond’s [“API Keys” dialog](https://www.wishpond.com/central/welcome?api_keys=true), also found in your Wishpond Account in the dropdown on your account name in the top right corner then API Keys.

We’ll automatically initialize Wishpond’s Tracking Code with your API Keys upon loading Analytics.js.

When you toggle on Wishpond in Segment your Wishpond account will start to receive data when you use `identify` or `track` methods.

## Identify

When you `identify` a user, we'll pass that user's information to Wishpond. Wishpond Tracking Code, method identify, will be triggered with the params used to identify.

For instance, when Segment identify get called:

```
analytics.identify('1e810c197e', {
  name: 'Bill Lumbergh',
  email: 'bill@initech.com'
});
```

Wishpond Tracker will be called with the following parameters:

```
Wishpond.Tracker.identify('1e810c197e', {
  name: 'Bill Lumbergh',
  email: 'bill@initech.com'
});
 ```

A new lead will be created be in your 'Wishpond Leads Database'. The lead will have the attributes: name 'Bill Lumbergh', email 'bill@initech.com'.
To more details how Wishpond's identify works please visit [Wishpond API Docs: #identify](http://developers.wishpond.com/#identify).

## Track

When you `track` an event, we will send that event to Wishpond. Wishpond Tracking Code, method track, will be triggered with the params used to track the event.

For instance, when Segment track get called:

```
analytics.track('Signed Up', {
  plan: 'Startup',
  source: 'Analytics Academy'
});});
```

Wishpond Tracker will be called with the following parameters:

```
Wishpond.Tracker.track('Signed Up', {
  plan: 'Startup',
  source: 'Analytics Academy'
});
 ```

A new event will be added to the lead that the current session is tracking. The event title will be 'Signed Up', and it will have the properties: plan: 'Startup',source: 'Analytics Academy'.

To more details how Wishpond's identify works please visit [Wishpond API Docs: #track](http://developers.wishpond.com/#tracking-events).

- - -
## Troubleshooting/ FAQ

### Integration is not working properly

Make sure you have copied the right keys from Wishpond’s [“API Keys” dialog](https://www.wishpond.com/central/welcome?api_keys=true), this integration will need `Merchant ID` and `Tracking Key`.

## License

Released under the [MIT license](License.md).


[Analytics.js]: https://segment.com/docs/libraries/analytics.js/
[ci-link]: https://circleci.com/gh/segment-integrations/analytics.js-integration-wishpond
[ci-badge]: https://circleci.com/gh/segment-integrations/analytics.js-integration-wishpond.svg?style=svg
