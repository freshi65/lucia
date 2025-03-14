# lucia-auth

## 1.6.0

### Minor changes

- [#626](https://github.com/pilcrowOnPaper/lucia/pull/626) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : `web()` middleware can take `Headers` or `Response`

- [#626](https://github.com/pilcrowOnPaper/lucia/pull/626) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Add `nextjs()` middleware

### Patch changes

- [#626](https://github.com/pilcrowOnPaper/lucia/pull/626) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Fix Express middleware returning broken url

## 1.5.0

### Minor changes

- [#567](https://github.com/pilcrowOnPaper/lucia/pull/567) by [@gustavocadev](https://github.com/gustavocadev) : Add `qwik()` middleware

- [#553](https://github.com/pilcrowOnPaper/lucia/pull/553) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Add `web()` middleware

## 1.4.0

### Minor changes

- [#539](https://github.com/pilcrowOnPaper/lucia/pull/539) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Update adapter specification

  - `setUser()` may return `void`

### Patch changes

- [#546](https://github.com/pilcrowOnPaper/lucia/pull/546) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Fix types issue with `Auth.handleRequest()`

## 1.3.0

### Minor changes

- [#525](https://github.com/pilcrowOnPaper/lucia/pull/525) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Update `Middleware`

  - Fix `node` middleware returning incorrect url

- [#529](https://github.com/pilcrowOnPaper/lucia/pull/529) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Update adapter requirements

  - Removed: `UserAdapter.updateUserAttributes()` should validate provided user id

  - `UserAdapter.updateUserAttributes()` may throw `AUTH_INVALID_USER_ID`

  - `UserAdapter.updateUserAttributes()` should return `void` or `UserSchema`

  - Removed: `UserAdapter.updateKeyPassword()` should validate provided key id

  - `UserAdapter.updateKeyPassword()` may throw `AUTH_INVALID_KEY_ID`

  - `UserAdapter.updateKeyPassword()` should return `void` or `KeySchema`

  - UserAdapter: `UserAdapter.getKey()` should delete single use keys with `shouldDataBeDeleted()`

  - `UserAdapter.setUser()` should use transactions or batch queries to store the user and key

### Patch changes

- [#529](https://github.com/pilcrowOnPaper/lucia/pull/529) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Remove unnecessary generic from `AuthRequest`

- [#531](https://github.com/pilcrowOnPaper/lucia/pull/531) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Remove `console.log()`

- [#535](https://github.com/pilcrowOnPaper/lucia/pull/535) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Fix hashing function

## 1.2.2

### Patch changes

- [#521](https://github.com/pilcrowOnPaper/lucia/pull/521) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Improve `crypto` polyfill

## 1.2.1

### Patch changes

- [#516](https://github.com/pilcrowOnPaper/lucia/pull/516) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Fix broken import

## 1.2.0

### Minor changes

- [#510](https://github.com/pilcrowOnPaper/lucia/pull/510) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Add `lucia-auth/polyfill/node`

  - Remove Node dependency

## 1.1.0

### Minor changes

- [#505](https://github.com/pilcrowOnPaper/lucia/pull/505) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : `generateRandomString()` takes an optional second parameter - alphabet

  - Remove `nanoid` dependency

## 1.0.0

### Major changes

- [#443](https://github.com/pilcrowOnPaper/lucia/pull/443) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : [Breaking] Update `UserSchema`

  - [Breaking] Remove type `UserData`

- [#443](https://github.com/pilcrowOnPaper/lucia/pull/443) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Release version 1.0!

- [#443](https://github.com/pilcrowOnPaper/lucia/pull/443) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : [Breaking] Rename `transformUserData()` to `transformDatabaseUser()`

  - Expose `transformDatabaseUser()`

- [#443](https://github.com/pilcrowOnPaper/lucia/pull/443) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : [Breaking] Set default middleware to `lucia` - Add `lucia` middleware

- [#443](https://github.com/pilcrowOnPaper/lucia/pull/443) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : [Breaking] Invalidate user cache on `AuthRequest.setSession()`

## 0.11.0

### Minor changes

- [#430](https://github.com/pilcrowOnPaper/lucia/pull/430) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : [Breaking] Rename properties

  - Rename `SingleUseKey.expires` to `SingleUserKey.expiresAt`, `SingleUseKey.isExpired` to `SingleUserKey.expired`, `SingleUseKey.isPasswordDefined` to `SingleUseKey.passwordDefined`

  - Rename `PersistentKey.isPasswordDefined` to `PersistentKey.passwordDefined`

  - Rename `Session.isFresh` to `Session.fresh`, `Session.idlePeriodExpires` to `Session.idlePeriodExpiresAt`, `Session.activePeriodExpires` to `Session.activePeriodExpiresAt`

  - Rename `Configuration.sessionTimeout` to `Configuration.sessionExpiresIn`

  - Update `Auth.createKey()`

- [#430](https://github.com/pilcrowOnPaper/lucia/pull/430) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Introduce middleware

  - [Breaking] Rename `Auth.validateRequestHeaders()` to `Auth.parseRequestHeaders()`

  - [Breaking] Replace `Auth.createSessionCookies()` with `Auth.createSessionCookie()`

  - [Breaking] `Configuration.sessionCookie` expects an object

  - Add `origin` config

- [#430](https://github.com/pilcrowOnPaper/lucia/pull/430) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : [Breaking] Update schema

  - Rename `Key.primary` to `Key.primary_key`

## 0.10.0

### Minor changes

- [#424](https://github.com/pilcrowOnPaper/lucia/pull/424) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Fix issues with single use keys

  - [Breaking] Update `createKey()`

- [#424](https://github.com/pilcrowOnPaper/lucia/pull/424) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Replace `Token.isExpired()` with `Token.isExpired`

## 0.9.1

### Patch changes

- [#415](https://github.com/pilcrowOnPaper/lucia/pull/415) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Fix adapter config

## 0.9.0

### Minor changes

- [#398](https://github.com/pilcrowOnPaper/lucia/pull/398) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : **Breaking changes** Better integrate single use keys and clean up APIÏ

  - Update `Key` type

  - Remove `getKeyUser()`

  - Replace `validateKeyPassword()` with `useKey()`

  - Replace `data.key` with `data.primaryKey` for `createUser()`

  - Update `createKey()`

  - `getAllUserKeys()` returns all keys, including those expired

## 0.8.0

### Minor changes

- [#392](https://github.com/pilcrowOnPaper/lucia/pull/392) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : [Breaking] Rename type `Configurations` to `Configuration`

  [Breaking] Attempting to use an expired key throws `AUTH_EXPIRED_KEY`

## 0.7.3

### Patch changes

- [#388](https://github.com/pilcrowOnPaper/lucia/pull/388) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : remove unnecessary code

## 0.7.2

### Patch changes

- [#381](https://github.com/pilcrowOnPaper/lucia/pull/381) by [@pilcrowOnPaper](https://github.com/pilcrowOnPaper) : Update links in README and package.json

## 0.7.1

- [Fix] update parameters for `createKey`, `createUser`

## 0.7.0

- [Feat] One time keys

- [Breaking] Update `KeySchema`, `UserAdapter`

- [Fix] `getAllUserSessions` only returns active or idle sessions

- Update type `Key`

## 0.6.2

- [Fix] Allow character `:` in provider user id

## 0.6.1

- [Fix] `validateKeyPassword` types

## 0.6.0

- [Breaking] Update `UserAdapter`

- [Breaking] Rename `AUTH_INVALID_KEY` to `AUTH_INVALID_KEY_ID`, `AUTH_DUPLICATE_KEY` to `AUTH_DUPLICATE_KEY_ID`

- [Breaking] `configuration.generateCustomUserId` must return a `string`

- [Fix] `createUser` checks for key id validity before user creation

## 0.5.0

- [Feat] Add keys

- [Breaking] Remove: `getUserByProviderId`, `updateUserProviderId`, `authenticateUser`, `updateUserPassword`

- [Breaking] Change parameters for `createUser`

- [Breaking] Remove error message: `AUTH_INVALID_PROVIDER_ID`, `AUTH_DUPLICATE_PROVIDER_ID`

- [Breaking] Remove `/adapter`

- [Breaking] Rename `session` table column `expires` to `active_expires`

- [Breaking] Lucia will generate its own user id by default (15 chars long)

- [Breaking] Update type `UserAdapter` and `Adapter`

- Allow `config.generateCustomUserId` to be synchronous

## 0.4.3

- Expose type `ENV`

## 0.4.2

- Type `UserSchema` includes any key/values

- Allow type `bigint` for `idle_expires`, `expires` in type `SessionSchema`

## 0.4.1

- `options` parameter for `createUser` is only necessary if `Lucia.UserAttributes` has keys

- `options.attributes` parameter for `createUser` is only required if `Lucia.UserAttributes` has keys

## 0.4.0

- [Breaking] Adapters are now functions that return the `Adapter` object

- Export type `LuciaErrorConstructor`, `AdapterFunction`

## 0.3.4

- Add `AUTO_USER_ID_GENERATION_NOT_SUPPORTED` error

## 0.3.3

- [Fix] Get proper types for `User`

## 0.3.2

- Export `Configurations` type

## 0.3.1

- [Fix] Return type for `lucia`

## 0.3.0

- [Breaking] `getSession` returns both active and idle sessions

- [Breaking] `Session.expires`, `Session.idlePeriodExpires` are `Date` objects

- [Breaking] `renewSession`, `validateSession`, `validateSessionUser` no longer sets session cookie using the provided function parameter

- [Breaking] Rename `Cookie.options` to `Cookie.attributes`

- [Breaking] Rename `Session.expires` to `Session.activePeriodExpires`

- [Breaking] Rename `Config.sessionTimeout` to `Config.sessionTimeout.activePeriod`, `Config.idlePeriodTimeout` to `Config.sessionTimeout.idlePeriod`

- [Breaking] Remove `Config.deleteCookieOption`

- [Breaking] Rename `Config.sessionCookieOption` to `Config.sessionCookie`

- `getSession`, `getSessionUser`, `renewSession`, `validateSessionUser`, `validateSession` deletes the target session from the database if dead by default

- `updateUserProviderId`, `updateUserAttributes`, `createSession` deletes the target user's dead sessions from the database by default

- Add `state`, `isFresh` property to `Session`

- Add `autoDatabaseCleanup` config

## 0.2.2

- [Fix] Ignore `getSessionAndUserBySessionId` if a normal adapter is provided as a user or session adapter

## 0.2.1

- Remove node dependencies (`crypto`, `util`) [#236](https://github.com/pilcrowOnPaper/lucia/issues/236)

- Adds `@noble/hashes` as dependency

- Use block size (`r`) of `16` for hashing passwords with scrypt

- Add `configs.hash.generate` and `configs.hash.validate` for custom hashing implementation

- Normalize password string on hashing

## 0.2.0

- [Breaking] Remove `validateRequest` and `getSessionUserFromRequest`

- [Breaking] Replace `parseRequest` with `validateRequestHeaders`

- [Breaking] `renewSession` requires `setSessionCookie` param and sets cookies

- [Breaking] `validateSession` renews idle sessions

- [Breaking] `getSessionUser` no longers renews idle sessions

- Add `validateSessionUser`, `getSession`, `getSessionUser`, `SESSION_COOKIE_NAME`

## 0.1.4

- [Breaking] Params for `setCookie` params for `validateRequest` and `getSessionUserFromRequest` is now `Session | null` instead of a `string`

- [Breaking] `createSessionCookies`^ returns an array of `Cookie`

- [Breaking] Remove `createBlankSessionCookies`

## 0.1.3

- Export `Lucia.Auth` and `Lucia.UserAttributes`

- Remove `cookie` and `cli-color` dependency

## 0.1.2

- [Breaking] `validateRequest` requires `setCookie` parameter

- Add `getSessionUserFromRequest`

## 0.1.1

- Make input type of request for `parseRequest` and `validateRequest` as minimal as possible
