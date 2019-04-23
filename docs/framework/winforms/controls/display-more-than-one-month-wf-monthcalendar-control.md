---
title: 'Procedura: Visualizzare più mesi nel controllo MonthCalendar di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], formatting display
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], multiple months
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d197caa2-38a5-4cb4-acc3-562130c2ace3
ms.openlocfilehash: 79100b52d8e0a5b651edb9d6555a4497287ed858
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209554"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>Procedura: Visualizzare più mesi nel controllo MonthCalendar di Windows Forms
I moduli di Windows <xref:System.Windows.Forms.MonthCalendar> controllo può visualizzare fino a 12 mesi alla volta. Per impostazione predefinita, il controllo Visualizza un solo mese, ma è possibile specificare il numero di mesi viene visualizzato e come devono essere disposte all'interno del controllo. Quando si modificano le dimensioni del calendario, il controllo viene ridimensionato, pertanto assicurarsi che c'è spazio sufficiente sul form per le nuove dimensioni.  
  
### <a name="to-display-multiple-months"></a>Per visualizzare più mesi  
  
-   Impostare il <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> proprietà per il numero di mesi per visualizzare orizzontalmente e verticalmente.  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Controllo MonthCalendar](monthcalendar-control-windows-forms.md)
- [Procedura: Selezionare un intervallo di date nel controllo MonthCalendar Windows Form](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Procedura: Modificare l'aspetto del controllo MonthCalendar di Windows Form](how-to-change-monthcalendar-control-appearance.md)
