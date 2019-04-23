---
title: Stili e modelli di Calendar
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Calendar
- templates [WPF], Calendar
- states [WPF], Calendar
- parts [WPF], Calendar
- Calendar [WPF], styles and templates
- ControlTemplate [WPF], Calendar
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
ms.openlocfilehash: 18bef548b11f1a680c1361027b86f6952bedaad0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227118"
---
# <a name="calendar-styles-and-templates"></a>Stili e modelli di Calendar
In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.Calendar> controllo. È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="calendar-parts"></a>Parti del calendario  
 La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.Calendar> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|Il mese attualmente visualizzato o l'anno nel <xref:System.Windows.Controls.Calendar>.|  
|PART_Root|<xref:System.Windows.Controls.Panel>|Il pannello che contiene il <xref:System.Windows.Controls.Primitives.CalendarItem>.|  
  
## <a name="calendar-states"></a>Stati di calendario  
 La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Calendar> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="calendaritem-parts"></a>CalendarItem parti  
 La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.Primitives.CalendarItem> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|La radice del controllo.|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|Il pulsante che consente di visualizzare la pagina di calendario precedente quando viene selezionato.|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|Il pulsante che consente di visualizzare la pagina successiva del calendario quando viene selezionato.|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|Il pulsante che consente di passare tra modalità mese, anno e modalità di dieci anni.|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|Ospita il contenuto in modalità mese.|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|Ospita il contenuto in modalità di anno o un decennio.|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|La sovrimpressione per lo stato disabilitato.|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|Il <xref:System.Windows.DataTemplate> che descrive la struttura visiva.|  
  
## <a name="calendaritem-states"></a>CalendarItem stati  
 La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Primitives.CalendarItem> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Stato Normal|CommonStates|Lo stato predefinito.|  
|Stato Disabled|CommonStates|Lo stato del calendario quando le <xref:System.Windows.UIElement.IsEnabled%2A> è di proprietà `false`.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="calendardaybutton-parts"></a>Parti CalendarDayButton  
 Il <xref:System.Windows.Controls.Primitives.CalendarDayButton> controllo non dispone di parti denominate.  
  
## <a name="calendardaybutton-states"></a>Stati di CalendarDayButton  
 La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Primitives.CalendarDayButton> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabilitato|CommonStates|Il <xref:System.Windows.Controls.Primitives.CalendarDayButton> è disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato il <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Premuto|CommonStates|Il <xref:System.Windows.Controls.Primitives.CalendarDayButton> viene premuto.|  
|Selezionato|SelectionStates|Il pulsante è selezionato.|  
|Deselezionato|SelectionStates|Il pulsante non è selezionato.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Il pulsante ha lo stato attivo.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Il pulsante non è attivo.|  
|Con stato attivo|FocusStates|Il pulsante ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il pulsante non è attivo.|  
|Attivo|ActiveStates|Il pulsante è attivo.|  
|Inattivo|ActiveStates|Il pulsante è inattivo.|  
|RegularDay|DayStates|Non rappresenta il pulsante <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|Oggi|DayStates|Rappresenta il pulsante <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|NormalDay|BlackoutDayStates|Il pulsante rappresenta un giorno che può essere selezionato.|  
|BlackoutDay|BlackoutDayStates|Il pulsante rappresenta un giorno che non può essere selezionato.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="calendarbutton-parts"></a>Parti CalendarButton  
 Il <xref:System.Windows.Controls.Primitives.CalendarButton> controllo non dispone di parti denominate.  
  
## <a name="calendarbutton-states"></a>Stati di CalendarButton  
 La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.Primitives.CalendarButton> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabilitato|CommonStates|Il <xref:System.Windows.Controls.Primitives.CalendarButton> è disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato il <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Premuto|CommonStates|Il <xref:System.Windows.Controls.Primitives.CalendarButton> viene premuto.|  
|Selezionato|SelectionStates|Il pulsante è selezionato.|  
|Deselezionato|SelectionStates|Il pulsante non è selezionato.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Il pulsante ha lo stato attivo.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Il pulsante non è attivo.|  
|Con stato attivo|FocusStates|Il pulsante ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il pulsante non è attivo.|  
|Attivo|ActiveStates|Il pulsante è attivo.|  
|Inattivo|ActiveStates|Il pulsante è inattivo.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="calendar-controltemplate-example"></a>Esempio di ControlTemplate del calendario  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Calendar> controllo e i tipi associati.  
  
 [!code-xaml[ControlTemplateExamples#Calendar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
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
