# eclipse_bluechi.bluechi.common role

The `common` role handles common tasks required by the `controller` and `agent` roles

## Requirements

### Installing on RHEL

When installing on RHEL, the machine should already be subscribed using the `subscription-manager`.

In addition, make sure to enable the Subscription-Manager Repository:
```
subscription-manager config --rhsm.manage_repos=1
```

