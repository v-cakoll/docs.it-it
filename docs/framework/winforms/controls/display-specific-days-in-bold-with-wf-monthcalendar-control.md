---
title: 'Procedura: Visualizzare giorni specifici in grassetto con il controllo MonthCalendar di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], displaying dates in bold
- examples [Windows Forms], calendar controls
- GetDayBold event
- MonthCalendar control [Windows Forms], dates displayed in bold
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
ms.openlocfilehash: 27b19e47d108b9af43a6d8882264d62c726ffe56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972081"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a>Procedura: Visualizzare giorni specifici in grassetto con il controllo MonthCalendar di Windows Forms
I moduli di Windows <xref:System.Windows.Forms.MonthCalendar> controllo può visualizzare i giorni in grassetto, come le date singolare o ripetute. È possibile eseguire questa operazione per attirare l'attenzione su date speciali, ad esempio i fine settimana e festivi.  
  
 Questa funzionalità è controllata da tre proprietà. Il <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> proprietà contiene date singole. Il <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> proprietà contiene le date visualizzate in grassetto ogni anno. Il <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> proprietà contiene le date visualizzate in grassetto ogni mese. Ognuna di queste proprietà contiene una matrice di <xref:System.DateTime> oggetti. Per aggiungere o rimuovere una data da uno di questi elenchi, è necessario aggiungere o rimuovere un <xref:System.DateTime> oggetto.  
  
### <a name="to-make-a-date-appear-in-bold-type"></a>Come è possibile visualizzare una data in grassetto  
  
1. Creare il <xref:System.DateTime> oggetti.  
  
    ```vb  
    Dim myVacation1 As Date = New DateTime(2001, 6, 10)  
    Dim myVacation2 As Date = New DateTime(2001, 6, 17)  
    ```  
  
    ```csharp  
    DateTime myVacation1 = new DateTime(2001, 6, 10);  
    DateTime myVacation2 = new DateTime(2001, 6, 17);  
    ```  
  
    ```cpp  
    DateTime myVacation1 = DateTime(2001, 6, 10);  
    DateTime myVacation2 = DateTime(2001, 6, 17);  
    ```  
  
2. Per una singola data in grassetto chiamando il <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, o <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> metodo il <xref:System.Windows.Forms.MonthCalendar> controllo.  
  
    ```vb  
    MonthCalendar1.AddBoldedDate(myVacation1)  
    MonthCalendar1.AddBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.AddBoldedDate(myVacation1);  
    monthCalendar1.AddBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->AddBoldedDate(myVacation1);  
    monthCalendar1->AddBoldedDate(myVacation2);  
    ```  
  
     - oppure -  
  
     Per un set di date in grassetto contemporaneamente mediante la creazione di una matrice di <xref:System.DateTime> oggetti e assegnarlo a una delle proprietà.  
  
    ```vb  
    Dim VacationDates As DateTime() = {myVacation1, myVacation2}  
    MonthCalendar1.BoldedDates = VacationDates  
    ```  
  
    ```csharp  
    DateTime[] VacationDates = {myVacation1, myVacation2};  
    monthCalendar1.BoldedDates = VacationDates;  
    ```  
  
    ```cpp  
    Array<DateTime>^ VacationDates = {myVacation1, myVacation2};  
    monthCalendar1->BoldedDates = VacationDates;  
    ```  
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a>Come è possibile visualizzare una data nel tipo di carattere normale  
  
1. Visualizzare una singola data in grassetto in caratteri normali chiamando il <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, o <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> (metodo).  
  
    ```vb  
    MonthCalendar1.RemoveBoldedDate(myVacation1)  
    MonthCalendar1.RemoveBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveBoldedDate(myVacation1);  
    monthCalendar1.RemoveBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveBoldedDate(myVacation1);  
    monthCalendar1->RemoveBoldedDate(myVacation2);  
    ```  
  
     - oppure -  
  
     Rimuovere tutte le date in grassetto da uno dei tre elenchi chiamando il <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, o <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> (metodo).  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. Aggiornare l'aspetto del tipo di carattere chiamando il <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> (metodo).  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Controllo MonthCalendar](monthcalendar-control-windows-forms.md)
- [Procedura: Selezionare un intervallo di date nel controllo MonthCalendar Windows Form](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Procedura: Modificare l'aspetto del controllo MonthCalendar di Windows Form](how-to-change-monthcalendar-control-appearance.md)
- [Procedura: Visualizzare più mesi nel controllo MonthCalendar Windows Form](display-more-than-one-month-wf-monthcalendar-control.md)
