# Push Notification Instructions
1. Currently integrates Xiaomi, Huawei, and Meizu push notifications. Developers can integrate other push services themselves. On Xiaomi, Huawei, and Meizu phones, each uses their own push service; other phones use Xiaomi push.
2. The keys in the project are for testing purposes only. Developers need to apply for their own keys.

## Xiaomi Push
1. Xiaomi supports both pass-through and notification bar push. Currently, VoIP-related messages use pass-through push, while other messages use notification bar push. The differences between pass-through and notification bar are as follows:

  |            | Pass-through Push                       | Notification Bar Push                   |
  | ---------- | --------------------------------------- | --------------------------------------- |
  | Auto-start allowed | No notification shown, but wakes up app | Shows notification and wakes up app     |
  | Auto-start disabled | No notification shown, doesn't wake app | Shows notification, but doesn't wake app |

2. When auto-start is allowed and notification bar push is used, notifications may appear duplicated

## Huawei Push

TODO

## Meizu Push

TODO
