---
title: 'Procedura dettagliata: utilizzo del controllo MaskedTextBox'
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
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06b8ffd2bda9597198d94c99a785c59cc7cc052e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>Procedura dettagliata: utilizzo del controllo MaskedTextBox
Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   L'inizializzazione di <xref:System.Windows.Forms.MaskedTextBox> controllo  
  
-   Utilizzo di <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> gestore eventi per avvertire l'utente quando un carattere non è conforme alla maschera  
  
-   Assegnazione di un tipo per il <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> proprietà e utilizzando il <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> gestore eventi per avvertire l'utente quando il valore di cui si sta tentando di eseguire il commit non è valido per il tipo di  
  
## <a name="creating-the-project-and-adding-a-control"></a>Creazione del progetto e aggiungendo un controllo  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>Per aggiungere un controllo MaskedTextBox al form  
  
1.  Aprire il form in cui si desidera posizionare il <xref:System.Windows.Forms.MaskedTextBox> controllo.  
  
2.  Trascinare un <xref:System.Windows.Forms.MaskedTextBox> controllo il **della casella degli strumenti** al form.  
  
3.  Il pulsante destro del controllo e scegliere **proprietà**. Nel **proprietà** finestra, seleziona il **Mask** proprietà e fare clic su di **...**  (pulsante) accanto al nome della proprietà.  
  
4.  Nel **maschera di Input** la finestra di dialogo, seleziona il **data breve** mascherare e fare clic su **OK**.  
  
5.  Nel **proprietà** finestra set di <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> proprietà `true`. Questa proprietà determina un breve segnale acustico ogni volta che l'utente tenta di un carattere che viola la definizione della maschera di input.  
  
 Per un riepilogo dei caratteri che supporta la proprietà maschera, vedere la sezione Note della <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.  
  
## <a name="alert-the-user-to-input-errors"></a>Avvisare l'utente per gli errori di Input  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>Aggiungere una descrizione comandi per l'input maschera rifiutato  
  
1.  Restituito per il **della casella degli strumenti** e aggiungere un <xref:System.Windows.Forms.ToolTip> al form.  
  
2.  Creare un gestore eventi per il <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> evento che genera il <xref:System.Windows.Forms.ToolTip> quando si verifica un errore di input. Il fumetto suggerimento rimane visibile per cinque secondi o fino a quando l'utente fa clic.  
  
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
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>Avvisare l'utente a un tipo che non è valido  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>Aggiungere una descrizione comandi per i tipi di dati non validi  
  
1.  Del modulo <xref:System.Windows.Forms.Form.Load> gestore dell'evento, assegnare un <xref:System.Type> oggetto che rappresenta il <xref:System.DateTime> tipo di <xref:System.Windows.Forms.MaskedTextBox> del controllo <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> proprietà:  
  
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
  
2.  Aggiungere un gestore eventi per l'evento <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>:  
  
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
 <xref:System.Windows.Forms.MaskedTextBox>  
 [Controllo MaskedTextBox](../../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)
