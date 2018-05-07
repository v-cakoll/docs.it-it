---
title: 'Procedura: selezionare un intervallo di date nel controllo MonthCalendar Windows Form'
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
ms.openlocfilehash: 8b6d64fcffb02c4496cff3f2821861117b0062fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a>Procedura: selezionare un intervallo di date nel controllo MonthCalendar Windows Form
Un'importante funzionalità di Windows Form <xref:System.Windows.Forms.MonthCalendar> controllo è che l'utente può selezionare un intervallo di date. Questa funzionalità è un miglioramento rispetto alla funzionalità di selezione della data del <xref:System.Windows.Forms.DateTimePicker> controllo, che consente solo all'utente di selezionare un valore data/ora singolo. È possibile impostare un intervallo di date o ottenere impostato dall'utente utilizzando le proprietà di un intervallo di selezione di <xref:System.Windows.Forms.MonthCalendar> controllo. Esempio di codice seguente viene illustrato come impostare un intervallo di selezione.  
  
### <a name="to-select-a-range-of-dates"></a>Per selezionare un intervallo di date  
  
1.  Creare <xref:System.DateTime> gli oggetti che rappresentano le date e il cognome in un intervallo.  
  
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
  
2.  Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>.  
  
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
  
     - oppure -  
  
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
 [Controllo MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [Procedura: Modificare l'aspetto del controllo MonthCalendar di Windows Form](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)  
 [Procedura: Visualizzare giorni specifici in grassetto con il controllo MonthCalendar di Windows Form](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)  
 [Procedura: Visualizzare più mesi nel controllo MonthCalendar di Windows Form](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
