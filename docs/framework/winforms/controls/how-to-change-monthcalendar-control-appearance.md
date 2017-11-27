---
title: 'Procedura: modificare il controllo MonthCalendar Windows Form &#39; s aspetto'
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
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 38cddb4222077c21d72828371a8fe025184c4f75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-windows-forms-monthcalendar-control39s-appearance"></a><span data-ttu-id="e1a1b-102">Procedura: modificare il controllo MonthCalendar Windows Form &#39; s aspetto</span><span class="sxs-lookup"><span data-stu-id="e1a1b-102">How to: Change the Windows Forms MonthCalendar Control&#39;s Appearance</span></span>
<span data-ttu-id="e1a1b-103">Windows Form <xref:System.Windows.Forms.MonthCalendar> controllo consente di personalizzare l'aspetto del calendario in molti modi.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="e1a1b-104">Ad esempio, è possibile impostare la combinazione di colori e scegliere di visualizzare o nascondere i numeri di settimana e la data corrente.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="e1a1b-105">Per modificare la combinazione di colori del calendario mensile</span><span class="sxs-lookup"><span data-stu-id="e1a1b-105">To change the month calendar's color scheme</span></span>  
  
-   <span data-ttu-id="e1a1b-106">Impostare proprietà quali <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> e <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="e1a1b-107">Il <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> proprietà determina anche il colore del carattere per i giorni della settimana.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="e1a1b-108">Il <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> proprietà determina il colore di date che precedono e seguono il mese visualizzato o mesi.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
    ```vb  
    MonthCalendar1.TitleBackColor = System.Drawing.Color.Blue  
    MonthCalendar1.TrailingForeColor = System.Drawing.Color.Red  
    MonthCalendar1.TitleForeColor = System.Drawing.Color.Yellow  
    ```  
  
    ```csharp  
    monthCalendar1.TitleBackColor = System.Drawing.Color.Blue;  
    monthCalendar1.TrailingForeColor = System.Drawing.Color.Red;  
    monthCalendar1.TitleForeColor = System.Drawing.Color.Yellow;  
    ```  
  
    ```cpp  
    monthCalendar1->TitleBackColor = System::Drawing::Color::Blue;  
    monthCalendar1->TrailingForeColor = System::Drawing::Color::Red;  
    monthCalendar1->TitleForeColor = System::Drawing::Color::Yellow;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="e1a1b-109">A partire da Windows Vista e a seconda del tema, l'impostazione di alcune proprietà potrebbe non modificare l'aspetto del calendario.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="e1a1b-110">Ad esempio, se Windows è impostato per utilizzare il tema Aero, impostando il <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, o <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> proprietà non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="e1a1b-111">In questo modo viene eseguito il rendering di una versione aggiornata del calendario con un aspetto derivato in fase di esecuzione dal tema del sistema operativo corrente.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="e1a1b-112">Se si desidera utilizzare queste proprietà e abilitare la versione precedente del calendario, è possibile disabilitare gli stili di visualizzazione per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="e1a1b-113">La disabilitazione degli stili potrebbe influenzare l'aspetto e il comportamento di altri controlli nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="e1a1b-114">Per disabilitare gli stili di visualizzazione in Visual Basic, aprire la finestra di progettazione del progetto e deselezionare il **gli stili visivi XP abilitare** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="e1a1b-115">Per disabilitare gli stili di visualizzazione in c#, aprire Program.cs e impostare come commento `Application.EnableVisualStyles();`.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="e1a1b-116">Per ulteriori informazioni sugli stili, vedere [procedura: abilitare gli stili di visualizzazione di Windows XP](http://msdn.microsoft.com/en-us/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).</span><span class="sxs-lookup"><span data-stu-id="e1a1b-116">For more information about visual styles, see [How to: Enable Windows XP Visual Styles](http://msdn.microsoft.com/en-us/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="e1a1b-117">Per visualizzare la data corrente nella parte inferiore del controllo</span><span class="sxs-lookup"><span data-stu-id="e1a1b-117">To display the current date at the bottom of the control</span></span>  
  
-   <span data-ttu-id="e1a1b-118">Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="e1a1b-119">Nell'esempio seguente attiva o disattiva la visualizzazione della data odierna quando il modulo si fa doppio clic.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
    ```vb  
    Private Sub Form1_DoubleClick(ByVal sender As Object, _  
    ByVal e As System.EventArgs) Handles MyBase.DoubleClick  
       ' Toggle between True and False.  
       MonthCalendar1.ShowToday = Not MonthCalendar1.ShowToday  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_DoubleClick(object sender, System.EventArgs e)  
    {  
       // Toggle between True and False.  
       monthCalendar1.ShowToday = !monthCalendar1.ShowToday;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void Form1_DoubleClick(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // Toggle between True and False.  
          monthCalendar1->ShowToday = !monthCalendar1->ShowToday;  
       }  
    ```  
  
     <span data-ttu-id="e1a1b-120">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-120">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="e1a1b-121">Per visualizzare i numeri di settimana</span><span class="sxs-lookup"><span data-stu-id="e1a1b-121">To display week numbers</span></span>  
  
-   <span data-ttu-id="e1a1b-122">Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="e1a1b-123">È possibile impostare questa proprietà nel codice o nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="e1a1b-124">Numeri di settimana vengono visualizzati in una colonna separata a sinistra del primo giorno della settimana.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e1a1b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1a1b-125">See Also</span></span>  
 [<span data-ttu-id="e1a1b-126">Controllo MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="e1a1b-126">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [<span data-ttu-id="e1a1b-127">Procedura: Selezionare un intervallo di date nel controllo MonthCalendar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e1a1b-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [<span data-ttu-id="e1a1b-128">Procedura: Visualizzare giorni specifici in grassetto con il controllo MonthCalendar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e1a1b-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)  
 [<span data-ttu-id="e1a1b-129">Procedura: Visualizzare più mesi nel controllo MonthCalendar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e1a1b-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
