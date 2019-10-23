# WobbleTween
Tweening library built for Unity3D, tested with 2019.3beta.   
Originally created by DigitalRuby (https://www.digitalruby.com/unity-plugins/)

## Documentation
### Avaliable Methods
```csharp
FloatTween Tween(object key, float start, float end, float duration, System.Action<ITween<float>> progress = null, System.Action<ITween<float>> completion = null, Func<float, float> ease = null)
```
```csharp
Vector2Tween Tween(object key, Vector2 start, Vector2 end, float duration, System.Action<ITween<Vector2>> progress, System.Action<ITween<Vector2>> completion = null, Func<float, float> ease = null)
```
```csharp
Vector3Tween Tween(object key, Vector3 start, Vector3 end, float duration, System.Action<ITween<Vector3>> progress, System.Action<ITween<Vector3>> completion = null, Func<float, float> ease = null)
```
```csharp
Vector4Tween Tween(object key, Vector4 start, Vector4 end, float duration, System.Action<ITween<Vector4>> progress = null, System.Action<ITween<Vector4>> completion = null, Func<float, float> ease = null)
```
```csharp
ColorTween Tween(object key, Color start, Color end, float duration, System.Action<ITween<Color>> progress = null, System.Action<ITween<Color>> completion = null, Func<float, float> ease = null)
```
```csharp
QuaternionTween Tween(object key, Quaternion start, Quaternion end, float duration, System.Action<ITween<Quaternion>> progress = null, System.Action<ITween<Quaternion>> completion = null, Func<float, float> ease = null)
```
### Usage
```csharp
//From 0 to 10 in 1s
TweenFactory.Tween("", 0f, 10f, 1f, 
    (progress) => {
        Debug.Log(progress.CurrentValue);
    },
    (completion) => {
        Debug.Log("Took 1s");
    }, TweenScaleFunctions.SineEaseInOut);

//Using optional args / different order of args
TweenFactory.Tween("", 0f, 10f, 1f,
    completion: (completion) => {
        Debug.Log("Took 1s");
    },
    progress: (progress) => {
        Debug.Log(progress.CurrentValue);
    }, ease: TweenScaleFunctions.SineEaseInOut);
```
```csharp
//Fade out color
Color faded = spriteRenderer.color;
faded.a = 0f;
TweenFactory.Tween("fadeout", spriteRenderer.color, hoverColor, 1f,
    (progress) => {
        spriteRenderer.color = progress.CurrentValue;
    },
    (completed) => {
        Debug.Log("Done fading");
    }, TweenScaleFunctions.SineEaseInOut);
```

### Avaliable Ease Functions
You can either write your own or use one of the following:
- Linear - A linear progress scale function.
- QuadraticEaseIn - A quadratic (x^2) progress scale function that eases in. 
- QuadraticEaseOut - A quadratic (x^2) progress scale function that eases out.
- QuadraticEaseInOut - A quadratic (x^2) progress scale function that eases in and out.
- CubicEaseIn - A cubic (x^3) progress scale function that eases in.
- CubicEaseOut - A cubic (x^3) progress scale function that eases out
- CubicEaseInOut - A cubic (x^3) progress scale function that eases in and out.
- QuarticEaseIn - A quartic (x^4) progress scale function that eases in.
- QuarticEaseOut - A quartic (x^4) progress scale function that eases out.
- QuarticEaseInOut - A quartic (x^4) progress scale function that eases in and out.
- QuinticEaseIn - A quintic (x^5) progress scale function that eases in.
- QuinticEaseOut - A quintic (x^5) progress scale function that eases out.
- QuinticEaseInOut - A quintic (x^5) progress scale function that eases in and out.
- SineEaseIn - A sine progress scale function that eases in.
- SineEaseOut - A sine progress scale function that eases out.
- SineEaseInOut - A sine progress scale function that eases in and out.
