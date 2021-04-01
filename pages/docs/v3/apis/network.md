---
title: Network Capacitor Plugin API
description: The Network API provides network and connectivity information.
editUrl: https://github.com/ionic-team/capacitor-plugins/blob/main/network/README.md
editApiUrl: https://github.com/ionic-team/capacitor-plugins/blob/main/network/src/definitions.ts
---

# @capacitor/network

The Network API provides network and connectivity information.

## Install

```bash
npm install @capacitor/network
npx cap sync
```

## Example

```typescript
import { Network } from '@capacitor/network';

Network.addListener('networkStatusChange', status => {
  console.log('Network status changed', status);
});

const logCurrentNetworkStatus = async () => {
  const status = await Network.getStatus();

  console.log('Network status:', status);
};
```

## API

<docgen-index>

* [`getStatus()`](#getstatus)
* [`addListener('networkStatusChange', ...)`](#addlistenernetworkstatuschange-)
* [`removeAllListeners()`](#removealllisteners)
* [Interfaces](#interfaces)
* [Type Aliases](#type-aliases)

</docgen-index>

<docgen-api>
<!--Update the source file JSDoc comments and rerun docgen to update the docs below-->

### getStatus()

```typescript
getStatus() => Promise<ConnectionStatus>
```

Query the current status of the network connection.

**Returns:** <code>Promise&lt;<a href="#connectionstatus">ConnectionStatus</a>&gt;</code>

**Since:** 1.0.0

--------------------


### addListener('networkStatusChange', ...)

```typescript
addListener(eventName: 'networkStatusChange', listenerFunc: ConnectionStatusChangeListener) => PluginListenerHandle
```

Listen for changes in the network connection.

| Param              | Type                                                                                      |
| ------------------ | ----------------------------------------------------------------------------------------- |
| **`eventName`**    | <code>'networkStatusChange'</code>                                                        |
| **`listenerFunc`** | <code><a href="#connectionstatuschangelistener">ConnectionStatusChangeListener</a></code> |

**Returns:** <code><a href="#pluginlistenerhandle">PluginListenerHandle</a></code>

**Since:** 1.0.0

--------------------


### removeAllListeners()

```typescript
removeAllListeners() => void
```

Remove all listeners (including the network status changes) for this plugin.

**Since:** 1.0.0

--------------------


### Interfaces


#### ConnectionStatus

Represents the state and type of the network connection.

| Prop                 | Type                                                      | Description                                                                                                                   | Since |
| -------------------- | --------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ----- |
| **`connected`**      | <code>boolean</code>                                      | Whether there is an active connection or not.                                                                                 | 1.0.0 |
| **`connectionType`** | <code><a href="#connectiontype">ConnectionType</a></code> | The type of network connection currently in use. If there is no active network connection, `connectionType` will be `'none'`. | 1.0.0 |


#### PluginListenerHandle

| Prop         | Type                       |
| ------------ | -------------------------- |
| **`remove`** | <code>() =&gt; void</code> |


### Type Aliases


#### ConnectionType

The type of network connection that a device might have.

<code>'wifi' | 'cellular' | 'none' | 'unknown'</code>


#### ConnectionStatusChangeListener

Callback to receive the status change notifications.

<code>(status: <a href="#connectionstatus">ConnectionStatus</a>): void</code>

</docgen-api>