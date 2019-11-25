---
title: Stili e modelli di RepeatButton
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: 8585e98536fd908daa11f21da395cab44924d612
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283420"
---
# <a name="repeatbutton-styles-and-templates"></a>Stili e modelli di RepeatButton

In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Primitives.RepeatButton>. È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).

## <a name="repeatbutton-parts"></a>Parti RepeatButton

Il controllo <xref:System.Windows.Controls.Primitives.RepeatButton> non dispone di parti denominate.

## <a name="repeatbutton-states"></a>Stati di RepeatButton

Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Primitives.RepeatButton>.

|Nome VisualState|Nome VisualStateGroup|description|
|-|-|-|
|Normale|CommonStates|Lo stato predefinito.|
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|
|Premuto|CommonStates|Il controllo è premuto.|
|Disabilitato|CommonStates|Il controllo è disabilitato.|
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|

## <a name="repeatbutton-controltemplate-example"></a>Esempio di ControlTemplate RepeatButton

Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Primitives.RepeatButton>.

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

L'esempio precedente usa una o più delle seguenti risorse.

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](control-styles-and-templates.md)
- [Personalizzazione dei controlli](control-customization.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md)
