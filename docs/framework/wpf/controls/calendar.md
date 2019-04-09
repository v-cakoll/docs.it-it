---
title: Calendar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Calendar
- Calendar control [WPF]
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
ms.openlocfilehash: 9a64c6cd6fc1cc53383f2617f7a7a78959e87c4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124787"
---
# <a name="calendar"></a>Calendar
Un calendario consente a un utente di selezionare una data mediante una rappresentazione visiva del calendario.  
  
 Oggetto <xref:System.Windows.Controls.Calendar> controllo può essere usato in modo autonomo o come parte dell'elenco a discesa un <xref:System.Windows.Controls.DatePicker> controllo. Per altre informazioni, vedere <xref:System.Windows.Controls.DatePicker>.  
  
 La figura seguente mostra due <xref:System.Windows.Controls.Calendar> controlli, uno con le selezioni e le date di blackout e uno senza.  
  
 ![Controlli calendario](./media/ndp-calendarcontrols.png "NDP_CalendarControls")  
Controlli del calendario  
  
 Nella tabella seguente vengono fornite informazioni sulle attività che sono in genere associati il <xref:System.Windows.Controls.Calendar>.  
  
|Attività|Implementazione|  
|----------|--------------------|  
|Specificare le date che non può essere selezionato.|Usare la proprietà <xref:System.Windows.Controls.Calendar.BlackoutDates%2A>.|  
|Dispone il <xref:System.Windows.Controls.Calendar> visualizzare un mese, un intero anno o un decennio.|Impostare il <xref:System.Windows.Controls.Calendar.DisplayMode%2A> proprietà al mese, anno o un decennio.|  
|Specificare se l'utente può selezionare una data, un intervallo di date o più intervalli di date.|Usare il <xref:System.Windows.Controls.Calendar.SelectionMode%2A>.|  
|Specificare l'intervallo di date che il <xref:System.Windows.Controls.Calendar> Visualizza.|Usare la <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A> e <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A> proprietà.|  
|Specificare se la data corrente è evidenziata.|Usare la proprietà <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A>. Per impostazione predefinita <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> è `true`.|  
|Modificare le dimensioni del <xref:System.Windows.Controls.Calendar>.|Usare un <xref:System.Windows.Controls.Viewbox> o impostare il <xref:System.Windows.FrameworkElement.LayoutTransform%2A> proprietà di un <xref:System.Windows.Media.ScaleTransform>. Si noti che se si imposta la <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> delle proprietà di un <xref:System.Windows.Controls.Calendar>, il calendario effettivo non modifica la dimensione.|  
  
 Il <xref:System.Windows.Controls.Calendar> controllo fornisce le operazioni di base utilizzando il mouse o tastiera. La tabella seguente riepiloga la navigazione da tastiera.  
  
|Combinazione di tasti|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|Operazione|  
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|ARROW|<xref:System.Windows.Controls.CalendarMode.Month>|Modifiche i <xref:System.Windows.Controls.Calendar.SelectedDate%2A> proprietà se il <xref:System.Windows.Controls.Calendar.SelectionMode%2A> proprietà non è impostata su <xref:System.Windows.Controls.CalendarSelectionMode.None>.|  
|ARROW|<xref:System.Windows.Controls.CalendarMode.Year>|Imposta il mese del <xref:System.Windows.Controls.Calendar.DisplayDate%2A> proprietà. Si noti che il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> non cambia.|  
|ARROW|<xref:System.Windows.Controls.CalendarMode.Decade>|Modificare l'anno del <xref:System.Windows.Controls.Calendar.DisplayDate%2A>. Si noti che il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> non cambia.|  
|MAIUSC + FRECCIA|<xref:System.Windows.Controls.CalendarMode.Month>|Se <xref:System.Windows.Controls.Calendar.SelectionMode%2A> non è impostata su <xref:System.Windows.Controls.CalendarSelectionMode.SingleDate> o <xref:System.Windows.Controls.CalendarSelectionMode.None>, estende l'intervallo di date selezionate.|  
|HOME|<xref:System.Windows.Controls.CalendarMode.Month>|Modifiche di <xref:System.Windows.Controls.Calendar.SelectedDate%2A> al primo giorno del mese corrente.|  
|HOME|<xref:System.Windows.Controls.CalendarMode.Year>|Imposta il mese del <xref:System.Windows.Controls.Calendar.DisplayDate%2A> al primo mese dell'anno. Il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> non cambia.|  
|HOME|<xref:System.Windows.Controls.CalendarMode.Decade>|Modificare l'anno del <xref:System.Windows.Controls.Calendar.DisplayDate%2A> per il primo anno del decennio. Il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> non cambia.|  
|FINE|<xref:System.Windows.Controls.CalendarMode.Month>|Modifiche di <xref:System.Windows.Controls.Calendar.SelectedDate%2A> all'ultimo giorno del mese corrente.|  
|FINE|<xref:System.Windows.Controls.CalendarMode.Year>|Imposta il mese del <xref:System.Windows.Controls.Calendar.DisplayDate%2A> per il mese dell'anno. Il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> non cambia.|  
|FINE|<xref:System.Windows.Controls.CalendarMode.Decade>|Modificare l'anno del <xref:System.Windows.Controls.Calendar.DisplayDate%2A> all'ultimo anno del decennio. Il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> non cambia.|  
|CTRL+FRECCIA SU|Qualsiasi|Passa al successivo più grande <xref:System.Windows.Controls.Calendar.DisplayMode%2A>. Se <xref:System.Windows.Controls.Calendar.DisplayMode%2A> già <xref:System.Windows.Controls.CalendarMode.Decade>, alcuna azione.|  
|CTRL+freccia GIÙ|Qualsiasi|Passa alla successiva più piccoli <xref:System.Windows.Controls.Calendar.DisplayMode%2A>. Se <xref:System.Windows.Controls.Calendar.DisplayMode%2A> già <xref:System.Windows.Controls.CalendarMode.Month>, alcuna azione.|  
|La barra spaziatrice o invio|<xref:System.Windows.Controls.CalendarMode.Year> oppure <xref:System.Windows.Controls.CalendarMode.Decade>|Commutatori <xref:System.Windows.Controls.Calendar.DisplayMode%2A> per il <xref:System.Windows.Controls.CalendarMode.Month> o <xref:System.Windows.Controls.CalendarMode.Year> rappresentato dall'elemento con lo stato attivo.|  
  
## <a name="see-also"></a>Vedere anche

- [Controlli](index.md)
- [Applicazione di stili e modelli](styling-and-templating.md)
