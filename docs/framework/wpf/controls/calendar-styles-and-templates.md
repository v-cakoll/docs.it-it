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
ms.openlocfilehash: a6f88d3371f4122a11c25a7cdf498f5822420498
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="calendar-styles-and-templates"></a>Stili e modelli di Calendar
In questo argomento vengono descritti gli stili e modelli per il <xref:System.Windows.Controls.Calendar> controllo. È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="calendar-parts"></a>Parti di calendario  
 La tabella seguente elenca le parti denominate la <xref:System.Windows.Controls.Calendar> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|Il mese corrente o l'anno nel <xref:System.Windows.Controls.Calendar>.|  
|PART_Root|<xref:System.Windows.Controls.Panel>|Il pannello che contiene il <xref:System.Windows.Controls.Primitives.CalendarItem>.|  
  
## <a name="calendar-states"></a>Stati di calendario  
 Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.Calendar> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="calendaritem-parts"></a>Parti CalendarItem  
 La tabella seguente elenca le parti denominate la <xref:System.Windows.Controls.Primitives.CalendarItem> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|La radice del controllo.|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|Pulsante che visualizza la pagina precedente del calendario quando viene selezionato.|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|Il pulsante che consente di visualizzare la pagina successiva del calendario quando viene selezionato.|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|Pulsante che consente di passare tra modalità mese, anno e modalità decade.|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|Ospita il contenuto in modalità mensile.|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|Ospita il contenuto in modalità di anno o decennio.|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|Sovrapposizione per lo stato disabilitato.|  
|Oggetto DayTitleTemplate|<xref:System.Windows.DataTemplate>|Il <xref:System.Windows.DataTemplate> che descrive la struttura visiva.|  
  
## <a name="calendaritem-states"></a>Stati CalendarItem  
 Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.Primitives.CalendarItem> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Stato Normal|CommonStates|Lo stato predefinito.|  
|Stato Disabled|CommonStates|Lo stato del calendario quando il <xref:System.Windows.UIElement.IsEnabled%2A> proprietà `false`.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="calendardaybutton-parts"></a>Parti di CalendarDayButton  
 Il <xref:System.Windows.Controls.Primitives.CalendarDayButton> controllo non dispone di parti denominate.  
  
## <a name="calendardaybutton-states"></a>Stati di CalendarDayButton  
 Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.Primitives.CalendarDayButton> controllo.  
  
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
|RegularDay|DayStates|Il pulsante rappresenta <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|Oggi|DayStates|Rappresenta il pulsante <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|NormalDay|BlackoutDayStates|Il pulsante rappresenta un giorno che può essere selezionato.|  
|BlackoutDay|BlackoutDayStates|Il pulsante rappresenta un giorno non può essere selezionato.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="calendarbutton-parts"></a>Parti di CalendarButton  
 Il <xref:System.Windows.Controls.Primitives.CalendarButton> controllo non dispone di parti denominate.  
  
## <a name="calendarbutton-states"></a>Stati di CalendarButton  
 Nella tabella seguente sono elencati gli stati visivi per la <xref:System.Windows.Controls.Primitives.CalendarButton> controllo.  
  
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
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classe e <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="calendar-controltemplate-example"></a>Esempio di ControlTemplate del controllo di calendario  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.Calendar> controllo e i tipi associati.  
  
 [!code-xaml[ControlTemplateExamples#Calendar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
 L'esempio precedente usa una o più delle seguenti risorse.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Stili e modelli di Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Personalizzazione dei controlli](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
