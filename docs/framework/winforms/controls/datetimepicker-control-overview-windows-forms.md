---
title: Cenni preliminari sul controllo DateTimePicker (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
ms.openlocfilehash: 451172b51427e4932470c53737c7bc276920271c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61909168"
---
# <a name="datetimepicker-control-overview-windows-forms"></a>Cenni preliminari sul controllo DateTimePicker (Windows Form)
I moduli di Windows <xref:System.Windows.Forms.DateTimePicker> controllo consente all'utente di selezionare un singolo elemento da un elenco di date o ore. Quando usato per rappresentare una data, viene visualizzata in due parti: un elenco di riepilogo a discesa con una data nel testo e una griglia in cui viene visualizzata quando si fa clic sulla freccia giù accanto all'elenco. La griglia è simile al <xref:System.Windows.Forms.MonthCalendar> controllo, che può essere usato per la selezione di date più. Per altre informazioni sul <xref:System.Windows.Forms.MonthCalendar> controllano, vedere [Cenni preliminari sul controllo MonthCalendar](monthcalendar-control-overview-windows-forms.md).  
  
## <a name="key-properties"></a>Proprietà chiave  
 Se si desidera il <xref:System.Windows.Forms.DateTimePicker> venga visualizzato come un controllo per la selezione o modifica dei tempi anziché le date, impostare il <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> proprietà `true` e il <xref:System.Windows.Forms.DateTimePicker.Format%2A> proprietà <xref:System.Windows.Forms.DateTimePickerFormat.Time>. Per altre informazioni, vedere [Procedura: Visualizzare l'ora con il controllo DateTimePicker](how-to-display-time-with-the-datetimepicker-control.md).  
  
 Quando la <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> è impostata su `true`, viene visualizzata una casella di controllo accanto della data selezionata nel controllo. Se la casella di controllo è selezionata, il valore di data e ora selezionato può essere aggiornato. Quando la casella di controllo è vuota, viene visualizzato il valore non disponibile.  
  
 Il controllo <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> e <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> determinano l'intervallo di date e ore. Il <xref:System.Windows.Forms.DateTimePicker.Value%2A> proprietà contiene la data corrente e l'ora il controllo è impostato su. Per informazioni dettagliate, vedere [Procedura: Impostare e restituire date con il Windows Form controllo DateTimePicker](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md). I valori possono essere visualizzati in quattro formati, che vengono impostati dal <xref:System.Windows.Forms.DateTimePicker.Format%2A> proprietà: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>, o <xref:System.Windows.Forms.DateTimePickerFormat.Custom>. Se si seleziona un formato personalizzato, è necessario impostare il <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> proprietà sulla stringa appropriata. Per informazioni dettagliate, vedere [Procedura: Visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Form](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Form](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
- [Procedura: Impostare e restituire date con il controllo DateTimePicker di Windows Form](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
