---
title: Impostare e restituire date con il controllo DateTimePicker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], setting in DateTimePicker
- DateTimePicker control [Windows Forms], setting and returning dates
- examples [Windows Forms], DateTimePicker control
ms.assetid: a8a48d68-e4b5-426e-9764-51230fc9acd2
ms.openlocfilehash: 1e0aa58e98748ccde9411f0f4871adbae3a5f14d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747105"
---
# <a name="how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control"></a>Procedura: impostare e restituire date con il controllo DateTimePicker Windows Form
La data o l'ora selezionata nel controllo <xref:System.Windows.Forms.DateTimePicker> Windows Form è determinata dalla proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A>, che può essere impostata sulla proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A> prima della visualizzazione del controllo, ad esempio in fase di progettazione o nell'evento <xref:System.Windows.Forms.Form.Load>, per determinare la data che verrà inizialmente selezionata nel controllo. Per impostazione predefinita, la proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A> del controllo è impostata sulla data corrente. Se la proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A> del controllo viene modificata nel codice, il controllo viene automaticamente aggiornato nel form in base alla nuova impostazione.  
  
 La proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A> restituisce come valore una struttura <xref:System.DateTime>. Numerose proprietà della struttura <xref:System.DateTime> restituiscono informazioni specifiche sulla data visualizzata. Tali proprietà, tuttavia, possono essere usate solo per la restituzione di un valore, non per l'impostazione.  
  
- Per i valori relativi alla data, le proprietà <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A> e <xref:System.DateTime.Year%2A> restituiscono valori Integer per le unità di tempo corrispondenti della data selezionata. La proprietà <xref:System.DateTime.DayOfWeek%2A> restituisce un valore che indica il giorno della settimana selezionato. Per un elenco dei valori disponibili, vedere l'enumerazione <xref:System.DayOfWeek>.  
  
- Per i valori relativi all'ora, le proprietà <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A> e <xref:System.DateTime.Millisecond%2A> restituiscono valori Integer per le unità di tempo corrispondenti. Per configurare il controllo in modo da visualizzare gli orari, vedere [procedura: visualizzare l'ora con il controllo DateTimePicker](how-to-display-time-with-the-datetimepicker-control.md).  
  
### <a name="to-set-the-date-and-time-value-of-the-control"></a>Per impostare i valori di data e di ora del controllo  
  
- Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A> su un valore di data o di ora.  
  
    ```vb  
    DateTimePicker1.Value = New DateTime(2001, 10, 20)  
    ```  
  
    ```csharp  
    dateTimePicker1.Value = new DateTime(2001, 10, 20);  
    ```  
  
    ```cpp  
    dateTimePicker1->Value = DateTime(2001, 10, 20);  
    ```  
  
### <a name="to-return-the-date-and-time-value"></a>Per restituire il valore di data e di ora  
  
- Chiamare la proprietà <xref:System.Windows.Forms.DateTimePicker.Text%2A> per restituire il valore completo nel formato impostato per il controllo, oppure chiamare il metodo appropriato della proprietà <xref:System.Windows.Forms.DateTimePicker.Value%2A> per restituire una parte del valore. Usare <xref:System.Windows.Forms.DateTimePicker.ToString%2A> per convertire le informazioni in una stringa visualizzabile all'utente.  
  
    ```vb  
    MessageBox.Show("The selected value is ", DateTimePicker1.Text)  
    MessageBox.Show("The day of the week is ",   
       DateTimePicker1.Value.DayOfWeek.ToString)  
    MessageBox.Show("Millisecond is: ",   
       DateTimePicker1.Value.Millisecond.ToString)  
    ```  
  
    ```csharp  
    MessageBox.Show ("The selected value is " +   
       dateTimePicker1.Text);  
    MessageBox.Show ("The day of the week is " +   
       dateTimePicker1.Value.DayOfWeek.ToString());  
    MessageBox.Show("Millisecond is: " +   
       dateTimePicker1.Value.Millisecond.ToString());  
    ```  
  
    ```cpp  
    MessageBox::Show (String::Concat("The selected value is ",  
       dateTimePicker1->Text));  
    MessageBox::Show (String::Concat("The day of the week is ",  
       dateTimePicker1->Value.DayOfWeek.ToString()));  
    MessageBox::Show(String::Concat("Millisecond is: ",  
       dateTimePicker1->Value.Millisecond.ToString()));  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Controllo DateTimePicker](datetimepicker-control-windows-forms.md)
- [Procedura: Visualizzare una data in un formato personalizzato con il controllo DateTimePicker di Windows Form](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
