---
title: Calendar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Calendar
- Calendar control [WPF]
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
ms.openlocfilehash: e99a716e7ca8f7b2c9ed11543f37e0b8cb7422a6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460816"
---
# <a name="calendar"></a>Calendar
Un calendario consente a un utente di selezionare una data tramite la visualizzazione di un calendario visivo.  
  
 Un controllo <xref:System.Windows.Controls.Calendar> può essere utilizzato autonomamente o come parte a discesa di un controllo <xref:System.Windows.Controls.DatePicker>. Per ulteriori informazioni, vedere <xref:System.Windows.Controls.DatePicker>.  
  
 Nella figura seguente vengono illustrati due controlli <xref:System.Windows.Controls.Calendar>, uno con le selezioni e le date di blackout e uno senza.  
  
 ![Controlli calendario](./media/ndp-calendarcontrols.png "NDP_CalendarControls")  
Controlli del calendario  
  
 Nella tabella seguente vengono fornite informazioni sulle attività generalmente associate al <xref:System.Windows.Controls.Calendar>.  
  
|Attività|Implementazione|  
|----------|--------------------|  
|Specificare le date che non possono essere selezionate.|Usare la proprietà <xref:System.Windows.Controls.Calendar.BlackoutDates%2A>.|  
|Fare in modo che il <xref:System.Windows.Controls.Calendar> visualizzi un mese, un anno intero o un decennio.|Impostare la proprietà <xref:System.Windows.Controls.Calendar.DisplayMode%2A> su month, year o decade.|  
|Specificare se l'utente può selezionare una data, un intervallo di date o più intervalli di date.|Usare il <xref:System.Windows.Controls.Calendar.SelectionMode%2A>.|  
|Specificare l'intervallo di date visualizzate dal <xref:System.Windows.Controls.Calendar>.|Usare le proprietà <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A> e <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A>.|  
|Consente di specificare se la data corrente è evidenziata.|Usare la proprietà <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A>. Per impostazione predefinita, <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> è `true`.|  
|Modificare le dimensioni del <xref:System.Windows.Controls.Calendar>.|Utilizzare un <xref:System.Windows.Controls.Viewbox> o impostare la proprietà <xref:System.Windows.FrameworkElement.LayoutTransform%2A> su un <xref:System.Windows.Media.ScaleTransform>. Si noti che se si impostano le proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> di un <xref:System.Windows.Controls.Calendar>, il calendario effettivo non ne modifica le dimensioni.|  
  
 Il controllo <xref:System.Windows.Controls.Calendar> fornisce la navigazione di base utilizzando il mouse o la tastiera. Nella tabella seguente viene riepilogata la navigazione da tastiera.  
  
|Combinazione di tasti|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|Operazione|  
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|FRECCIA|<xref:System.Windows.Controls.CalendarMode.Month>|Modifica la proprietà <xref:System.Windows.Controls.Calendar.SelectedDate%2A> se la proprietà <xref:System.Windows.Controls.Calendar.SelectionMode%2A> non è impostata su <xref:System.Windows.Controls.CalendarSelectionMode.None>.|  
|FRECCIA|<xref:System.Windows.Controls.CalendarMode.Year>|Modifica il mese della proprietà <xref:System.Windows.Controls.Calendar.DisplayDate%2A>. Si noti che il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> non cambia.|  
|FRECCIA|<xref:System.Windows.Controls.CalendarMode.Decade>|Modifica l'anno del <xref:System.Windows.Controls.Calendar.DisplayDate%2A>. Si noti che il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> non cambia.|  
|MAIUSC + freccia|<xref:System.Windows.Controls.CalendarMode.Month>|Se <xref:System.Windows.Controls.Calendar.SelectionMode%2A> non è impostato su <xref:System.Windows.Controls.CalendarSelectionMode.SingleDate> o <xref:System.Windows.Controls.CalendarSelectionMode.None>, estende l'intervallo di date selezionate.|  
|HOME|<xref:System.Windows.Controls.CalendarMode.Month>|Imposta il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> sul primo giorno del mese corrente.|  
|HOME|<xref:System.Windows.Controls.CalendarMode.Year>|Modifica il mese del <xref:System.Windows.Controls.Calendar.DisplayDate%2A> al primo mese dell'anno. Il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> non cambia.|  
|HOME|<xref:System.Windows.Controls.CalendarMode.Decade>|Modifica l'anno del <xref:System.Windows.Controls.Calendar.DisplayDate%2A> al primo anno del decennio. Il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> non cambia.|  
|FINE|<xref:System.Windows.Controls.CalendarMode.Month>|Imposta il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> sull'ultimo giorno del mese corrente.|  
|FINE|<xref:System.Windows.Controls.CalendarMode.Year>|Imposta il mese del <xref:System.Windows.Controls.Calendar.DisplayDate%2A> sull'ultimo mese dell'anno. Il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> non cambia.|  
|FINE|<xref:System.Windows.Controls.CalendarMode.Decade>|Modifica l'anno del <xref:System.Windows.Controls.Calendar.DisplayDate%2A> nell'ultimo anno del decennio. Il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> non cambia.|  
|CTRL+FRECCIA SU|Qualsiasi|Passa alla <xref:System.Windows.Controls.Calendar.DisplayMode%2A>successiva più grande. Se <xref:System.Windows.Controls.Calendar.DisplayMode%2A> è già <xref:System.Windows.Controls.CalendarMode.Decade>, non viene eseguita alcuna azione.|  
|CTRL+freccia GIÙ|Qualsiasi|Passa alla <xref:System.Windows.Controls.Calendar.DisplayMode%2A>inferiore successiva. Se <xref:System.Windows.Controls.Calendar.DisplayMode%2A> è già <xref:System.Windows.Controls.CalendarMode.Month>, non viene eseguita alcuna azione.|  
|BARRA SPAZIAtrice o invio|<xref:System.Windows.Controls.CalendarMode.Year> o <xref:System.Windows.Controls.CalendarMode.Decade>|Passa <xref:System.Windows.Controls.Calendar.DisplayMode%2A> al <xref:System.Windows.Controls.CalendarMode.Month> o <xref:System.Windows.Controls.CalendarMode.Year> rappresentato dall'elemento con lo stato attivo.|  
  
## <a name="see-also"></a>Vedere anche

- [Controlli](index.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
