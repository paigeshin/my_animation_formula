# my_animation_formula

### Scale Boune

```swift
    .scaleEffect(self.animateMeasureScale ? 1.0 : 1.1)
    .animation(.interpolatingSpring(stiffness: 350, damping: 5, initialVelocity: 10).repeatForever(autoreverses: false), value: self.animateMeasureScale)
    .onAppear {
          self.animateMeasureScale.toggle()
    }
```

### Bouncing Wave 

```swift
for (index, _ ) in self.sampleAnalytics.enumerated() {
    withAnimation(.interactiveSpring(response: 0.8, dampingFraction: 0.8, blendDuration: 0.8).delay(Double(index) * 0.05)) {
        self.sampleAnalytics[index].animate = true
    }
}
```

### Graph Animation 

```swift
          for (index, _ ) in self.sampleAnalytics.enumerated() {
                
                // For Some Reason Delay is Not Working
                // Using Dispatch Queue Delay
                DispatchQueue.main.asyncAfter(deadline: .now() + Double(index) * 0.05) {
                    withAnimation(.easeInOut(duration: 0.8)) {
                        self.sampleAnalytics[index].animate = true
                    }
                }
            }
```

```swift
     for (index, _ ) in self.sampleAnalytics.enumerated() {
                
                // For Some Reason Delay is Not Working
                // Using Dispatch Queue Delay
                DispatchQueue.main.asyncAfter(deadline: .now() + Double(index) * 0.05) {
                    withAnimation(.interactiveSpring(response: 0.8, dampingFraction: 0.8, blendDuration: 0.8)) {
                        self.sampleAnalytics[index].animate = true
                    }
                }
            }
```

### Spring

```swift
      .animation(.interpolatingSpring(mass: 1, stiffness: 100, damping: 20, initialVelocity: 0), value: self.show)
```
