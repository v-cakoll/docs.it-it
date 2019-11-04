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
ms.openlocfilehash: 49d9ced42572ac06a4ff824ec41a59c14497d215
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460934"
---
# <a name="calendar-styles-and-templates"></a>Stili e modelli di Calendar
In questo argomento vengono descritti gli stili e i modelli per il controllo <xref:System.Windows.Controls.Calendar>. È possibile modificare il <xref:System.Windows.Controls.ControlTemplate> predefinito per dare al controllo un aspetto univoco. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="calendar-parts"></a>Parti del calendario  
 Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.Calendar>.  
  
|Parte|Digitare|Descrizione|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|Mese o anno attualmente visualizzato nel <xref:System.Windows.Controls.Calendar>.|  
|PART_Root|<xref:System.Windows.Controls.Panel>|Pannello che contiene il <xref:System.Windows.Controls.Primitives.CalendarItem>.|  
  
## <a name="calendar-states"></a>Stati del calendario  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Calendar>.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
  
## <a name="calendaritem-parts"></a>Parti CalendarItem  
 Nella tabella seguente sono elencate le parti denominate per il controllo <xref:System.Windows.Controls.Primitives.CalendarItem>.  
  
|Parte|Digitare|Descrizione|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|Radice del controllo.|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|Pulsante che visualizza la pagina precedente del calendario quando viene selezionato.|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|Pulsante che visualizza la pagina successiva del calendario quando viene selezionato.|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|Pulsante che consente di passare tra la modalità mese, la modalità anno e la modalità decade.|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|Ospita il contenuto in modalità mese.|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|Ospita il contenuto in modalità anno o decade.|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|Sovrapposizione per lo stato disabilitato.|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|<xref:System.Windows.DataTemplate> che descrive la struttura visiva.|  
  
## <a name="calendaritem-states"></a>Stati CalendarItem  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Primitives.CalendarItem>.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Stato normale|CommonStates|Lo stato predefinito.|  
|Stato disabilitato|CommonStates|Stato del calendario quando la proprietà <xref:System.Windows.UIElement.IsEnabled%2A> è `false`.|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
  
## <a name="calendardaybutton-parts"></a>Parti CalendarDayButton  
 Il controllo <xref:System.Windows.Controls.Primitives.CalendarDayButton> non dispone di parti denominate.  
  
## <a name="calendardaybutton-states"></a>Stati CalendarDayButton  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Primitives.CalendarDayButton>.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabilitato|CommonStates|Il <xref:System.Windows.Controls.Primitives.CalendarDayButton> è disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse viene posizionato sul <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Premuto|CommonStates|Viene premuto il <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Selezionati|SelectionStates|Il pulsante è selezionato.|  
|Deselezionato|SelectionStates|Il pulsante non è selezionato.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Il pulsante ha lo stato attivo.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Il pulsante non ha lo stato attivo.|  
|Con stato attivo|FocusStates|Il pulsante ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il pulsante non ha lo stato attivo.|  
|Attivo|ActiveStates|Il pulsante è attivo.|  
|Inattivo|ActiveStates|Il pulsante è inattivo.|  
|RegularDay|DayStates|Il pulsante non rappresenta <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|Oggi|DayStates|Il pulsante rappresenta <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|NormalDay|BlackoutDayStates|Il pulsante rappresenta un giorno selezionabile.|  
|BlackoutDay|BlackoutDayStates|Il pulsante rappresenta un giorno che non può essere selezionato.|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
  
## <a name="calendarbutton-parts"></a>Parti CalendarButton  
 Il controllo <xref:System.Windows.Controls.Primitives.CalendarButton> non dispone di parti denominate.  
  
## <a name="calendarbutton-states"></a>Stati CalendarButton  
 Nella tabella seguente sono elencati gli Stati di visualizzazione per il controllo <xref:System.Windows.Controls.Primitives.CalendarButton>.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|Disabilitato|CommonStates|Il <xref:System.Windows.Controls.Primitives.CalendarButton> è disabilitato.|  
|MouseOver|CommonStates|Il puntatore del mouse viene posizionato sul <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Premuto|CommonStates|Viene premuto il <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Selezionati|SelectionStates|Il pulsante è selezionato.|  
|Deselezionato|SelectionStates|Il pulsante non è selezionato.|  
|CalendarButtonFocused|CalendarButtonFocusStates|Il pulsante ha lo stato attivo.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|Il pulsante non ha lo stato attivo.|  
|Con stato attivo|FocusStates|Il pulsante ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il pulsante non ha lo stato attivo.|  
|Attivo|ActiveStates|Il pulsante è attivo.|  
|Inattivo|ActiveStates|Il pulsante è inattivo.|  
|Valido|ValidationStates|Il controllo Usa la classe <xref:System.Windows.Controls.Validation> e la proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non ha lo stato attivo.|  
  
## <a name="calendar-controltemplate-example"></a>Esempio di ControlTemplate del calendario  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il controllo <xref:System.Windows.Controls.Calendar> e i tipi associati.  
  
 [!code-xaml[ControlTemplateExamples#Calendar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
 L'esempio precedente usa una o più delle seguenti risorse.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](control-styles-and-templates.md)
- [Personalizzazione dei controlli](control-customization.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
