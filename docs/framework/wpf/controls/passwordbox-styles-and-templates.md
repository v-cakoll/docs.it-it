---
title: Stili e modelli di PasswordBox
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: 4ba90182468466773644c7375059f0cc01675b33
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283470"
---
# <a name="passwordbox-styles-and-templates"></a>Stili e modelli di PasswordBox

In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.PasswordBox>. È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).

## <a name="passwordbox-parts"></a>Parti PasswordBox

Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.PasswordBox>.

|Parte|Digitare|description|
|-|-|-|
|PART_ContentHost|<xref:System.Windows.FrameworkElement>|Elemento visivo che può contenere un <xref:System.Windows.FrameworkElement>. Il testo dell'<xref:System.Windows.Controls.PasswordBox> viene visualizzato in questo elemento.|

## <a name="passwordbox-states"></a>Stati di PasswordBox

Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.PasswordBox>.

|Nome VisualState|Nome VisualStateGroup|description|
|-|-|-|
|Normale|CommonStates|Lo stato predefinito.|
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|
|Disabilitato|CommonStates|Il controllo è disabilitato.|
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|

## <a name="passwordbox-controltemplate-example"></a>Esempio di ControlTemplate PasswordBox

Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.PasswordBox>.

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

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
