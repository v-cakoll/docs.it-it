---
title: Stili e modelli di GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 474cda0abc6a18c015836c749c78f4d33aa5abd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187484"
---
# <a name="groupbox-styles-and-templates"></a>Stili e modelli di GroupBox
<a name="introduction"></a>In questo argomento vengono descritti <xref:System.Windows.Controls.GroupBox> gli stili e i modelli per il controllo. È possibile modificare <xref:System.Windows.Controls.ControlTemplate> l'impostazione predefinita per conferire al controllo un aspetto univoco. Per ulteriori informazioni, vedere [Creare un modello per un controllo.](../../../desktop-wpf/themes/how-to-create-apply-template.md)  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a>Parti di GroupBox  
 Il <xref:System.Windows.Controls.GroupBox> controllo non dispone di parti denominate.  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a>Stati di GroupBox  
 Nella tabella seguente sono elencati gli stati di visualizzazione per il <xref:System.Windows.Controls.GroupBox> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Valido|ValidationStates|Il controllo <xref:System.Windows.Controls.Validation> utilizza la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> classe e `false`la proprietà associata è .|  
|InvalidFocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata ha `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata ha `true` il controllo non ha lo stato attivo.|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a>Esempio di controllo GroupBoxGroupBox ControlTemplate Example  
 Nell'esempio seguente viene <xref:System.Windows.Controls.ControlTemplate> illustrato <xref:System.Windows.Controls.GroupBox> come definire un per il controllo.  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 Utilizza <xref:System.Windows.Controls.ControlTemplate> una o più delle risorse seguenti.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](control-styles-and-templates.md)
- [Personalizzazione dei controlli](control-customization.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Creare un modello per un controlloCreate a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md)
