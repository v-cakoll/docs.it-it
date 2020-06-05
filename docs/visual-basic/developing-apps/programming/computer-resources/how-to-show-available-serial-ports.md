---
title: 'Procedura: Mostrare le porte seriali disponibili'
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, availability
- My.Computer.Ports.SerialPortNames property
- My.Computer.Ports object
- ports, serial port availability
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
ms.openlocfilehash: e7a9166f1879ed0850ca893bed307a0318298bbb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401823"
---
# <a name="how-to-show-available-serial-ports-in-visual-basic"></a>Procedura: mostrare le porte seriali disponibili in Visual Basic

Questo argomento descrive come usare `My.Computer.Ports` per visualizzare le porte seriali disponibili del computer in Visual Basic.  
  
 I nomi delle porte seriali sono disponibili in un controllo <xref:System.Windows.Forms.ListBox> per consentire agli utenti di selezionare la porta da usare.  
  
## <a name="example"></a>Esempio  

 Questo esempio esegue il ciclo attraverso tutte le stringhe restituite dalla proprietà `My.Computer.Ports.SerialPortNames`. Queste stringhe rappresentano i nomi delle porte seriali disponibili nel computer.  
  
 In genere, gli utenti selezionano la porta seriale che l'applicazione deve usare dall'elenco delle porte disponibili. In questo esempio i nomi delle porte seriali sono archiviati un controllo <xref:System.Windows.Forms.ListBox>. Per altre informazioni, vedere [Controllo ListBox](../../../../framework/winforms/controls/listbox-control-windows-forms.md).  
  
 [!code-vb[VbVbalrMyComputer#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#45)]  
  
 Questo esempio di codice è disponibile anche come frammento di codice IntelliSense. Nella selezione del frammento di codice si trova in **Connettività e rete**. Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  

 L'esempio presenta i requisiti seguenti:  
  
- Un riferimento del progetto a System.Windows.Forms.dll.  
  
- Accedere ai membri dello spazio dei nomi <xref:System.Windows.Forms>. Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo. Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
- Presenza all'interno del modulo di un controllo <xref:System.Windows.Forms.ListBox> denominato `ListBox1`.  
  
## <a name="robust-programming"></a>Programmazione efficiente  

 Non è necessario usare il controllo <xref:System.Windows.Forms.ListBox> per visualizzare i nomi delle porte seriali disponibili. In alternativa, è possibile usare un controllo <xref:System.Windows.Forms.ComboBox> o un altro controllo. Se l'applicazione non richiede una risposta da parte dell'utente, è possibile usare un controllo <xref:System.Windows.Forms.TextBox> per visualizzare le informazioni.  
  
> [!NOTE]
> I nomi delle porte restituiti da `My.Computer.Ports.SerialPortNames` potrebbero non essere corretti se l'applicazione viene eseguita con Windows 98. Per evitare errori dell'applicazione, usare la funzione di gestione delle eccezioni, ad esempio l'istruzione `Try...Catch...Finally` o `Using`, quando per aprire le porte si usano i nomi delle porte stesse.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [Procedura: Comporre numeri con modem collegati a porte seriali](how-to-dial-modems-attached-to-serial-ports.md)
- [Procedura: Inviare stringhe a porte seriali](how-to-send-strings-to-serial-ports.md)
- [Procedura: Ricevere stringhe da porte seriali](how-to-receive-strings-from-serial-ports.md)
