---
title: Visualizza le icone di errore per la convalida dei form con il componente ErrorProvider
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
ms.openlocfilehash: a1e346e332db489351f59c9a0c03ae731baf3dc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745904"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>Procedura: visualizzare le icone di errori per la convalida dei form con il componente ErrorProvider di Windows Form
È possibile utilizzare un componente Windows Forms <xref:System.Windows.Forms.ErrorProvider> per visualizzare un'icona di errore quando l'utente immette dati non validi. È necessario disporre di almeno due controlli sul form per eseguire una tabulazione tra di essi e richiamare quindi il codice di convalida.  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>Per visualizzare un'icona di errore quando il valore di un controllo non è valido  
  
1. Aggiungere due controlli, ad esempio caselle di testo, a un Windows Form.  
  
2. Aggiungere un componente <xref:System.Windows.Forms.ErrorProvider> al modulo.  
  
3. Selezionare il primo controllo e aggiungere il codice al gestore dell'evento <xref:System.Windows.Forms.Control.Validating>. Affinché il codice venga eseguito correttamente, è necessario che la procedura sia connessa all'evento. Per altre informazioni, vedere [procedura: creare gestori eventi in fase di esecuzione per Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Il codice seguente verifica la validità dei dati immessi dall'utente. Se i dati non sono validi, viene chiamato il metodo <xref:System.Windows.Forms.ErrorProvider.SetError%2A>. Il primo argomento del metodo <xref:System.Windows.Forms.ErrorProvider.SetError%2A> specifica il controllo a cui visualizzare l'icona accanto a. Il secondo argomento è il testo dell'errore da visualizzare.  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. Eseguire il progetto. Digitare non valido (in questo esempio, dati non numerici) nel primo controllo, quindi premere TAB per la seconda. Quando viene visualizzata l'icona di errore, puntare con il puntatore del mouse per visualizzare il testo dell'errore.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [Panoramica sul componente ErrorProvider](errorprovider-component-overview-windows-forms.md)
- [Procedura: Visualizzare errori in un dataset con il componente ErrorProvider di Windows Form](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
