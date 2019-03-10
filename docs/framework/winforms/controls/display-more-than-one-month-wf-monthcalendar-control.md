---
title: 'Procedura: Visualizzare più mesi nel controllo MonthCalendar Windows Form'
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
ms.openlocfilehash: febed820bae460f51bb19f08caa6027011abd55d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715347"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="dab32-102">Procedura: Visualizzare più mesi nel controllo MonthCalendar Windows Form</span><span class="sxs-lookup"><span data-stu-id="dab32-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="dab32-103">I moduli di Windows <xref:System.Windows.Forms.MonthCalendar> controllo può visualizzare fino a 12 mesi alla volta.</span><span class="sxs-lookup"><span data-stu-id="dab32-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="dab32-104">Per impostazione predefinita, il controllo Visualizza un solo mese, ma è possibile specificare il numero di mesi viene visualizzato e come devono essere disposte all'interno del controllo.</span><span class="sxs-lookup"><span data-stu-id="dab32-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="dab32-105">Quando si modificano le dimensioni del calendario, il controllo viene ridimensionato, pertanto assicurarsi che c'è spazio sufficiente sul form per le nuove dimensioni.</span><span class="sxs-lookup"><span data-stu-id="dab32-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="dab32-106">Per visualizzare più mesi</span><span class="sxs-lookup"><span data-stu-id="dab32-106">To display multiple months</span></span>  
  
-   <span data-ttu-id="dab32-107">Impostare il <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> proprietà per il numero di mesi per visualizzare orizzontalmente e verticalmente.</span><span class="sxs-lookup"><span data-stu-id="dab32-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dab32-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dab32-108">See also</span></span>
- [<span data-ttu-id="dab32-109">Controllo MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="dab32-109">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="dab32-110">Procedura: Selezionare un intervallo di date nel controllo MonthCalendar Windows Form</span><span class="sxs-lookup"><span data-stu-id="dab32-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="dab32-111">Procedura: Modificare l'aspetto del controllo MonthCalendar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="dab32-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
