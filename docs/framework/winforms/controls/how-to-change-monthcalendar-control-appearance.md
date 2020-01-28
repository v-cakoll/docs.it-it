---
title: Modificare l'aspetto del controllo MonthCalendar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: ded9059ede4ad03f637c0e697b880c41a9a8ba32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746648"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a><span data-ttu-id="0d878-102">Procedura: modificare l'aspetto del controllo MonthCalendar Windows Form</span><span class="sxs-lookup"><span data-stu-id="0d878-102">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>
<span data-ttu-id="0d878-103">Il controllo Windows Forms <xref:System.Windows.Forms.MonthCalendar> consente di personalizzare l'aspetto del calendario in molti modi.</span><span class="sxs-lookup"><span data-stu-id="0d878-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="0d878-104">Ad esempio, è possibile impostare la combinazione di colori e scegliere di visualizzare o nascondere i numeri settimanali e la data corrente.</span><span class="sxs-lookup"><span data-stu-id="0d878-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="0d878-105">Per modificare la combinazione di colori del calendario mensile</span><span class="sxs-lookup"><span data-stu-id="0d878-105">To change the month calendar's color scheme</span></span>  
  
- <span data-ttu-id="0d878-106">Impostare proprietà quali <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> e <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d878-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="0d878-107">La proprietà <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> determina anche il colore del carattere per i giorni della settimana.</span><span class="sxs-lookup"><span data-stu-id="0d878-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="0d878-108">La proprietà <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> determina il colore delle date che precedono e seguono il mese o i mesi visualizzati.</span><span class="sxs-lookup"><span data-stu-id="0d878-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
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
    > <span data-ttu-id="0d878-109">A partire da Windows Vista e a seconda del tema, l'impostazione di alcune proprietà potrebbe non modificare l'aspetto del calendario.</span><span class="sxs-lookup"><span data-stu-id="0d878-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="0d878-110">Se, ad esempio, Windows è impostato in modo da utilizzare il tema Aero, l'impostazione delle proprietà <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>o <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="0d878-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="0d878-111">Questo perché una versione aggiornata del calendario viene sottoposta a rendering con un aspetto derivato in fase di esecuzione dal tema del sistema operativo corrente.</span><span class="sxs-lookup"><span data-stu-id="0d878-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="0d878-112">Se si desidera utilizzare queste proprietà e abilitare la versione precedente del calendario, è possibile disabilitare gli stili visivi per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0d878-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="0d878-113">La disabilitazione degli stili di visualizzazione potrebbe influire sull'aspetto e sul comportamento di altri controlli nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0d878-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="0d878-114">Per disabilitare gli stili di visualizzazione in Visual Basic, aprire Progettazione progetti e deselezionare la casella di controllo **Abilita stili di visualizzazione XP** .</span><span class="sxs-lookup"><span data-stu-id="0d878-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="0d878-115">Per disabilitare gli stili di C#visualizzazione in, aprire Program.cs e impostare come commento `Application.EnableVisualStyles();`.</span><span class="sxs-lookup"><span data-stu-id="0d878-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="0d878-116">Per altre informazioni sugli stili di visualizzazione, vedere [Abilitazione degli stili di visualizzazione](/windows/desktop/controls/cookbook-overview).</span><span class="sxs-lookup"><span data-stu-id="0d878-116">For more information about visual styles, see [Enabling Visual Styles](/windows/desktop/controls/cookbook-overview).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="0d878-117">Per visualizzare la data corrente nella parte inferiore del controllo</span><span class="sxs-lookup"><span data-stu-id="0d878-117">To display the current date at the bottom of the control</span></span>  
  
- <span data-ttu-id="0d878-118">Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="0d878-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="0d878-119">Nell'esempio seguente viene alternata la visualizzazione e l'omissione della data odierna quando si fa doppio clic sul form.</span><span class="sxs-lookup"><span data-stu-id="0d878-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
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
  
     <span data-ttu-id="0d878-120">(Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="0d878-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="0d878-121">Per visualizzare i numeri settimanali</span><span class="sxs-lookup"><span data-stu-id="0d878-121">To display week numbers</span></span>  
  
- <span data-ttu-id="0d878-122">Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="0d878-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="0d878-123">Questa proprietà può essere impostata nel codice o nel Finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="0d878-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="0d878-124">I numeri settimanali vengono visualizzati in una colonna separata a sinistra del primo giorno della settimana.</span><span class="sxs-lookup"><span data-stu-id="0d878-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0d878-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d878-125">See also</span></span>

- [<span data-ttu-id="0d878-126">Controllo MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="0d878-126">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="0d878-127">Procedura: Selezionare un intervallo di date nel controllo MonthCalendar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0d878-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="0d878-128">Procedura: Visualizzare giorni specifici in grassetto con il controllo MonthCalendar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0d878-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="0d878-129">Procedura: Visualizzare più mesi nel controllo MonthCalendar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0d878-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
