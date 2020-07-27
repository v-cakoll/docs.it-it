---
title: Stili e modelli di TextBox
description: Informazioni sugli stili e i modelli per il controllo TextBox Windows Presentation Foundation. Modificare il ControlTemplate per dare al controllo un aspetto univoco.
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 0e15fd40f5590ee46da49cc6c0d5fb30e051f7e4
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164725"
---
# <a name="textbox-styles-and-templates"></a>Stili e modelli di TextBox
In questo argomento vengono descritti gli stili e i modelli per il <xref:System.Windows.Controls.TextBox> controllo. È possibile modificare l'impostazione predefinita <xref:System.Windows.Controls.ControlTemplate> per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="textbox-parts"></a>Parti casella di testo  
 Nella tabella seguente sono elencate le parti denominate per il <xref:System.Windows.Controls.TextBox> controllo.  
  
|Parte|Type|Descrizione|  
|-|-|-|  
|PART_ContentHost|<xref:System.Windows.FrameworkElement>|Elemento visivo che può contenere un oggetto <xref:System.Windows.FrameworkElement> . Il testo di <xref:System.Windows.Controls.TextBox> viene visualizzato in questo elemento.|  
  
## <a name="textbox-states"></a>Stati TextBox  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il <xref:System.Windows.Controls.TextBox> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|  
|Disabled|CommonStates|Il controllo è disabilitato.|  
|ReadOnly|CommonStates|L'utente non può modificare il testo in <xref:System.Windows.Controls.TextBox> .|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
|Valido|ValidationStates|Il controllo Usa la <xref:System.Windows.Controls.Validation> classe e la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false` .|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> controllo ha lo stato attivo per la proprietà associata `true` .|  
|InvalidUnfocused|ValidationStates|Il controllo non ha lo <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> stato attivo per la proprietà associata `true` .|  
  
## <a name="textbox-controltemplate-example"></a>Esempio di ControlTemplate TextBox  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.TextBox> controllo.  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
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
