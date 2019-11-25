---
title: Stili e modelli di DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
ms.openlocfilehash: 002d1c3271827239dcd3a319621f66fb5bc68d4e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283779"
---
# <a name="datepicker-styles-and-templates"></a>Stili e modelli di DatePicker
In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.DatePicker>. È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco. Per altre informazioni, vedere [creare un modello per un controllo](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="datepicker-parts"></a>Parti DatePicker  
 Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.DatePicker>.  
  
|Parte|Digitare|description|  
|-|-|-|  
|PART_Root|<xref:System.Windows.Controls.Grid>|Radice del controllo.|  
|PART_Button|<xref:System.Windows.Controls.Button>|Pulsante che consente di aprire e chiudere la <xref:System.Windows.Controls.Calendar>.|  
|PART_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|Casella di testo che consente di immettere una data.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Popup per il controllo <xref:System.Windows.Controls.DatePicker>.|  
  
## <a name="datepicker-states"></a>Stati DatePicker  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.DatePicker>.  
  
|Nome VisualState|Nome VisualStateGroup|description|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabilitato|CommonStates|Il <xref:System.Windows.Controls.DatePicker> è disabilitato.|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
  
## <a name="datepickertextbox-parts"></a>Parti DatePickerTextBox  
 Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.  
  
|Parte|Digitare|description|  
|-|-|-|  
|PART_Watermark|<xref:System.Windows.Controls.ContentControl>|Elemento contenente il testo iniziale nel <xref:System.Windows.Controls.DatePicker>.|  
|PART_ContentElement|<xref:System.Windows.FrameworkElement>|Elemento visivo che può contenere un <xref:System.Windows.FrameworkElement>. Il testo dell'<xref:System.Windows.Controls.TextBox> viene visualizzato in questo elemento.|  
  
## <a name="datepickertextbox-states"></a>Stati DatePickerTextBox  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.  
  
|Nome VisualState|Nome VisualStateGroup|description|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabilitato|CommonStates|Il <xref:System.Windows.Controls.Primitives.DatePickerTextBox> è disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse viene posizionato sul <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|ReadOnly|CommonStates|L'utente non può modificare il testo nel <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
|Filigranata|WatermarkStates|Il controllo Visualizza il testo iniziale.  Il <xref:System.Windows.Controls.Primitives.DatePickerTextBox> si trova nello stato quando l'utente non ha immesso il testo o ha selezionato una data.|  
|Con filigrana|WatermarkStates|L'utente ha immesso il testo nella <xref:System.Windows.Controls.Primitives.DatePickerTextBox> o ha selezionato una data nel <xref:System.Windows.Controls.DatePicker>.|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` e il controllo non ha lo stato attivo.|  
  
## <a name="datepicker-controltemplate-example"></a>Esempio di ControlTemplate DatePicker  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.DatePicker>.  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
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
