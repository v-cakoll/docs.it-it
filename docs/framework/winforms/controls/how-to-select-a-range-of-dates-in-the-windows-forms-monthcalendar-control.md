---
title: Selezionare un intervallo di date nel controllo MonthCalendar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], selecting range in calendar controls
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], selecting date range
- MonthCalendar control [Windows Forms], selecting date range
ms.assetid: 95d9ab95-b0f8-4c19-9f63-b5cd4593a5d0
ms.openlocfilehash: bda96af21a8f86a54d5c0fe0204546b980076d26
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732892"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a>Procedura: selezionare un intervallo di date nel controllo MonthCalendar Windows Form
Una funzionalità importante del controllo Windows Forms <xref:System.Windows.Forms.MonthCalendar> è che l'utente può selezionare un intervallo di date. Questa funzionalità rappresenta un miglioramento rispetto alla funzionalità di selezione della data del controllo <xref:System.Windows.Forms.DateTimePicker>, che consente all'utente di selezionare un solo valore di data/ora. È possibile impostare un intervallo di date o ottenere un intervallo di selezione impostato dall'utente usando le proprietà del controllo <xref:System.Windows.Forms.MonthCalendar>. Nell'esempio di codice riportato di seguito viene illustrato come impostare un intervallo di selezione.  
  
### <a name="to-select-a-range-of-dates"></a>Per selezionare un intervallo di date  
  
1. Creare <xref:System.DateTime> oggetti che rappresentano la prima e l'ultima data di un intervallo.  
  
    ```vb  
    Dim projectStart As Date = New DateTime(2001, 2, 13)  
    Dim projectEnd As Date = New DateTime(2001, 2, 28)  
    ```  
  
    ```csharp  
    DateTime projectStart = new DateTime(2001, 2, 13);  
    DateTime projectEnd = new DateTime(2001, 2, 28);  
    ```  
  
    ```cpp  
    DateTime projectStart = DateTime(2001, 2, 13);  
    DateTime projectEnd = DateTime(2001, 2, 28);  
    ```  
  
2. Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>.  
  
    ```vb  
    MonthCalendar1.SelectionRange = New SelectionRange(projectStart, projectEnd)  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionRange = new SelectionRange(projectStart, projectEnd);  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionRange = gcnew  
       SelectionRange(projectStart, projectEnd);  
    ```  
  
     \- oppure -  
  
     Impostare le proprietà <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> e <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A>.  
  
    ```vb  
    MonthCalendar1.SelectionStart = projectStart  
    MonthCalendar1.SelectionEnd = projectEnd  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionStart = projectStart;  
    monthCalendar1.SelectionEnd = projectEnd;  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionStart = projectStart;  
    monthCalendar1->SelectionEnd = projectEnd;  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Controllo MonthCalendar](monthcalendar-control-windows-forms.md)
- [Procedura: Modificare l'aspetto del controllo MonthCalendar di Windows Form](how-to-change-monthcalendar-control-appearance.md)
- [Procedura: Visualizzare giorni specifici in grassetto con il controllo MonthCalendar di Windows Form](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [Procedura: Visualizzare più mesi nel controllo MonthCalendar di Windows Form](display-more-than-one-month-wf-monthcalendar-control.md)
