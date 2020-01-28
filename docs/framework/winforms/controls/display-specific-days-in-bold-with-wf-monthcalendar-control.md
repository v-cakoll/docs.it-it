---
title: Visualizza giorni specifici in grassetto con il controllo MonthCalendar
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
ms.openlocfilehash: 377eb76f562fff20aae2136ddb7130516d2d76f7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745889"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a>Procedura: visualizzare giorni specifici in grassetto con il controllo MonthCalendar Windows Form
Il controllo Windows Forms <xref:System.Windows.Forms.MonthCalendar> può visualizzare i giorni in grassetto, come date singolari o in base a ripetizione. Questa operazione può essere eseguita per attirare l'attenzione su date speciali, ad esempio festività e fine settimana.  
  
 Questa funzionalità è controllata da tre proprietà. La proprietà <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> contiene date singole. La proprietà <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> contiene date visualizzate in grassetto ogni anno. La proprietà <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> contiene date visualizzate in grassetto ogni mese. Ognuna di queste proprietà contiene una matrice di oggetti <xref:System.DateTime>. Per aggiungere o rimuovere una data da uno di questi elenchi, è necessario aggiungere o rimuovere un oggetto <xref:System.DateTime>.  
  
### <a name="to-make-a-date-appear-in-bold-type"></a>Per visualizzare una data in grassetto  
  
1. Creare gli oggetti <xref:System.DateTime>.  
  
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
  
2. Creare una singola data in grassetto chiamando il metodo <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>o <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> del controllo <xref:System.Windows.Forms.MonthCalendar>.  
  
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
  
     \- oppure -  
  
     Impostare un set di date in grassetto in una sola volta creando una matrice di oggetti di <xref:System.DateTime> e assegnando a una delle proprietà.  
  
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
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a>Per visualizzare una data nel carattere normale  
  
1. Viene visualizzata una singola data in grassetto nel tipo di carattere normale chiamando il metodo <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>o <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A>.  
  
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
  
     \- oppure -  
  
     Rimuovere tutte le date in grassetto da uno dei tre elenchi chiamando il metodo <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>o <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A>.  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. Aggiornare l'aspetto del tipo di carattere chiamando il metodo <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A>.  
  
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
- [Procedura: Selezionare un intervallo di date nel controllo MonthCalendar di Windows Form](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Procedura: Modificare l'aspetto del controllo MonthCalendar di Windows Form](how-to-change-monthcalendar-control-appearance.md)
- [Procedura: Visualizzare più mesi nel controllo MonthCalendar di Windows Form](display-more-than-one-month-wf-monthcalendar-control.md)
