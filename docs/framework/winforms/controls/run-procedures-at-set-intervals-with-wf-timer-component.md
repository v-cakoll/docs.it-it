---
title: 'Procedura: eseguire routine a intervalli predefiniti con il componente Timer Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], timers
- timers [Windows Forms], event intervals
- initialization [Windows Forms], Timer components
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], initializing
- procedures [Windows Forms], specific time intervals
ms.assetid: 8025247a-2de4-4d86-b8ab-a8cb8aeab2ea
ms.openlocfilehash: bf0e22eab3b6517521dbe06a73f63af232746df1
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45529010"
---
# <a name="how-to-run-procedures-at-set-intervals-with-the-windows-forms-timer-component"></a><span data-ttu-id="d8b53-102">Procedura: eseguire routine a intervalli predefiniti con il componente Timer Windows Form</span><span class="sxs-lookup"><span data-stu-id="d8b53-102">How to: Run Procedures at Set Intervals with the Windows Forms Timer Component</span></span>
<span data-ttu-id="d8b53-103">A volte può essere necessario creare una routine che venga eseguita a intervalli di tempo specificati fino alla conclusione di un ciclo oppure al termine di un intervallo di tempo predefinito.</span><span class="sxs-lookup"><span data-stu-id="d8b53-103">You might sometimes want to create a procedure that runs at specific time intervals until a loop has finished or that runs when a set time interval has elapsed.</span></span> <span data-ttu-id="d8b53-104">Il componente <xref:System.Windows.Forms.Timer> rende possibile una procedura di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="d8b53-104">The <xref:System.Windows.Forms.Timer> component makes such a procedure possible.</span></span>  
  
 <span data-ttu-id="d8b53-105">Questo componente è progettato per l'ambiente Windows Form.</span><span class="sxs-lookup"><span data-stu-id="d8b53-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="d8b53-106">Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="d8b53-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8b53-107">L'uso del componente <xref:System.Windows.Forms.Timer> presenta alcune limitazioni.</span><span class="sxs-lookup"><span data-stu-id="d8b53-107">There are some limitations when using the <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="d8b53-108">Per altre informazioni, vedere [limitazioni della proprietà di Interval del componente Timer di Windows Form](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md).</span><span class="sxs-lookup"><span data-stu-id="d8b53-108">For more information, see [Limitations of the Windows Forms Timer Component's Interval Property](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md).</span></span>  
  
### <a name="to-run-a-procedure-at-set-intervals-with-the-timer-component"></a><span data-ttu-id="d8b53-109">Per eseguire una routine a intervalli predefiniti con il componente Timer</span><span class="sxs-lookup"><span data-stu-id="d8b53-109">To run a procedure at set intervals with the Timer component</span></span>  
  
1.  <span data-ttu-id="d8b53-110">Aggiungere un oggetto <xref:System.Windows.Forms.Timer> al form.</span><span class="sxs-lookup"><span data-stu-id="d8b53-110">Add a <xref:System.Windows.Forms.Timer> to your form.</span></span> <span data-ttu-id="d8b53-111">Per informazioni su come eseguire questa operazione a livello di codice, vedere la sezione Esempio più avanti.</span><span class="sxs-lookup"><span data-stu-id="d8b53-111">See the following Example section for an illustration of how to do this programmatically.</span></span> <span data-ttu-id="d8b53-112">Visual Studio offre inoltre supporto per l'aggiunta di componenti a un form.</span><span class="sxs-lookup"><span data-stu-id="d8b53-112">Visual Studio also has support for adding components to a form.</span></span> <span data-ttu-id="d8b53-113">Vedere anche [procedura: aggiungere controlli senza un'interfaccia utente a un Windows Form](https://msdn.microsoft.com/library/becyw7bz\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="d8b53-113">Also see [How to: Add Controls Without a User Interface to Windows Forms](https://msdn.microsoft.com/library/becyw7bz\(v=vs.110\)).</span></span>  
  
2.  <span data-ttu-id="d8b53-114">Impostare la proprietà <xref:System.Windows.Forms.Timer.Interval%2A> (in millisecondi) per il timer.</span><span class="sxs-lookup"><span data-stu-id="d8b53-114">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property (in milliseconds) for the timer.</span></span> <span data-ttu-id="d8b53-115">Questa proprietà determina il tempo che dovrà trascorrere prima che la routine venga eseguita nuovamente.</span><span class="sxs-lookup"><span data-stu-id="d8b53-115">This property determines how much time will pass before the procedure is run again.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8b53-116">Quanto maggiore è la frequenza con cui si verifica un evento timer, tanto maggiore sarà il tempo di attività del processore richiesto per rispondere all'evento.</span><span class="sxs-lookup"><span data-stu-id="d8b53-116">The more often a timer event occurs, the more processor time is used in responding to the event.</span></span> <span data-ttu-id="d8b53-117">Ciò può rallentare le prestazioni complessive.</span><span class="sxs-lookup"><span data-stu-id="d8b53-117">This can slow down overall performance.</span></span> <span data-ttu-id="d8b53-118">Non impostare un intervallo minore del necessario.</span><span class="sxs-lookup"><span data-stu-id="d8b53-118">Do not set a smaller interval than you need.</span></span>  
  
3.  <span data-ttu-id="d8b53-119">Scrivere il codice appropriato nel gestore eventi per <xref:System.Windows.Forms.Timer.Tick>.</span><span class="sxs-lookup"><span data-stu-id="d8b53-119">Write appropriate code in the <xref:System.Windows.Forms.Timer.Tick> event handler.</span></span> <span data-ttu-id="d8b53-120">Il codice scritto in questo evento verrà eseguito con l'intervallo specificato nella proprietà <xref:System.Windows.Forms.Timer.Interval%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8b53-120">The code you write in this event will run at the interval specified in the <xref:System.Windows.Forms.Timer.Interval%2A> property.</span></span>  
  
4.  <span data-ttu-id="d8b53-121">Impostare la proprietà <xref:System.Windows.Forms.Timer.Enabled%2A> su `true` per avviare il timer.</span><span class="sxs-lookup"><span data-stu-id="d8b53-121">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true` to start the timer.</span></span> <span data-ttu-id="d8b53-122">Si verificherà l'evento <xref:System.Windows.Forms.Timer.Tick> e la routine verrà eseguita con l'intervallo impostato.</span><span class="sxs-lookup"><span data-stu-id="d8b53-122">The <xref:System.Windows.Forms.Timer.Tick> event will begin to occur, running your procedure at the set interval.</span></span>  
  
5.  <span data-ttu-id="d8b53-123">Al momento appropriato, impostare la proprietà <xref:System.Windows.Forms.Timer.Enabled%2A> su `false` per impedire che la routine venga eseguita di nuovo.</span><span class="sxs-lookup"><span data-stu-id="d8b53-123">At the appropriate time, set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `false` to stop the procedure from running again.</span></span> <span data-ttu-id="d8b53-124">Impostazione dell'intervallo su `0` non causa l'arresto del timer.</span><span class="sxs-lookup"><span data-stu-id="d8b53-124">Setting the interval to `0` does not cause the timer to stop.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8b53-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8b53-125">Example</span></span>  
 <span data-ttu-id="d8b53-126">Questo primo esempio tiene traccia dell'ora del giorno in incrementi di un secondo.</span><span class="sxs-lookup"><span data-stu-id="d8b53-126">This first code example tracks the time of day in one-second increments.</span></span> <span data-ttu-id="d8b53-127">Usa un componente <xref:System.Windows.Forms.Button>, un componente <xref:System.Windows.Forms.Label>, e un componente <xref:System.Windows.Forms.Timer> in un form.</span><span class="sxs-lookup"><span data-stu-id="d8b53-127">It uses a <xref:System.Windows.Forms.Button>, a <xref:System.Windows.Forms.Label>, and a <xref:System.Windows.Forms.Timer> component on a form.</span></span> <span data-ttu-id="d8b53-128">La proprietà <xref:System.Windows.Forms.Timer.Interval%2A> è impostata su 1000, ovvero su un secondo.</span><span class="sxs-lookup"><span data-stu-id="d8b53-128">The <xref:System.Windows.Forms.Timer.Interval%2A> property is set to 1000 (equal to one second).</span></span> <span data-ttu-id="d8b53-129">Nell'evento <xref:System.Windows.Forms.Timer.Tick> la didascalia dell'etichetta viene impostata sull'ora corrente.</span><span class="sxs-lookup"><span data-stu-id="d8b53-129">In the <xref:System.Windows.Forms.Timer.Tick> event, the label's caption is set to the current time.</span></span> <span data-ttu-id="d8b53-130">Quando si fa clic sul pulsante, la proprietà <xref:System.Windows.Forms.Timer.Enabled%2A> viene impostata su `false`, impedendo l'aggiornamento della didascalia dell'etichetta da parte del timer.</span><span class="sxs-lookup"><span data-stu-id="d8b53-130">When the button is clicked, the <xref:System.Windows.Forms.Timer.Enabled%2A> property is set to `false`, stopping the timer from updating the label's caption.</span></span> <span data-ttu-id="d8b53-131">Esempio di codice seguente si suppone un form con un <xref:System.Windows.Forms.Button> controllo denominato `Button1`, un <xref:System.Windows.Forms.Timer> controllo denominato `Timer1`e un <xref:System.Windows.Forms.Label> controllo denominato `Label1`.</span><span class="sxs-lookup"><span data-stu-id="d8b53-131">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   ' Set to 1 second.  
   Timer1.Interval = 1000  
   ' Enable timer.  
   Timer1.Enabled = True  
   Button1.Text = "Enabled"  
End Sub  
x  
Private Sub Timer1_Tick(ByVal Sender As Object, ByVal e As EventArgs) Handles Timer1.Tick  
' Set the caption to the current time.  
   Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
      If Button1.Text = "Stop" Then  
         Button1.Text = "Start"  
         Timer1.Enabled = False  
      Else  
         Button1.Text = "Stop"  
         Timer1.Enabled = True  
      End If  
End Sub  
```  
  
```csharp  
private void InitializeTimer()  
{  
    // Call this procedure when the application starts.  
    // Set to 1 second.  
    Timer1.Interval = 1000;  
    Timer1.Tick += new EventHandler(Timer1_Tick);  
  
    // Enable timer.  
    Timer1.Enabled = true;  
  
    Button1.Text = "Stop";  
    Button1.Click += new EventHandler(Button1_Click);  
}  
  
private void Timer1_Tick(object Sender, EventArgs e)     
{  
   // Set the caption to the current time.  
   Label1.Text = DateTime.Now.ToString();  
}  
  
private void Button1_Click(object sender, EventArgs e)  
{  
  if ( Button1.Text == "Stop" )  
  {  
    Button1.Text = "Start";  
    Timer1.Enabled = false;  
  }  
  else  
  {  
    Button1.Text = "Stop";  
    Timer1.Enabled = true;  
  }  
}  
```  
  
```cpp  
private:  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      // Set to 1 second.  
      timer1->Interval = 1000;  
      // Enable timer.  
      timer1->Enabled = true;  
      this->timer1->Tick += gcnew System::EventHandler(this,    
                               &Form1::timer1_Tick);  
  
      button1->Text = S"Stop";  
      this->button1->Click += gcnew System::EventHandler(this,   
                               &Form1::button1_Click);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      // Set the caption to the current time.  
      label1->Text = DateTime::Now.ToString();  
   }  
  
   void button1_Click(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if ( button1->Text == "Stop" )  
      {  
         button1->Text = "Start";  
         timer1->Enabled = false;  
      }  
      else  
      {  
         button1->Text = "Stop";  
         timer1->Enabled = true;  
      }  
   }  
```  
  
## <a name="example"></a><span data-ttu-id="d8b53-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8b53-132">Example</span></span>  
 <span data-ttu-id="d8b53-133">Questo secondo esempio di codice viene eseguita una routine ogni 600 millisecondi, fino al termine di un ciclo.</span><span class="sxs-lookup"><span data-stu-id="d8b53-133">This second code example runs a procedure every 600 milliseconds until a loop has finished.</span></span> <span data-ttu-id="d8b53-134">Esempio di codice seguente si suppone un form con un <xref:System.Windows.Forms.Button> controllo denominato `Button1`, un <xref:System.Windows.Forms.Timer> controllo denominato `Timer1`e un <xref:System.Windows.Forms.Label> controllo denominato `Label1`.</span><span class="sxs-lookup"><span data-stu-id="d8b53-134">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
' This variable will be the loop counter.  
Private counter As Integer  
  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   counter = 0  
   Timer1.Interval = 600  
   Timer1.Enabled = True  
End Sub  
  
Private Sub Timer1_Tick(ByVal sender As Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
   If counter => 10 Then  
      ' Exit loop code.  
      Timer1.Enabled = False  
      counter = 0  
   Else  
      ' Run your procedure here.  
      ' Increment counter.  
      counter = counter + 1  
      Label1.Text = "Procedures Run: " & counter.ToString  
   End If  
End Sub  
```  
  
```csharp  
// This variable will be the loop counter.  
private int counter;  
  
private void InitializeTimer()  
{  
   // Run this procedure in an appropriate event.  
   counter = 0;  
   timer1.Interval = 600;  
   timer1.Enabled = true;  
   // Hook up timer's tick event handler.  
   this.timer1.Tick += new System.EventHandler(this.timer1_Tick);  
}  
  
private void timer1_Tick(object sender, System.EventArgs e)     
{  
   if (counter >= 10)   
   {  
      // Exit loop code.  
      timer1.Enabled = false;  
      counter = 0;  
   }  
   else  
   {  
      // Run your procedure here.  
      // Increment counter.  
      counter = counter + 1;  
      label1.Text = "Procedures Run: " + counter.ToString();  
      }  
}  
```  
  
```cpp  
private:  
   int counter;  
  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      counter = 0;  
      timer1->Interval = 600;  
      timer1->Enabled = true;  
      // Hook up timer's tick event handler.  
      this->timer1->Tick += gcnew System::EventHandler(this, &Form1::timer1_Tick);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if (counter >= 10)   
      {  
         // Exit loop code.  
         timer1->Enabled = false;  
         counter = 0;  
      }  
      else  
      {  
         // Run your procedure here.  
         // Increment counter.  
         counter = counter + 1;  
         label1->Text = String::Concat("Procedures Run: ",  
            counter.ToString());  
      }  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8b53-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8b53-135">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="d8b53-136">Componente Timer</span><span class="sxs-lookup"><span data-stu-id="d8b53-136">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="d8b53-137">Panoramica sul componente Timer</span><span class="sxs-lookup"><span data-stu-id="d8b53-137">Timer Component Overview</span></span>](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
