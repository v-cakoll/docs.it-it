---
title: 'Procedura: Distinguere tra clic e doppio clic'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- mouse [Windows Forms], click
- mouse [Windows Forms], double-click
- mouse clicks [Windows Forms], single versus double
ms.assetid: d836ac8c-85bc-4f3a-a761-8aee03dc682c
ms.openlocfilehash: 2d02e8faac1dd55e2a7e64b00137df011c931f32
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707496"
---
# <a name="how-to-distinguish-between-clicks-and-double-clicks"></a>Procedura: Distinguere tra clic e doppio clic
In genere, un singolo *clic* avvia un'azione dell'interfaccia utente e un *doppio clic* estende l'azione. Ad esempio, un solo clic consente in genere di scegliere un elemento e un doppio clic consente di modificare l'elemento selezionato. Gli eventi Click in Windows Form, tuttavia, non si adattano facilmente a uno scenario in cui un clic e un doppio clic eseguono azioni incompatibili, perché un'azione associata all'evento <xref:System.Windows.Forms.Control.Click> o <xref:System.Windows.Forms.Control.MouseClick> viene eseguito prima dell'azione collegata all'evento <xref:System.Windows.Forms.Control.DoubleClick> o <xref:System.Windows.Forms.Control.MouseDoubleClick>. Questo argomento illustra due soluzioni a questo problema. Una soluzione consiste nel gestire l'evento di doppio clic e ripristinare le azioni nella gestione dell'evento Click. In rare situazioni potrebbe essere necessario simulare un comportamento di clic e doppio clic gestendo l'evento <xref:System.Windows.Forms.Control.MouseDown> e usando le proprietà <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> e <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> della classe <xref:System.Windows.Forms.SystemInformation>. A questo punto, si misura l'intervallo trascorso tra un clic e l'altro e, se viene eseguito un secondo clic prima che venga raggiunto il valore di <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> all'interno di un rettangolo definito da <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, eseguire l'azione di doppio clic; in caso contrario, eseguire l'azione di clic.  
  
### <a name="to-roll-back-a-click-action"></a>Per eseguire il rollback di un'azione di clic  
  
-   Assicurarsi che il controllo con cui si lavora disponga del comportamento standard di doppio clic. In caso contrario, abilitare il controllo con il metodo <xref:System.Windows.Forms.Control.SetStyle%2A>. Gestire l'evento di doppio clic ed eseguire il rollback dell'azione di clic, nonché dell'azione di doppio clic. L'esempio di codice seguente illustra come creare un pulsante personalizzato con doppio clic abilitato, nonché come eseguire il rollback dell'azione di clic nel codice di gestione dell'evento di doppio clic.  
  
     [!code-csharp[System.Windows.Forms.ButtonDoubleClick#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ButtonDoubleClick#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/VB/Form1.vb#1)]  
  
### <a name="to-distinguish-between-clicks-in-the-mousedown-event"></a>Per distinguere tra clic nell'evento MouseDown  
  
-   Gestire l'evento <xref:System.Windows.Forms.Control.MouseDown> e determinare la posizione e l'intervallo tra i clic usando le proprietà <xref:System.Windows.Forms.SystemInformation> appropriate e un componente <xref:System.Windows.Forms.Timer>. Eseguire l'azione appropriata a seconda che venga eseguito un clic o un doppio clic. Nell'esempio di codice seguente viene illustrato come procedere.  
  
     [!code-cpp[System.Windows.Forms.SingleVersusDoubleClick#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/cpp/form1.cpp#0)]
     [!code-csharp[System.Windows.Forms.SingleVersusDoubleClick#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/CS/form1.cs#0)]
     [!code-vb[System.Windows.Forms.SingleVersusDoubleClick#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi presentano i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questi esempi dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questi esempi in Visual Studio incollare il codice in nuovi progetti.  
  
## <a name="see-also"></a>Vedere anche
- [Input del mouse in un'applicazione Windows Forms](mouse-input-in-a-windows-forms-application.md)
