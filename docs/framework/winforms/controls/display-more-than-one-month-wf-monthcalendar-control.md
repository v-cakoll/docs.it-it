---
title: "Procedura: visualizzare più mesi nel controllo MonthCalendar Windows Form"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63cf236f93fa3352e536c71000f6bb110abf02fa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>Procedura: visualizzare più mesi nel controllo MonthCalendar Windows Form
Windows Form <xref:System.Windows.Forms.MonthCalendar> controllo può visualizzare fino a dodici mesi contemporaneamente. Per impostazione predefinita, il controllo Visualizza un solo mese, ma è possibile specificare il numero di mesi viene visualizzato e la modalità di disposizione all'interno del controllo. Quando si modificano le dimensioni del calendario, il controllo viene ridimensionato, è necessario che vi sia spazio sufficiente nel form per le nuove dimensioni.  
  
### <a name="to-display-multiple-months"></a>Per visualizzare più mesi  
  
-   Impostare il <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> proprietà per il numero di mesi da visualizzare orizzontalmente e verticalmente.  
  
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
 [Controllo MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [Procedura: Selezionare un intervallo di date nel controllo MonthCalendar di Windows Form](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [Procedura: Modificare l'aspetto del controllo MonthCalendar di Windows Form](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
