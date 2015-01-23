# Infinario Flash SDK

The `com.infinario.api.Infinario` class provides access to the Infinario
asynchronous ActionScript tracking API. In order to track events, instantiate the
class and call initialize with at least the company token (you can get it when you log in to Infinario), for example:

```ActionScript
import com.infinario.api.Infinario;

var infinario:Infinario = new Infinario();
infinario.initialize({token: '12345678-90ab-cdef-1234-567890abcdef'});
```

## Identifying the customer

When tracking events, you have to specify which customer generated
them. This can be either done right when calling initialize:

```ActionScript
infinario.initialize({token: '12345678-90ab-cdef-1234-567890abcdef', customer: 'john123'});
```

or by calling `identify`.

```ActionScript
infinario.identify('john123');
```

## Tracking events

To track events for the currently selected customer, simply
call the `track` method.

```ActionScript
infinario.track('purchase')
```

You can also specify event properties to store with the event.

```ActionScript
infinario.track('purchase', {'product': 'bottle', 'amount': 5})
```

## Updating customer properties

You can also update information that is stored with a customer.

```ActionScript
infinario.update({'first_name': 'John', 'last_name': 'Smith'})
```

