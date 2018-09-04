---
title: 'Procedura dettagliata: aggiornamento delle informazioni sulla barra di stato in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
ms.openlocfilehash: 49722d5dadf694e8ee3037646652b921ddda3e91
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43542603"
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a><span data-ttu-id="d626e-102">Procedura dettagliata: aggiornamento delle informazioni sulla barra di stato in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="d626e-102">Walkthrough: Updating Status Bar Information at Run Time</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="d626e-103">Il <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> controlli sostituire e aggiungano funzionalità rispetto al <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli; tuttavia, il <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli vengono mantenuti per compatibilità con le versioni precedenti e per un uso futuro, se si Scegliere.</span><span class="sxs-lookup"><span data-stu-id="d626e-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="d626e-104">Spesso, in fase di esecuzione, un programma richiede di aggiornare in modo dinamico il contenuto dei pannelli della barra di stato in base alle modifiche dello stato dell'applicazione o all'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d626e-104">Often, a program will call for you to update the contents of status bar panels dynamically at run time, based on changes to application state or other user interaction.</span></span> <span data-ttu-id="d626e-105">Si tratta di un metodo comune utilizzato per segnalare agli utenti che sono attivati tasti quali BLOC MAIUSC, BLOC NUM o BLOC SCORR oppure per fornire la data o un orologio come riferimento.</span><span class="sxs-lookup"><span data-stu-id="d626e-105">This is a common way to signal users that keys such as the CAPS LOCK, NUM LOCK, or SCROLL LOCK are enabled, or to provide the date or a clock as a convenient reference.</span></span>  
  
 <span data-ttu-id="d626e-106">Nell'esempio seguente, si userà un'istanza di <xref:System.Windows.Forms.StatusBarPanel> classe per visualizzare un orologio.</span><span class="sxs-lookup"><span data-stu-id="d626e-106">In the following example, you will use an instance of the <xref:System.Windows.Forms.StatusBarPanel> class to host a clock.</span></span>  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a><span data-ttu-id="d626e-107">Per preparare la barra di stato per l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d626e-107">To get the status bar ready for updating</span></span>  
  
1.  <span data-ttu-id="d626e-108">Creare un nuovo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="d626e-108">Create a new Windows form.</span></span>  
  
2.  <span data-ttu-id="d626e-109">Aggiungere un oggetto <xref:System.Windows.Forms.StatusBar> al form.</span><span class="sxs-lookup"><span data-stu-id="d626e-109">Add a <xref:System.Windows.Forms.StatusBar> control to your form.</span></span> <span data-ttu-id="d626e-110">Per informazioni dettagliate, vedere [Procedura: aggiungere controlli a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d626e-110">For details, see [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
3.  <span data-ttu-id="d626e-111">Aggiungere un pannello della barra di stato per i <xref:System.Windows.Forms.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="d626e-111">Add a status bar panel to your <xref:System.Windows.Forms.StatusBar> control.</span></span> <span data-ttu-id="d626e-112">Per informazioni dettagliate, vedere [Procedura: aggiungere pannelli a un controllo StatusBar](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).</span><span class="sxs-lookup"><span data-stu-id="d626e-112">For details, see [How to: Add Panels to a StatusBar Control](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).</span></span>  
  
4.  <span data-ttu-id="d626e-113">Per il <xref:System.Windows.Forms.StatusBar> controllo è stato aggiunto al form, impostare il <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="d626e-113">For the <xref:System.Windows.Forms.StatusBar> control you added to your form, set the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true`.</span></span>  
  
5.  <span data-ttu-id="d626e-114">Aggiungere un controllo Windows Form <xref:System.Windows.Forms.Timer> componente al form.</span><span class="sxs-lookup"><span data-stu-id="d626e-114">Add a Windows Forms <xref:System.Windows.Forms.Timer> component to the form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d626e-115">I moduli di Windows <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> componente è stato progettato per l'ambiente Windows Form.</span><span class="sxs-lookup"><span data-stu-id="d626e-115">The Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="d626e-116">Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="d626e-116">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
6.  <span data-ttu-id="d626e-117">Impostare la proprietà <xref:System.Windows.Forms.Timer.Enabled%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="d626e-117">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>  
  
7.  <span data-ttu-id="d626e-118">Impostare il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà del <xref:System.Windows.Forms.Timer> su 30000.</span><span class="sxs-lookup"><span data-stu-id="d626e-118">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> to 30000.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d626e-119">Il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà del <xref:System.Windows.Forms.Timer> viene impostato su 30 secondi (30.000 millisecondi) per garantire che l'ora esatta viene riflessa nel periodo di tempo visualizzato.</span><span class="sxs-lookup"><span data-stu-id="d626e-119">The <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> component is set to 30 seconds (30,000 milliseconds) to ensure that an accurate time is reflected in the time displayed.</span></span>  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a><span data-ttu-id="d626e-120">Per implementare il timer per l'aggiornamento della barra di stato</span><span class="sxs-lookup"><span data-stu-id="d626e-120">To implement the timer to update the status bar</span></span>  
  
1.  <span data-ttu-id="d626e-121">Inserire il codice seguente nel gestore dell'evento del <xref:System.Windows.Forms.Timer> componenti per aggiornare il pannello del <xref:System.Windows.Forms.StatusBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="d626e-121">Insert the following code into the event handler of the <xref:System.Windows.Forms.Timer> component to update the panel of the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     <span data-ttu-id="d626e-122">Ora è possibile eseguire l'applicazione per osservare l'orologio in funzione nel pannello della barra di stato.</span><span class="sxs-lookup"><span data-stu-id="d626e-122">At this point, you are ready to run the application and observe the clock running in the status bar panel.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="d626e-123">Per eseguire il test dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d626e-123">To test the application</span></span>  
  
1.  <span data-ttu-id="d626e-124">Effettuare il debug dell'applicazione, quindi premere F5 per eseguirla.</span><span class="sxs-lookup"><span data-stu-id="d626e-124">Debug the application and press F5 to run it.</span></span> <span data-ttu-id="d626e-125">Per informazioni dettagliate sul debug, vedere [Debug in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="d626e-125">For details about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d626e-126">Sono richiesti circa 30 secondi per visualizzare l'orologio sulla barra di stato.</span><span class="sxs-lookup"><span data-stu-id="d626e-126">It will take approximately 30 seconds for the clock to appear in the status bar.</span></span> <span data-ttu-id="d626e-127">per ottenere l'ora più accurata possibile.</span><span class="sxs-lookup"><span data-stu-id="d626e-127">This is to get the most accurate time possible.</span></span> <span data-ttu-id="d626e-128">Viceversa, per visualizzare più rapidamente l'orologio, è possibile ridurre il valore della <xref:System.Windows.Forms.Timer.Interval%2A> proprietà è impostata nel passaggio 7 nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="d626e-128">Conversely, to make the clock appear sooner, you can reduce the value of the <xref:System.Windows.Forms.Timer.Interval%2A> property you set in step 7 in the previous procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d626e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d626e-129">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="d626e-130">Procedura: Aggiungere pannelli a un controllo StatusBar</span><span class="sxs-lookup"><span data-stu-id="d626e-130">How to: Add Panels to a StatusBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 [<span data-ttu-id="d626e-131">Procedura: Individuare il pannello selezionato nel controllo StatusBar di Windows Form</span><span class="sxs-lookup"><span data-stu-id="d626e-131">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [<span data-ttu-id="d626e-132">Cenni preliminari sul controllo StatusBar</span><span class="sxs-lookup"><span data-stu-id="d626e-132">StatusBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
