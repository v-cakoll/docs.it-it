---
title: Cenni preliminari sul controllo MonthCalendar (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
ms.openlocfilehash: a081c4e6d8210a6bb65fa14b31d12d4295931d53
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718883"
---
# <a name="monthcalendar-control-overview-windows-forms"></a>Cenni preliminari sul controllo MonthCalendar (Windows Form)
I moduli di Windows <xref:System.Windows.Forms.MonthCalendar> controllo presenta un'interfaccia grafica intuitiva per gli utenti possono visualizzare e impostare le informazioni sulla data. Il controllo verrà visualizzato un calendario: una griglia contenente i giorni del mese, distribuiti in colonne sotto i giorni della settimana, con l'intervallo di date evidenziate selezionato numerati. È possibile selezionare un altro mese facendo clic sui pulsanti freccia su entrambi i lati della didascalia del mese. A differenza dell'analoga <xref:System.Windows.Forms.DateTimePicker> (controllo), è possibile selezionare più di una data con questo controllo. Per altre informazioni sul <xref:System.Windows.Forms.DateTimePicker> controllano, vedere [controllo DateTimePicker](datetimepicker-control-windows-forms.md).  
  
## <a name="configuring-the-monthcalendar-control"></a>Configurazione del controllo MonthCalendar  
 Il <xref:System.Windows.Forms.MonthCalendar> aspetto del controllo è ampiamente configurabile. Per impostazione predefinita, data odierna viene visualizzata un cerchio e viene anche indicata nella parte inferiore della griglia. È possibile modificare questa funzionalità impostando la <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> e <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> delle proprietà per `false`. È anche possibile aggiungere i numeri di settimana al calendario, impostando il <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> proprietà `true`. Impostando il <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> proprietà, è possibile avere più mesi visualizzate orizzontalmente e verticalmente. Per impostazione predefinita, viene visualizzata la domenica come primo giorno della settimana, ma è possibile designare dei giorni usando il <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> proprietà.  
  
 È anche possibile impostare determinate date deve essere visualizzato grassetto con una sola volta, annuale o mensile, aggiungendo <xref:System.DateTime> gli oggetti per il <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>, e <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> proprietà. Per altre informazioni, vedere [Procedura: Visualizzare giorni specifici in grassetto con il Windows Form controllo MonthCalendar](display-specific-days-in-bold-with-wf-monthcalendar-control.md).  
  
 Le proprietà chiave della <xref:System.Windows.Forms.MonthCalendar> controllo è <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, l'intervallo di date selezionato nel controllo. Il <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> valore non può superare il numero massimo di giorni durante i quali può essere selezionato, impostare nel <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A> proprietà. La data più recente e meno recente selezionabili dall'utente è determinate dalle <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> e <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> proprietà.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.MonthCalendar>
- [Controllo MonthCalendar](monthcalendar-control-windows-forms.md)
