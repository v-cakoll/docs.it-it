---
title: Visualizza più di un mese nel controllo MonthCalendar
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
ms.openlocfilehash: 5d3925bc19ddcd67742f0ab8b5b2e45530820f38
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745895"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>Procedura: visualizzare più mesi nel controllo MonthCalendar Windows Form
Il controllo Windows Forms <xref:System.Windows.Forms.MonthCalendar> può essere visualizzato fino a 12 mesi alla volta. Per impostazione predefinita, il controllo Visualizza un solo mese, ma è possibile specificare il numero di mesi visualizzati e il modo in cui vengono disposti all'interno del controllo. Quando si modificano le dimensioni del calendario, il controllo viene ridimensionato, quindi assicurarsi che sia disponibile spazio sufficiente sul form per le nuove dimensioni.  
  
### <a name="to-display-multiple-months"></a>Per visualizzare più mesi  
  
- Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> sul numero di mesi da visualizzare orizzontalmente e verticalmente.  
  
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
- [Procedura: Selezionare un intervallo di date nel controllo MonthCalendar di Windows Form](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Procedura: Modificare l'aspetto del controllo MonthCalendar di Windows Form](how-to-change-monthcalendar-control-appearance.md)
