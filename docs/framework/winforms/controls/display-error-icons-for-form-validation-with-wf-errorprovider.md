---
title: 'Procedura: visualizzare le icone di errori per la convalida dei form con il componente ErrorProvider di Windows Form'
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
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 02638ab59c0ba1c0eb0f8090be118b3d5a9111f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>Procedura: visualizzare le icone di errori per la convalida dei form con il componente ErrorProvider di Windows Form
È possibile utilizzare un Windows Form <xref:System.Windows.Forms.ErrorProvider> componente per visualizzare un'icona di errore quando l'utente immette dati non validi. È necessario disporre di almeno due controlli nel form per scheda tra di essi e quindi richiamare il codice di convalida.  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>Per visualizzare un'icona di errore quando il valore di un controllo non è valido  
  
1.  Aggiungere due controlli, ad esempio, le caselle di testo, a un Windows Form.  
  
2.  Aggiungere un <xref:System.Windows.Forms.ErrorProvider> componente al form.  
  
3.  Selezionare il primo controllo e aggiungere codice al relativo <xref:System.Windows.Forms.Control.Validating> gestore dell'evento. Affinché questo codice venga eseguito correttamente, la procedura deve essere collegata all'evento. Per ulteriori informazioni, vedere [procedura: creare gestori eventi in fase di esecuzione per Windows Form](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Il codice seguente verifica la validità dei dati che immessi dall'utente; Se i dati non sono validi, il <xref:System.Windows.Forms.ErrorProvider.SetError%2A> metodo viene chiamato. Il primo argomento del <xref:System.Windows.Forms.ErrorProvider.SetError%2A> metodo consente di specificare il controllo da visualizzare accanto all'icona. Il secondo argomento è il testo di errore da visualizzare.  
  
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
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  Eseguire il progetto. Tipo di dati non valido (in questo esempio, non numerico) nel primo controllo e quindi passare al secondo. Quando viene visualizzata l'icona di errore, posizionare il puntatore del mouse per visualizzare il testo dell'errore.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>  
 [Panoramica sul componente ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [Procedura: Visualizzare errori in un dataset con il componente ErrorProvider di Windows Form](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)
