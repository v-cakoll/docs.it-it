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
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a>Procedura: modificare l'aspetto del controllo MonthCalendar Windows Form
Il controllo Windows Forms <xref:System.Windows.Forms.MonthCalendar> consente di personalizzare l'aspetto del calendario in molti modi. Ad esempio, è possibile impostare la combinazione di colori e scegliere di visualizzare o nascondere i numeri settimanali e la data corrente.  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>Per modificare la combinazione di colori del calendario mensile  
  
- Impostare proprietà quali <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> e <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>. La proprietà <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> determina anche il colore del carattere per i giorni della settimana. La proprietà <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> determina il colore delle date che precedono e seguono il mese o i mesi visualizzati.  
  
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
    > A partire da Windows Vista e a seconda del tema, l'impostazione di alcune proprietà potrebbe non modificare l'aspetto del calendario. Se, ad esempio, Windows è impostato in modo da utilizzare il tema Aero, l'impostazione delle proprietà <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>o <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> non ha alcun effetto. Questo perché una versione aggiornata del calendario viene sottoposta a rendering con un aspetto derivato in fase di esecuzione dal tema del sistema operativo corrente. Se si desidera utilizzare queste proprietà e abilitare la versione precedente del calendario, è possibile disabilitare gli stili visivi per l'applicazione. La disabilitazione degli stili di visualizzazione potrebbe influire sull'aspetto e sul comportamento di altri controlli nell'applicazione. Per disabilitare gli stili di visualizzazione in Visual Basic, aprire Progettazione progetti e deselezionare la casella di controllo **Abilita stili di visualizzazione XP** . Per disabilitare gli stili di C#visualizzazione in, aprire Program.cs e impostare come commento `Application.EnableVisualStyles();`. Per altre informazioni sugli stili di visualizzazione, vedere [Abilitazione degli stili di visualizzazione](/windows/desktop/controls/cookbook-overview).  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>Per visualizzare la data corrente nella parte inferiore del controllo  
  
- Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> su `true`. Nell'esempio seguente viene alternata la visualizzazione e l'omissione della data odierna quando si fa doppio clic sul form.  
  
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
  
     (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>Per visualizzare i numeri settimanali  
  
- Impostare la proprietà <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> su `true`. Questa proprietà può essere impostata nel codice o nel Finestra Proprietà.  
  
     I numeri settimanali vengono visualizzati in una colonna separata a sinistra del primo giorno della settimana.  
  
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
- [Procedura: Selezionare un intervallo di date nel controllo MonthCalendar di Windows Form](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Procedura: Visualizzare giorni specifici in grassetto con il controllo MonthCalendar di Windows Form](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [Procedura: Visualizzare più mesi nel controllo MonthCalendar di Windows Form](display-more-than-one-month-wf-monthcalendar-control.md)
