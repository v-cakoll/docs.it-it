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
ms.workload: dotnet
ms.openlocfilehash: b9c401532fa7a5f09462cf12084f32bca3f721cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-windows-forms-monthcalendar-control39s-appearance"></a>Procedura: modificare il controllo MonthCalendar Windows Form &#39; s aspetto
Windows Form <xref:System.Windows.Forms.MonthCalendar> controllo consente di personalizzare l'aspetto del calendario in molti modi. Ad esempio, è possibile impostare la combinazione di colori e scegliere di visualizzare o nascondere i numeri di settimana e la data corrente.  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>Per modificare la combinazione di colori del calendario mensile  
  
-   Impostare proprietà quali <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> e <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>. Il <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> proprietà determina anche il colore del carattere per i giorni della settimana. Il <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> proprietà determina il colore di date che precedono e seguono il mese visualizzato o mesi.  
  
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
    >  A partire da Windows Vista e a seconda del tema, l'impostazione di alcune proprietà potrebbe non modificare l'aspetto del calendario. Ad esempio, se Windows è impostato per utilizzare il tema Aero, impostando il <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, o <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> proprietà non ha alcun effetto. In questo modo viene eseguito il rendering di una versione aggiornata del calendario con un aspetto derivato in fase di esecuzione dal tema del sistema operativo corrente. Se si desidera utilizzare queste proprietà e abilitare la versione precedente del calendario, è possibile disabilitare gli stili di visualizzazione per l'applicazione. La disabilitazione degli stili potrebbe influenzare l'aspetto e il comportamento di altri controlli nell'applicazione. Per disabilitare gli stili di visualizzazione in Visual Basic, aprire la finestra di progettazione del progetto e deselezionare il **gli stili visivi XP abilitare** casella di controllo. Per disabilitare gli stili di visualizzazione in c#, aprire Program.cs e impostare come commento `Application.EnableVisualStyles();`. Per ulteriori informazioni sugli stili, vedere [procedura: abilitare gli stili di visualizzazione di Windows XP](http://msdn.microsoft.com/en-us/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>Per visualizzare la data corrente nella parte inferiore del controllo  
  
-   Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> su `true`. Nell'esempio seguente attiva o disattiva la visualizzazione della data odierna quando il modulo si fa doppio clic.  
  
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
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>Per visualizzare i numeri di settimana  
  
-   Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> su `true`. È possibile impostare questa proprietà nel codice o nella finestra Proprietà.  
  
     Numeri di settimana vengono visualizzati in una colonna separata a sinistra del primo giorno della settimana.  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [Procedura: Selezionare un intervallo di date nel controllo MonthCalendar di Windows Form](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [Procedura: Visualizzare giorni specifici in grassetto con il controllo MonthCalendar di Windows Form](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)  
 [Procedura: Visualizzare più mesi nel controllo MonthCalendar di Windows Form](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
