---
title: "Procedura: Creare un'applicazione Windows Forms dalla riga di comando"
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91261e5077352179719e631ebeb26670ffd74792
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665237"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a>Procedura: Creare un'applicazione Windows Forms dalla riga di comando
Le procedure seguenti descrivono i passaggi di base che è necessario completare per creare ed eseguire un'applicazione Windows Forms dalla riga di comando. Esiste un supporto completo per queste procedure in Visual Studio.  Vedere anche [procedura dettagliata: Controllo che ospita un Windows Form in WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).  
  
## <a name="procedure"></a>Routine  
  
#### <a name="to-create-the-form"></a>Per creare il form  
  
1. In un file di codice vuoto digitare le istruzioni import o using seguenti:  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. Dichiarare una classe denominata `Form1` che eredita dalla classe Form.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. Creare un costruttore predefinito per `Form1`.  
  
     Si aggiungerà il resto del codice al costruttore in una procedura successiva.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. Aggiungere un metodo `Main` alla classe.  
  
    1. Si applicano i <xref:System.STAThreadAttribute> c# `Main` metodo per specificare l'applicazione Windows Forms è un apartment a thread singolo. (L'attributo non è necessario in Visual Basic, poiché le applicazioni di Windows forms sviluppate con Visual Basic usare un modello di apartment a thread singolo per impostazione predefinita.)  
  
    2. Chiamare <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> per applicare gli stili del sistema operativo all'applicazione.  
  
    3. Creare un'istanza del form ed eseguirla.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a>Per compilare l'applicazione ed eseguirla  
  
1. Al prompt dei comandi di .NET Framework passare alla directory creata per la classe `Form1`.  
  
2. Compilare il form.  
  
    - Se si usa c#, digitare: `csc form1.cs`  
  
         `-or-`  
  
    - Se si utilizza Visual Basic, digitare: `vbc form1.vb`  
  
3. Al prompt dei comandi, digitare: `Form1.exe`  
  
## <a name="adding-a-control-and-handling-an-event"></a>Aggiunta di un controllo e gestione di un evento  
 I passaggi della precedente procedura hanno illustrato come creare un Windows Form di base che viene compilato ed eseguito. La procedura successiva mostrerà come creare e aggiungere un controllo al form e come gestire un evento per il controllo. Per altre informazioni sui controlli è possibile aggiungere a un Windows Form, vedere [Windows Forms Controls](./controls/index.md).  
  
 Oltre a saper creare applicazioni Windows Forms, è consigliabile conoscere la programmazione basata sugli eventi e come gestire l'input utente. Per altre informazioni, vedere [creazione di gestori di eventi in Windows Form](creating-event-handlers-in-windows-forms.md), e [la gestione degli Input dell'utente](./controls/handling-user-input.md)  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a>Per dichiarare un pulsante e gestirne l'evento click  
  
1. Dichiarare un pulsante denominato `button1`.  
  
2. Nel costruttore creare il pulsante e impostarne le proprietà <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> e <xref:System.Windows.Forms.Control.Text%2A>.  
  
3. Aggiungere il pulsante al form.  
  
     Nell'esempio di codice seguente viene illustrato come dichiarare il pulsante.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. Creare un metodo per gestire l'evento <xref:System.Windows.Forms.Control.Click> per il pulsante.  
  
5. Nel gestore dell'evento click visualizzare un oggetto <xref:System.Windows.Forms.MessageBox> con il messaggio "Hello World".  
  
     Nell'esempio di codice seguente viene illustrato come gestire l'evento click del pulsante.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. Associare l'evento <xref:System.Windows.Forms.Control.Click> al metodo creato.  
  
     Nell'esempio di codice seguente viene illustrato come associare l'evento al metodo.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. Compilare ed eseguire l'applicazione come descritto nella precedente procedura.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente è l'esempio completo tratto dalle precedenti procedure.  
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Per compilare il codice, seguire le istruzioni disponibili nella procedura che descrive come compilare ed eseguire l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [Modifica dell'aspetto di Windows Form](changing-the-appearance-of-windows-forms.md)
- [Miglioramento delle applicazioni Windows Form](./advanced/index.md)
- [Guida introduttiva a Windows Form](getting-started-with-windows-forms.md)
