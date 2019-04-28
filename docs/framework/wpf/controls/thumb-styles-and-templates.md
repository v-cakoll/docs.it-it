---
title: Stili e modelli di Thumb
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
ms.openlocfilehash: b7fc595f0c592d42f118c6b5542edf93716c2fca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790780"
---
# <a name="thumb-styles-and-templates"></a>Stili e modelli di Thumb

In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.Primitives.Thumb> controllo. È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).

## <a name="thumb-parts"></a>Parti di Thumb

Il <xref:System.Windows.Controls.Primitives.Thumb> controllo non dispone di parti denominate.

## <a name="thumb-states"></a>Stati di Thumb

La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Primitives.Thumb> controllo.

|Nome VisualState|Nome VisualStateGroup|Descrizione|
|-|-|-|
|Normale|CommonStates|Lo stato predefinito.|
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|
|Premuto|CommonStates|Il controllo è premuto.|
|Disabilitato|CommonStates|Il controllo è disabilitato.|
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|

## <a name="thumb-controltemplate-example"></a>Esempio di ControlTemplate Thumb

Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Primitives.Thumb> controllo.

[!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]

L'esempio precedente usa una o più delle seguenti risorse.

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](control-styles-and-templates.md)
- [Personalizzazione dei controlli](control-customization.md)
- [Applicazione di stili e modelli](styling-and-templating.md)
- [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
