---
title: Cenni preliminari sul controllo DateTimePicker
ms.date: 03/30/2017
f1_keywords:
- DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
ms.openlocfilehash: 63271dd91116c1f68d426f3ed5aa710644ded928
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746937"
---
# <a name="datetimepicker-control-overview-windows-forms"></a>Cenni preliminari sul controllo DateTimePicker (Windows Form)
Il controllo Windows Forms <xref:System.Windows.Forms.DateTimePicker> consente all'utente di selezionare un singolo elemento da un elenco di date o ore. Quando viene usato per rappresentare una data, viene visualizzato in due parti: un elenco a discesa con una data rappresentata nel testo e una griglia visualizzata quando si fa clic sulla freccia in giù accanto all'elenco. La griglia ha un aspetto analogo al controllo <xref:System.Windows.Forms.MonthCalendar>, che può essere usato per selezionare più date. Per ulteriori informazioni sul controllo <xref:System.Windows.Forms.MonthCalendar>, vedere [Cenni preliminari sul controllo MonthCalendar](monthcalendar-control-overview-windows-forms.md).  
  
## <a name="key-properties"></a>Proprietà chiave  
 Se si desidera che il <xref:System.Windows.Forms.DateTimePicker> venga visualizzato come controllo per la selezione o la modifica delle ore anziché delle date, impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> su `true` e la proprietà <xref:System.Windows.Forms.DateTimePicker.Format%2A> su <xref:System.Windows.Forms.DateTimePickerFormat.Time>. Per altre informazioni [, vedere Procedura: visualizzare l'ora con il controllo DateTimePicker](how-to-display-time-with-the-datetimepicker-control.md).  
  
 Quando la proprietà <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> è impostata su `true`, viene visualizzata una casella di controllo accanto alla data selezionata nel controllo. Quando la casella di controllo è selezionata, è possibile aggiornare il valore di data e ora selezionato. Quando la casella di controllo è vuota, il valore non è disponibile.  
  
 Le proprietà <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> e <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> del controllo determinano l'intervallo di date e ore. La proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A> contiene la data e l'ora correnti in cui è impostato il controllo. Per informazioni dettagliate, vedere [procedura: impostare e restituire date con il controllo DateTimePicker Windows Forms](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md). I valori possono essere visualizzati in quattro formati, impostati dalla proprietà <xref:System.Windows.Forms.DateTimePicker.Format%2A>: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>o <xref:System.Windows.Forms.DateTimePickerFormat.Custom>. Se è selezionato un formato personalizzato, è necessario impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> su una stringa appropriata. Per informazioni dettagliate, vedere [procedura: visualizzare una data in un formato personalizzato con il controllo DateTimePicker Windows Forms](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Form](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
- [Procedura: Impostare e restituire date con il controllo DateTimePicker di Windows Form](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
