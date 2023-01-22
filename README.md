# my_animation_formula

### Scale Boune

```swift
    .scaleEffect(self.animateMeasureScale ? 1.0 : 1.1)
    .animation(.interpolatingSpring(stiffness: 350, damping: 5, initialVelocity: 10).repeatForever(autoreverses: false), value: self.animateMeasureScale)
    .onAppear {
          self.animateMeasureScale.toggle()
    }
```
