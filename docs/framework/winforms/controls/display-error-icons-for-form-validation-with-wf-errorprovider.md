---
title: 'Procedura: Visualizzare le icone di errore per la convalida dei moduli con il componente ErrorProvider di Windows Forms'
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
ms.openlocfilehash: 9487d4f82878ffefe17c576b16f654293ef01106
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316505"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>Procedura: Visualizzare le icone di errore per la convalida dei moduli con il componente ErrorProvider di Windows Forms
È possibile usare un controllo Windows Form <xref:System.Windows.Forms.ErrorProvider> componente per visualizzare un'icona di errore quando l'utente immette i dati non validi. È necessario disporre almeno due controlli sul form per scheda tra di essi e quindi richiamare il codice di convalida.  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>Per visualizzare un'icona di errore quando il valore di un controllo è valido  
  
1. Aggiungere due controlli, ad esempio, le caselle di testo, ovvero a un modulo di Windows.  
  
2. Aggiungere un <xref:System.Windows.Forms.ErrorProvider> componente al form.  
  
3. Selezionare il primo controllo e aggiungere codice al relativo <xref:System.Windows.Forms.Control.Validating> gestore dell'evento. Affinché il codice funzioni correttamente, la routine deve essere collegata all'evento. Per altre informazioni, vedere [Procedura: Creare i gestori eventi in fase di esecuzione per Windows Form](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Il codice seguente verifica la validità dei dati che immessi dall'utente; Se i dati non sono validi, il <xref:System.Windows.Forms.ErrorProvider.SetError%2A> viene chiamato il metodo. Il primo argomento del <xref:System.Windows.Forms.ErrorProvider.SetError%2A> metodo specifica che il controllo viene visualizzata l'icona accanto a. Il secondo argomento è il testo di errore da visualizzare.  
  
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
  
     (Visual c#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. Eseguire il progetto. Digitare i dati non validi (in questo esempio, non numerico) nel primo controllo e quindi passare al secondo. Quando viene visualizzata l'icona di errore, posizionare il puntatore del mouse per visualizzare il testo dell'errore.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [Panoramica del componente ErrorProvider](errorprovider-component-overview-windows-forms.md)
- [Procedura: Visualizzare gli errori all'interno di un set di dati con il componente ErrorProvider di Windows Forms](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
