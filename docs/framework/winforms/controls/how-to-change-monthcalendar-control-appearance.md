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
ms.openlocfilehash: 5582624d881b2d8039bcd5e8ac45e548c7b38f57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929041"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a>Procedura: Modificare l'aspetto del controllo MonthCalendar di Windows Forms
Il controllo <xref:System.Windows.Forms.MonthCalendar> Windows Forms consente di personalizzare l'aspetto del calendario in molti modi. Ad esempio, è possibile impostare la combinazione di colori e scegliere di visualizzare o nascondere i numeri settimanali e la data corrente.  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>Per modificare la combinazione di colori del calendario mensile  
  
- Impostare proprietà quali <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> e <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>. La <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> proprietà determina anche il colore del carattere per i giorni della settimana. La <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> proprietà determina il colore delle date che precedono e seguono il mese o i mesi visualizzati.  
  
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
    > A partire da Windows Vista e a seconda del tema, l'impostazione di alcune proprietà potrebbe non modificare l'aspetto del calendario. Se, ad esempio, Windows è impostato in modo da utilizzare il tema Aero <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>l'impostazione delle <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> proprietà,, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>o non ha alcun effetto. Questo perché una versione aggiornata del calendario viene sottoposta a rendering con un aspetto derivato in fase di esecuzione dal tema del sistema operativo corrente. Se si desidera utilizzare queste proprietà e abilitare la versione precedente del calendario, è possibile disabilitare gli stili visivi per l'applicazione. La disabilitazione degli stili di visualizzazione potrebbe influire sull'aspetto e sul comportamento di altri controlli nell'applicazione. Per disabilitare gli stili di visualizzazione in Visual Basic, aprire Progettazione progetti e deselezionare la casella di controllo **Abilita stili di visualizzazione XP** . Per disabilitare gli stili di C#visualizzazione in, aprire Program.cs e `Application.EnableVisualStyles();`impostare come commento. Per altre informazioni sugli stili di visualizzazione, vedere Abilitazione degli [stili di visualizzazione](/windows/desktop/controls/cookbook-overview).  
  
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
- [Procedura: Selezionare un intervallo di date nel controllo Windows Forms MonthCalendar](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Procedura: Visualizza giorni specifici in grassetto con il controllo Windows Forms MonthCalendar](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [Procedura: Visualizza più di un mese nel controllo Windows Forms MonthCalendar](display-more-than-one-month-wf-monthcalendar-control.md)
