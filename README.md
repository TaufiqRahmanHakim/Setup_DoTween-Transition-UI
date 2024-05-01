# Setup_DoTween-Transition-UI
```csharp
using DG.Tweening;
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class UiTransition : MonoBehaviour
{
    public float fadeTime = 0.5f;
    public CanvasGroup canvasGroup;
    public RectTransform rectTransform;
    public Ease fadeInEase;
    public Ease fadeOutEase;

    public void UiInteractFadeIn()
    {
        canvasGroup.alpha = 0f;
        rectTransform.transform.localPosition = new Vector3(-250f, 0f, 0f);
        rectTransform.DOAnchorPos(new Vector2(0f, 0f), fadeTime, false).SetEase(fadeInEase);
        canvasGroup.DOFade(1, fadeTime);
    }
    public void UiInteractFadeOut()
    {
        canvasGroup.alpha = 1f;
        rectTransform.transform.localPosition = new Vector3(0f, 0f, 0f);
        rectTransform.DOAnchorPos(new Vector2(-250f, 0f), fadeTime, false).SetEase(fadeOutEase);
        canvasGroup.DOFade(1, fadeTime);
    }

}
```
