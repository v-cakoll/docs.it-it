---
title: Eseguire routine a intervalli prestabiliti con componente timer
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
ms.openlocfilehash: dcc88beee947e2a83b426dcd2f3fd9d70c20fb67
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743120"
---
# <a name="how-to-run-procedures-at-set-intervals-with-the-windows-forms-timer-component"></a>Procedura: Eseguire routine a intervalli predefiniti con il componente Timer di Windows Form
A volte può essere necessario creare una routine che venga eseguita a intervalli di tempo specificati fino alla conclusione di un ciclo oppure al termine di un intervallo di tempo predefinito. Il componente <xref:System.Windows.Forms.Timer> rende possibile una procedura di questo tipo.  
  
 Questo componente è progettato per l'ambiente Windows Form. Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
> [!NOTE]
> L'uso del componente <xref:System.Windows.Forms.Timer> presenta alcune limitazioni. Per ulteriori informazioni, vedere [limitazioni della proprietà Interval del componente Timer Windows Forms](limitations-of-the-timer-component-interval-property.md).  
  
## <a name="to-run-a-procedure-at-set-intervals-with-the-timer-component"></a>Per eseguire una routine a intervalli predefiniti con il componente Timer  
  
1. Aggiungere un oggetto <xref:System.Windows.Forms.Timer> al form. Per informazioni su come eseguire questa operazione a livello di codice, vedere la sezione Esempio più avanti. Visual Studio offre anche il supporto per l'aggiunta di componenti a un modulo. Vedere anche [procedura: aggiungere controlli senza interfaccia utente per Windows Forms](how-to-add-controls-without-a-user-interface-to-windows-forms.md).  
  
2. Impostare la proprietà <xref:System.Windows.Forms.Timer.Interval%2A> (in millisecondi) per il timer. Questa proprietà determina il tempo che dovrà trascorrere prima che la routine venga eseguita nuovamente.  
  
    > [!NOTE]
    > Quanto maggiore è la frequenza con cui si verifica un evento timer, tanto maggiore sarà il tempo di attività del processore richiesto per rispondere all'evento. Ciò può rallentare le prestazioni complessive. Non impostare un intervallo minore del necessario.  
  
3. Scrivere il codice appropriato nel gestore eventi per <xref:System.Windows.Forms.Timer.Tick>. Il codice scritto in questo evento verrà eseguito con l'intervallo specificato nella proprietà <xref:System.Windows.Forms.Timer.Interval%2A>.  
  
4. Impostare la proprietà <xref:System.Windows.Forms.Timer.Enabled%2A> su `true` per avviare il timer. Si verificherà l'evento <xref:System.Windows.Forms.Timer.Tick> e la routine verrà eseguita con l'intervallo impostato.  
  
5. Al momento appropriato, impostare la proprietà <xref:System.Windows.Forms.Timer.Enabled%2A> su `false` per impedire che la routine venga eseguita di nuovo. L'impostazione dell'intervallo su `0` non comporta l'arresto del timer.  
  
## <a name="example"></a>Esempio  
 Questo primo esempio tiene traccia dell'ora del giorno in incrementi di un secondo. Usa un componente <xref:System.Windows.Forms.Button>, un componente <xref:System.Windows.Forms.Label>, e un componente <xref:System.Windows.Forms.Timer> in un form. La proprietà <xref:System.Windows.Forms.Timer.Interval%2A> è impostata su 1000, ovvero su un secondo. Nell'evento <xref:System.Windows.Forms.Timer.Tick> la didascalia dell'etichetta viene impostata sull'ora corrente. Quando si fa clic sul pulsante, la proprietà <xref:System.Windows.Forms.Timer.Enabled%2A> viene impostata su `false`, impedendo l'aggiornamento della didascalia dell'etichetta da parte del timer. Nell'esempio di codice seguente è necessario disporre di un form con un controllo <xref:System.Windows.Forms.Button> denominato `Button1`, un controllo <xref:System.Windows.Forms.Timer> denominato `Timer1`e un controllo <xref:System.Windows.Forms.Label> denominato `Label1`.  
  
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
  
## <a name="example"></a>Esempio  
 Questo secondo esempio di codice viene eseguita una routine ogni 600 millisecondi, fino al termine di un ciclo. Nell'esempio di codice seguente è necessario disporre di un form con un controllo <xref:System.Windows.Forms.Button> denominato `Button1`, un controllo <xref:System.Windows.Forms.Timer> denominato `Timer1`e un controllo <xref:System.Windows.Forms.Label> denominato `Label1`.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Timer>
- [Componente Timer](timer-component-windows-forms.md)
- [Panoramica sul componente Timer](timer-component-overview-windows-forms.md)
