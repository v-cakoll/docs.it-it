---
title: Cenni preliminari sul controllo DateTimePicker (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
ms.openlocfilehash: cf44cdff7da06a27921ce5881199a3a88b1096f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528352"
---
# <a name="datetimepicker-control-overview-windows-forms"></a>Cenni preliminari sul controllo DateTimePicker (Windows Form)
Windows Form <xref:System.Windows.Forms.DateTimePicker> controllo consente all'utente di selezionare un singolo elemento da un elenco di date o ore. Quando utilizzato per rappresentare una data, viene visualizzato in due parti: un elenco a discesa con una data rappresentata in testo e una griglia in cui viene visualizzata quando si fa clic su freccia in giù accanto all'elenco. Aspetto della griglia di <xref:System.Windows.Forms.MonthCalendar> controllo, che può essere utilizzato per la selezione di più date. Per ulteriori informazioni sul <xref:System.Windows.Forms.MonthCalendar> di controllo, vedere [Cenni preliminari sul controllo MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md).  
  
## <a name="key-properties"></a>Proprietà chiave  
 Se si desidera il <xref:System.Windows.Forms.DateTimePicker> venga visualizzato come un controllo per la selezione o la modifica di ore anziché date, impostare il <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> proprietà `true` e <xref:System.Windows.Forms.DateTimePicker.Format%2A> proprietà <xref:System.Windows.Forms.DateTimePickerFormat.Time>. Per ulteriori informazioni vedere [come: tempo di visualizzazione con il controllo DateTimePicker](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md).  
  
 Quando il <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> è impostata su `true`, viene visualizzata una casella di controllo accanto alla data selezionata nel controllo. Se la casella di controllo è selezionata, il valore di data e ora selezionato può essere aggiornato. Quando la casella di controllo è vuota, viene visualizzato il valore non disponibile.  
  
 Il controllo <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> e <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> determinano l'intervallo di date e ore. Il <xref:System.Windows.Forms.DateTimePicker.Value%2A> proprietà contiene la data corrente e l'ora di impostare per il controllo. Per informazioni dettagliate, vedere [procedura: impostare e restituire date con il controllo DateTimePicker di Windows Form](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md). I valori possono essere visualizzati in quattro formati, che vengono impostati dal <xref:System.Windows.Forms.DateTimePicker.Format%2A> proprietà: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>, o <xref:System.Windows.Forms.DateTimePickerFormat.Custom>. Se si seleziona un formato personalizzato, è necessario impostare il <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> proprietà su una stringa appropriata. Per informazioni dettagliate, vedere [procedura: visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Form](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Form](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)  
 [Procedura: Impostare e restituire date con il controllo DateTimePicker di Windows Form](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
