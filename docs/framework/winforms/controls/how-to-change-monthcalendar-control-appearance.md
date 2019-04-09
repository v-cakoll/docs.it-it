---
title: "Procedura: Modificare l'aspetto del controllo MonthCalendar di Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: 233143099996759cc006b3f28b984938554a0d18
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199921"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a>Procedura: Modificare l'aspetto del controllo MonthCalendar di Windows Forms
I moduli di Windows <xref:System.Windows.Forms.MonthCalendar> controllo consente di personalizzare l'aspetto del calendario in molti modi. Ad esempio, è possibile impostare la combinazione di colori e scegliere di visualizzare o nascondere i numeri di settimana e la data corrente.  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>Per modificare lo schema di colori del calendario mensile  
  
-   Impostare proprietà quali <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> e <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>. Il <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> proprietà determina anche il colore del carattere per i giorni della settimana. Il <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> proprietà determina il colore delle date che precedono e seguono il mese visualizzato o mesi.  
  
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
    >  A partire da Windows Vista e a seconda del tema, l'impostazione di alcune proprietà potrebbero non modificare l'aspetto del calendario. Ad esempio, se Windows è impostato per utilizzare il tema Aero, impostando il <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, o <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> proprietà non ha alcun effetto. Questo avviene perché viene eseguito il rendering di una versione aggiornata del calendario con un aspetto che è derivato in fase di esecuzione dal tema del sistema operativo corrente. Se si desidera utilizzare queste proprietà e abilitare la versione precedente del calendario, è possibile disabilitare gli stili di visualizzazione per l'applicazione. La disabilitazione di stili potrebbe influenzare l'aspetto e il comportamento di altri controlli nell'applicazione. Per disabilitare gli stili di visualizzazione in Visual Basic, aprire Creazione progetti e deselezionare il **stili visivi XP abilitare** casella di controllo. Per disabilitare gli stili di visualizzazione in c#, aprire Program.cs e impostare come commento `Application.EnableVisualStyles();`. Per altre informazioni sugli stili di visualizzazione, vedere [attivazione di stili](/windows/desktop/controls/cookbook-overview).  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>Per visualizzare la data corrente nella parte inferiore del controllo  
  
-   Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> su `true`. L'esempio seguente attiva o disattiva la visualizzazione della data odierna quando fa doppio clic sul form.  
  
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
  
     (Visual c#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>Per visualizzare i numeri di settimana  
  
-   Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> su `true`. È possibile impostare questa proprietà nel codice o nella finestra Proprietà.  
  
     I numeri di settimana vengono visualizzati in un'altra colonna a sinistra del primo giorno della settimana.  
  
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

- [Controllo MonthCalendar](monthcalendar-control-windows-forms.md)
- [Procedura: Selezionare un intervallo di date nel controllo MonthCalendar di Windows Forms](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Procedura: Visualizzare giorni specifici in grassetto con il controllo MonthCalendar di Windows Forms](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [Procedura: Visualizzare più mesi nel controllo MonthCalendar di Windows Forms](display-more-than-one-month-wf-monthcalendar-control.md)
