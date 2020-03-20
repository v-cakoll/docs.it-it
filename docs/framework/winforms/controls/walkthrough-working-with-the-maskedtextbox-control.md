---
title: 'Procedura dettagliata: utilizzo del controllo MaskedTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: db32b3ec88a07747ea3e286af9f04edce3f1ba3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182070"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>Procedura dettagliata: utilizzo del controllo MaskedTextBox
Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
- Inizializzazione <xref:System.Windows.Forms.MaskedTextBox> del controllo  
  
- Utilizzo <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> del gestore eventi per avvisare l'utente quando un carattere non è conforme alla maschera  
  
- L'assegnazione di <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> un tipo <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> alla proprietà e l'utilizzo del gestore eventi per avvisare l'utente quando il valore che sta tentando di eseguire il commit non è valido per il tipoAssigning a type to the property and using the event handler to alert the user when the value they're attempting to commit is not valid for the type  
  
## <a name="creating-the-project-and-adding-a-control"></a>Creazione del progetto e aggiunta di un controlloCreating the Project and Adding a Control  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>Per aggiungere un controllo MaskedTextBox al form  
  
1. Aprire il modulo in cui <xref:System.Windows.Forms.MaskedTextBox> si desidera inserire il controllo.  
  
2. Trascinare <xref:System.Windows.Forms.MaskedTextBox> un controllo dalla **Casella degli strumenti** al form.  
  
3. Fare clic con il pulsante destro del mouse sul controllo e scegliere **Proprietà**. Nella finestra **Proprietà** selezionare la proprietà **Maschera** e fare clic sul pulsante **...** (ellini) accanto al nome della proprietà.  
  
4. Nella finestra di dialogo **Maschera di input,** selezionare la maschera **Data breve** e fare clic su **OK**.  
  
5. Nella finestra **Proprietà** <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> impostare `true`la proprietà su . Questa proprietà genera un breve e-beep da suonare ogni volta che l'utente tenta di immettere un carattere che viola la definizione della maschera.  
  
 Per un riepilogo dei caratteri supportati dalla proprietà Mask, <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> vedere la sezione Osservazioni della proprietà.  
  
## <a name="alert-the-user-to-input-errors"></a>Avvisare l'utente di errori di input  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>Aggiungere un suggerimento per l'input maschera rifiutato  
  
1. Tornare alla casella degli <xref:System.Windows.Forms.ToolTip> **strumenti** e aggiungere a al form.  
  
2. Creare un gestore <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> eventi per <xref:System.Windows.Forms.ToolTip> l'evento che genera l'oggetto quando si verifica un errore di input. Il suggerimento del fumetto rimane visibile per cinque secondi o finché l'utente non fa clic su di esso.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>Avvisare l'utente di un tipo non valido  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>Aggiungere un suggerimento per tipi di dati non validiAdd a balloon tip for invalid data types  
  
1. Nel gestore <xref:System.Windows.Forms.Form.Load> eventi del form <xref:System.Type> assegnare <xref:System.DateTime> un oggetto <xref:System.Windows.Forms.MaskedTextBox> che <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> rappresenta il tipo alla proprietà del controllo:  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. Aggiungere un gestore eventi per l'evento <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>:  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MaskedTextBox>
- [Controllo MaskedTextBox](maskedtextbox-control-windows-forms.md)
