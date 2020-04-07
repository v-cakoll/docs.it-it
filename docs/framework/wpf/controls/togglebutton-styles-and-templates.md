---
title: Stili e modelli di ToggleButton
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: e055dcbd557f9b90eb2fe99ad15a05b6f229fd28
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805919"
---
# <a name="togglebutton-styles-and-templates"></a>Stili e modelli di ToggleButton

In questo argomento vengono descritti <xref:System.Windows.Controls.Primitives.ToggleButton> gli stili e i modelli per il controllo. È possibile modificare <xref:System.Windows.Controls.ControlTemplate> l'impostazione predefinita per conferire al controllo un aspetto univoco. Per ulteriori informazioni, vedere [Creare un modello per un controllo.](../../../desktop-wpf/themes/how-to-create-apply-template.md)

## <a name="togglebutton-parts"></a>Parti ToggleButton

Il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo non dispone di parti denominate.

## <a name="togglebutton-states"></a>Stati ToggleButtonToggleButton States

Nella tabella seguente sono elencati gli stati di visualizzazione per il <xref:System.Windows.Controls.Primitives.ToggleButton> controllo.

|Nome VisualState|Nome VisualStateGroup|Descrizione|
|-|-|-|
|Normale|CommonStates|Lo stato predefinito.|
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|
|Premuto|CommonStates|Il controllo è premuto.|
|Disabled|CommonStates|Il controllo è disabilitato.|
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|
|Selezionato|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `true`.|
|Non selezionato|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `false`.|
|Indeterminato|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> è `true` e <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `null`.|
|Valido|ValidationStates|Il controllo <xref:System.Windows.Controls.Validation> utilizza la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> classe e `false`la proprietà associata è .|
|InvalidFocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.|
|InvalidUnfocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.|

> [!NOTE]
> Se lo stato di visualizzazione Indeterminato non esiste nel modello di controllo, lo stato di visualizzazione Unchecked verrà usato come stato di visualizzazione predefinito.

## <a name="togglebutton-controltemplate-example"></a>Esempio di controllo ToggleButtonToggleButton ControlTemplate Example

Nell'esempio seguente viene <xref:System.Windows.Controls.ControlTemplate> illustrato <xref:System.Windows.Controls.Primitives.ToggleButton> come definire un per il controllo.

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

L'esempio precedente usa una o più delle seguenti risorse.

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](control-styles-and-templates.md)
- [Personalizzazione dei controlli](control-customization.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Creare un modello per un controlloCreate a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md)
