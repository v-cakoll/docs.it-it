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
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="c5d3a-102">Procedura: visualizzare giorni specifici in grassetto con il controllo MonthCalendar Windows Form</span><span class="sxs-lookup"><span data-stu-id="c5d3a-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="c5d3a-103">Il controllo Windows Forms <xref:System.Windows.Forms.MonthCalendar> può visualizzare i giorni in grassetto, come date singolari o in base a ripetizione.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="c5d3a-104">Questa operazione può essere eseguita per attirare l'attenzione su date speciali, ad esempio festività e fine settimana.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="c5d3a-105">Questa funzionalità è controllata da tre proprietà.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-105">Three properties control this feature.</span></span> <span data-ttu-id="c5d3a-106">La proprietà <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> contiene date singole.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="c5d3a-107">La proprietà <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> contiene date visualizzate in grassetto ogni anno.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="c5d3a-108">La proprietà <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> contiene date visualizzate in grassetto ogni mese.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="c5d3a-109">Ognuna di queste proprietà contiene una matrice di oggetti <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="c5d3a-110">Per aggiungere o rimuovere una data da uno di questi elenchi, è necessario aggiungere o rimuovere un oggetto <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="c5d3a-111">Per visualizzare una data in grassetto</span><span class="sxs-lookup"><span data-stu-id="c5d3a-111">To make a date appear in bold type</span></span>  
  
1. <span data-ttu-id="c5d3a-112">Creare gli oggetti <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-112">Create the <xref:System.DateTime> objects.</span></span>  
  
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
  
2. <span data-ttu-id="c5d3a-113">Creare una singola data in grassetto chiamando il metodo <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>o <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> del controllo <xref:System.Windows.Forms.MonthCalendar>.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
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
  
     <span data-ttu-id="c5d3a-114">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="c5d3a-114">–or–</span></span>  
  
     <span data-ttu-id="c5d3a-115">Impostare un set di date in grassetto in una sola volta creando una matrice di oggetti di <xref:System.DateTime> e assegnando a una delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
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
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="c5d3a-116">Per visualizzare una data nel carattere normale</span><span class="sxs-lookup"><span data-stu-id="c5d3a-116">To make a date appear in the regular font</span></span>  
  
1. <span data-ttu-id="c5d3a-117">Viene visualizzata una singola data in grassetto nel tipo di carattere normale chiamando il metodo <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>o <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
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
  
     <span data-ttu-id="c5d3a-118">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="c5d3a-118">–or–</span></span>  
  
     <span data-ttu-id="c5d3a-119">Rimuovere tutte le date in grassetto da uno dei tre elenchi chiamando il metodo <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>o <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. <span data-ttu-id="c5d3a-120">Aggiornare l'aspetto del tipo di carattere chiamando il metodo <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5d3a-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c5d3a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5d3a-121">See also</span></span>

- [<span data-ttu-id="c5d3a-122">Controllo MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="c5d3a-122">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="c5d3a-123">Procedura: Selezionare un intervallo di date nel controllo MonthCalendar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c5d3a-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="c5d3a-124">Procedura: Modificare l'aspetto del controllo MonthCalendar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c5d3a-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="c5d3a-125">Procedura: Visualizzare più mesi nel controllo MonthCalendar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c5d3a-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
