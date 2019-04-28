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
ms.openlocfilehash: 5c8e199dd7123e1490c8a836a62ffea158797eb8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912249"
---
# <a name="datepicker-styles-and-templates"></a>Stili e modelli di DatePicker
In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.DatePicker> controllo. È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="datepicker-parts"></a>Parti del controllo DatePicker  
 La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.DatePicker> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_Root|<xref:System.Windows.Controls.Grid>|La radice del controllo.|  
|PART_Button|<xref:System.Windows.Controls.Button>|Il pulsante che apre e chiude il <xref:System.Windows.Controls.Calendar>.|  
|PART_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|La casella di testo che consente di immettere una data.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|La finestra popup per la <xref:System.Windows.Controls.DatePicker> controllo.|  
  
## <a name="datepicker-states"></a>Stati del controllo DatePicker  
 La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.DatePicker> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabilitato|CommonStates|Il <xref:System.Windows.Controls.DatePicker> è disabilitato.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="datepickertextbox-parts"></a>Parti DatePickerTextBox  
 La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.Primitives.DatePickerTextBox> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_Watermark|<xref:System.Windows.Controls.ContentControl>|L'elemento che contiene il testo iniziale nel <xref:System.Windows.Controls.DatePicker>.|  
|PART_ContentElement|<xref:System.Windows.FrameworkElement>|Un elemento visivo che può contenere un <xref:System.Windows.FrameworkElement>. Il testo del <xref:System.Windows.Controls.TextBox> viene visualizzato in questo elemento.|  
  
## <a name="datepickertextbox-states"></a>Stati di DatePickerTextBox  
 La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Primitives.DatePickerTextBox> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabilitato|CommonStates|Il <xref:System.Windows.Controls.Primitives.DatePickerTextBox> è disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato il <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|ReadOnly|CommonStates|L'utente non è possibile modificare il testo nel <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
|Transmux|WatermarkStates|Il controllo Visualizza il testo iniziale.  Il <xref:System.Windows.Controls.Primitives.DatePickerTextBox> si trova nello stato quando l'utente non è il testo immesso o selezionato una data.|  
|Unwatermarked|WatermarkStates|L'utente ha immesso testo nel <xref:System.Windows.Controls.Primitives.DatePickerTextBox> selezionato una data o il <xref:System.Windows.Controls.DatePicker>.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="datepicker-controltemplate-example"></a>Esempio di ControlTemplate DatePicker  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.DatePicker> controllo.  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
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
