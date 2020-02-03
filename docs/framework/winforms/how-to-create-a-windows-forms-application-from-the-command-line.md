---
title: Creare una Windows Forms Application dalla riga di comando
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
ms.openlocfilehash: da6b9da53a36a44233dde4f0d1c4f147d913c7cf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739533"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a>Procedura: creare una Windows Forms Application dalla riga di comando

Le procedure seguenti descrivono i passaggi di base che è necessario completare per creare ed eseguire un'applicazione Windows Forms dalla riga di comando. Esiste un supporto completo per queste procedure in Visual Studio.  Vedere anche [procedura dettagliata: hosting di un controllo Windows Forms in WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).
  
## <a name="procedure"></a>Routine  
  
#### <a name="to-create-the-form"></a>Per creare il form  
  
1. In un file di codice vuoto digitare il `Imports` o le istruzioni `using` seguenti:  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. Dichiarare una classe denominata `Form1` che eredita dalla classe form:
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. Creare un costruttore senza parametri per `Form1`.
  
     Si aggiungerà il resto del codice al costruttore in una procedura successiva.
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. Aggiungere un metodo `Main` alla classe.
  
    1. Applicare il <xref:System.STAThreadAttribute> al metodo C# `Main` per specificare che il Windows Forms Application è un Apartment a thread singolo. L'attributo non è necessario in Visual Basic, poiché le applicazioni Windows Forms sviluppate con Visual Basic usano un modello di Apartment a thread singolo per impostazione predefinita.  
  
    2. Chiamare <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> per applicare gli stili del sistema operativo all'applicazione.  
  
    3. Creare un'istanza del form ed eseguirla.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a>Per compilare l'applicazione ed eseguirla  
  
1. Al prompt dei comandi di .NET Framework passare alla directory creata per la classe `Form1`.  
  
2. Compilare il form.  
  
    - Se si usa C#, digitare: `csc form1.cs`  
  
         `-or-`  
  
    - Se si utilizza Visual Basic, digitare: `vbc form1.vb`  
  
3. Al prompt dei comandi digitare: `Form1.exe`  
  
## <a name="adding-a-control-and-handling-an-event"></a>Aggiunta di un controllo e gestione di un evento

I passaggi della precedente procedura hanno illustrato come creare un Windows Form di base che viene compilato ed eseguito. La procedura successiva mostrerà come creare e aggiungere un controllo al form e come gestire un evento per il controllo. Per ulteriori informazioni sui controlli che è possibile aggiungere a Windows Forms, vedere [controlli di Windows Forms](./controls/index.md).
  
 Oltre a saper creare applicazioni Windows Forms, è consigliabile conoscere la programmazione basata sugli eventi e come gestire l'input utente. Per altre informazioni, vedere [creazione di gestori eventi in Windows Forms](creating-event-handlers-in-windows-forms.md)e [gestione dell'input dell'utente](./controls/handling-user-input.md)  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a>Per dichiarare un pulsante e gestirne l'evento click  
  
1. Dichiarare un pulsante denominato `button1`.  
  
2. Nel costruttore creare il pulsante e impostarne le proprietà <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> e <xref:System.Windows.Forms.Control.Text%2A>.  
  
3. Aggiungere il pulsante al form.  
  
     Nell'esempio di codice riportato di seguito viene illustrato come dichiarare il controllo Button:
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. Creare un metodo per gestire l'evento <xref:System.Windows.Forms.Control.Click> per il pulsante.  
  
5. Nel gestore dell'evento click visualizzare un oggetto <xref:System.Windows.Forms.MessageBox> con il messaggio "Hello World".  
  
     Nell'esempio di codice riportato di seguito viene illustrato come gestire l'evento click del controllo Button:
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. Associare l'evento <xref:System.Windows.Forms.Control.Click> al metodo creato.  
  
     Nell'esempio di codice seguente viene illustrato come associare l'evento al metodo.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. Compilare ed eseguire l'applicazione come descritto nella precedente procedura.  
  
## <a name="example"></a>Esempio  
 
L'esempio di codice seguente è l'esempio completo delle procedure precedenti:
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [Modifica dell'aspetto di Windows Form](changing-the-appearance-of-windows-forms.md)
- [Miglioramento delle applicazioni Windows Form](./advanced/index.md)
- [Guida introduttiva a Windows Form](getting-started-with-windows-forms.md)
