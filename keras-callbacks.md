# Introduction to TensoFlow
## Keras Callbacks
Keras allows us to define callbacks based on an event. During the training, every time the event occurs our callback is invoked. You can actuate on your train in your callback

The following steps are needed
* Define your `class` for your `callback` - `tf.keras.callbacks.Callback`
* Define the event that will invoke your callback - `def on_epoch_end`
* Check a condition. `logs.get()`
* Do something based on the condition

```python
class myCallback(tf.keras.callbacks.Callback):
  def on_epoch_end(self, epoch, logs={}):
    if(logs.get('acc') > 0.99):
      print("Reached 99% accuracy so cancelling training")
      self.model.stop_training = True
      
callbacks = myCallback()

# ...

# Add your callback when you call .fit method
model.fit(x_train, y_train, epochs=5, callbacks = [callbacks])
```
