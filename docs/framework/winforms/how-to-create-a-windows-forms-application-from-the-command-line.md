---
title: Creare un'applicazione Windows Form dalla riga di comandoCreate a Windows Forms application from the command line
titleSuffix: ''
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
ms.openlocfilehash: 7bd3add526a6b60d628b05d46eca22ce407c36b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181982"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a>Procedura: creare un'applicazione Windows Form dalla riga di comandoHow to: Create a Windows Forms application from the command line

Le procedure seguenti descrivono i passaggi di base che è necessario completare per creare ed eseguire un'applicazione Windows Forms dalla riga di comando. Esiste un supporto completo per queste procedure in Visual Studio.  Vedere [anche Procedura dettagliata: hosting di un controllo Windows Form in WPF.](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
  
## <a name="procedure"></a>Procedura  
  
#### <a name="to-create-the-form"></a>Per creare il form  
  
1. In un file di codice `Imports` `using` vuoto digitare le istruzioni seguenti:In an empty code file, type the following or statements:  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. Dichiarare una `Form1` classe denominata che eredita dalla classe Form:
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. Creare un costruttore `Form1`senza parametri per .
  
     Si aggiungerà il resto del codice al costruttore in una procedura successiva.
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. Aggiungere un metodo `Main` alla classe.
  
    1. Applicare <xref:System.STAThreadAttribute> il per `Main` il metodo di C , per specificare l'applicazione Windows Form è un apartment a thread singolo. L'attributo non è necessario in Visual Basic, poiché le applicazioni Windows Form sviluppate con Visual Basic utilizzano un modello di apartment a thread singolo per impostazione predefinita.  
  
    2. Chiamare <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> per applicare gli stili del sistema operativo all'applicazione.  
  
    3. Creare un'istanza del form ed eseguirla.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a>Per compilare l'applicazione ed eseguirla  
  
1. Al prompt dei comandi di .NET Framework passare alla directory creata per la classe `Form1`.  
  
2. Compilare il form.  
  
    - Se si utilizza C , digitare:`csc form1.cs`  
  
         `-or-`  
  
    - Se si utilizza Visual Basic, digitare:`vbc form1.vb`  
  
3. Al prompt dei comandi digitare: `Form1.exe`  
  
## <a name="adding-a-control-and-handling-an-event"></a>Aggiunta di un controllo e gestione di un evento

I passaggi della precedente procedura hanno illustrato come creare un Windows Form di base che viene compilato ed eseguito. La procedura successiva mostrerà come creare e aggiungere un controllo al form e come gestire un evento per il controllo. Per ulteriori informazioni sui controlli che è possibile aggiungere a Windows Form, vedere [Controlli Windows Form](./controls/index.md).
  
 Oltre a saper creare applicazioni Windows Forms, è consigliabile conoscere la programmazione basata sugli eventi e come gestire l'input utente. Per ulteriori informazioni, vedere [Creazione di gestori eventi in Windows Form](creating-event-handlers-in-windows-forms.md)e Gestione [dell'input dell'utente](./controls/handling-user-input.md)  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a>Per dichiarare un pulsante e gestirne l'evento click  
  
1. Dichiarare un pulsante denominato `button1`.  
  
2. Nel costruttore creare il pulsante e impostarne le proprietà <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> e <xref:System.Windows.Forms.Control.Text%2A>.  
  
3. Aggiungere il pulsante al form.  
  
     Esempio di codice seguente viene illustrato come dichiarare il controllo pulsante:The following code example demonstrates how to declare the button control:
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. Creare un metodo per gestire l'evento <xref:System.Windows.Forms.Control.Click> per il pulsante.  
  
5. Nel gestore dell'evento click visualizzare un oggetto <xref:System.Windows.Forms.MessageBox> con il messaggio "Hello World".  
  
     Esempio di codice seguente viene illustrato come gestire l'evento click del controllo pulsante:The following code example demonstrates how to handle the button control's click event:
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. Associare l'evento <xref:System.Windows.Forms.Control.Click> al metodo creato.  
  
     Nell'esempio di codice seguente viene illustrato come associare l'evento al metodo.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. Compilare ed eseguire l'applicazione come descritto nella precedente procedura.  
  
## <a name="example"></a>Esempio  

L'esempio di codice seguente è l'esempio completo delle procedure precedenti:The following code example is the complete example from the previous procedures:
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [Modifica dell'aspetto di Windows Form](changing-the-appearance-of-windows-forms.md)
- [Miglioramento delle applicazioni Windows Form](./advanced/index.md)
- [Guida introduttiva a Windows Forms](getting-started-with-windows-forms.md)
