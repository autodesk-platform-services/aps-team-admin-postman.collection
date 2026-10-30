# Postman collection for the Team Admin API

[![Postman](https://img.shields.io/badge/Postman-v8-orange.svg)](https://www.getpostman.com/)
[![Team Admin API](https://img.shields.io/badge/Team%20Admin%20API-v1%20Public%20Beta-green.svg)](https://aps.autodesk.com/en/docs/team_admin/v1/tutorials/get-started/)
![Beginner](https://img.shields.io/badge/Level-Beginner-green.svg)
[![License](https://img.shields.io/:license-MIT-blue.svg)](http://opensource.org/licenses/MIT)

The Team Admin API lets you discover the Autodesk teams you administer, view and invite team members, explore product pools, and manage direct product assignments. This repository provides a Postman collection with pre-populated requests so you can try the API without writing code.

## Requests

| Folder | Requests |
| --- | --- |
| Teams | List administered teams |
| Team users | List, get, find by exact email, add (invite) |
| Product pools | List product pools |
| Assignments | List, list by user, find user/product assignment, assign product, unassign product |

## Get started

1. Import `Team Admin API - Public Beta.postman_collection.json` into [Postman](https://www.postman.com/downloads/).
2. Create an app on the [APS portal](https://get-started.aps.autodesk.com/?check_logged_in=1#create-an-account) and register the callback URL `https://oauth.pstmn.io/v1/browser-callback`.
3. In the collection **Variables** tab, set `client_id` and `client_secret`.
4. In the collection **Authorization** tab, select **Get New Access Token**, sign in with an account that administers the team, then select **Use Token**. The API requires a three-legged token (OAuth 2.0 Authorization Code). Application-only tokens aren't accepted.
5. Send **List Administered Teams** and set `team_id` to a returned `id`. Set `user_id` and `product_id` from the user and product pool lists.

Requests in the Team users and Assignments folders that use `lookup_email`, `invite_email`, `user_id` or `product_id` read those collection variables.

## Notes

- The `url` variable defaults to `https://developer.api.autodesk.com`. Update it if you are targeting another environment.
- The default `scope` covers all requests. For read-only access, set it to `tmadmapi:team:read`.
- Add team user, assign product and unassign product change real data. For a read-only Collection Runner run, select only GET requests.
- List endpoints for teams, users and product pools return one page per request. Enable the `cursor` query parameter and pass the returned `pagination.cursor` (URL-encoded) to get the next page. Assignment lists aren't paginated.

## Resources

- [Get started with the Team Admin API](https://aps.autodesk.com/en/docs/team_admin/v1/tutorials/get-started/)

## License

This collection is licensed under the terms of the [MIT License](http://opensource.org/licenses/MIT). See the [LICENSE](LICENSE) file for details.

## Written by

Joao Martins [in/jpornelas](https://linkedin.com/in/jpornelas), [Developer Advocate](http://aps.autodesk.com)