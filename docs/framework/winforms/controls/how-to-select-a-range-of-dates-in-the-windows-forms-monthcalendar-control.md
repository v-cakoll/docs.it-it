---
title: 'Procedura: Selezionare un intervallo di date nel controllo MonthCalendar di Windows Forms'
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
ms.openlocfilehash: 82d0499cb40f79a3110b8432fbee66774bcc14a7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332235"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="0ee8b-102">Procedura: Selezionare un intervallo di date nel controllo MonthCalendar di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ee8b-102">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="0ee8b-103">Una caratteristica importante dei moduli di Windows <xref:System.Windows.Forms.MonthCalendar> controllo è che l'utente può selezionare un intervallo di date.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-103">An important feature of the Windows Forms <xref:System.Windows.Forms.MonthCalendar> control is that the user can select a range of dates.</span></span> <span data-ttu-id="0ee8b-104">Questa funzionalità è un miglioramento rispetto alla funzionalità di selezione della data del <xref:System.Windows.Forms.DateTimePicker> controllo, che consente solo all'utente di selezionare un valore data/ora singolo.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-104">This feature is an improvement over the date-selection feature of the <xref:System.Windows.Forms.DateTimePicker> control, which only enables the user to select a single date/time value.</span></span> <span data-ttu-id="0ee8b-105">È possibile impostare un intervallo di date oppure ottenere impostato dall'utente utilizzando le proprietà di un intervallo di selezione il <xref:System.Windows.Forms.MonthCalendar> controllo.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-105">You can set a range of dates or get a selection range set by the user by using properties of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span> <span data-ttu-id="0ee8b-106">Esempio di codice seguente viene illustrato come impostare un intervallo di selezione.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-106">The following code example demonstrates how to set a selection range.</span></span>  
  
### <a name="to-select-a-range-of-dates"></a><span data-ttu-id="0ee8b-107">Per selezionare un intervallo di date</span><span class="sxs-lookup"><span data-stu-id="0ee8b-107">To select a range of dates</span></span>  
  
1. <span data-ttu-id="0ee8b-108">Creare <xref:System.DateTime> gli oggetti che rappresentano le date e il cognome in un intervallo.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-108">Create <xref:System.DateTime> objects that represent the first and last dates in a range.</span></span>  
  
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
  
2. <span data-ttu-id="0ee8b-109">Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-109">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> property.</span></span>  
  
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
  
     <span data-ttu-id="0ee8b-110">- oppure -</span><span class="sxs-lookup"><span data-stu-id="0ee8b-110">–or–</span></span>  
  
     <span data-ttu-id="0ee8b-111">Impostare le proprietà <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> e <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ee8b-111">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> and <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> properties.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0ee8b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ee8b-112">See also</span></span>

- [<span data-ttu-id="0ee8b-113">Controllo MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="0ee8b-113">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="0ee8b-114">Procedura: Modificare l'aspetto del controllo MonthCalendar di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ee8b-114">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="0ee8b-115">Procedura: Visualizzare giorni specifici in grassetto con il controllo MonthCalendar di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ee8b-115">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="0ee8b-116">Procedura: Visualizzare più mesi nel controllo MonthCalendar di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ee8b-116">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
