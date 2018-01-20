---
title: "Procedura dettagliata: dimostrazione dell'ereditarietà visiva"
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
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c5ef33be9841b5c74b6ae2448daf56079489b61
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a>Procedura dettagliata: dimostrazione dell'ereditarietà visiva
L'ereditarietà visiva consente di visualizzare i controlli nel form di base e di aggiungere nuovi controlli. In questa procedura dettagliata verrà creato un form di base che verrà compilato in una libreria di classi. La libreria di classi verrà importata in un altro progetto e verrà creato un nuovo form che eredita dal form di base. Durante questa procedura dettagliata, si apprenderà come:  
  
-   Creare un progetto di libreria di classi contenente un form di base.  
  
-   Aggiungere un pulsante con proprietà che le classi derivate del form di base possono modificare.  
  
-   Aggiungere un pulsante che non può essere modificato dagli eredi del form di base.  
  
-   Creare un progetto contenente un form che eredita da `BaseForm`.  
  
 Infine, questa procedura dettagliata illustrerà la differenza tra controlli privati e protetti in un form ereditato.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
> [!CAUTION]
>  Non tutti i controlli supportano l'ereditarietà visiva da un form di base. I controlli seguenti non supportano lo scenario descritto in questa procedura dettagliata:  
>   
>  <xref:System.Windows.Forms.WebBrowser>  
>   
>  <xref:System.Windows.Forms.ToolStrip>  
>   
>  <xref:System.Windows.Forms.ToolStripPanel>  
>   
>  <xref:System.Windows.Forms.TableLayoutPanel>  
>   
>  <xref:System.Windows.Forms.FlowLayoutPanel>  
>   
>  <xref:System.Windows.Forms.DataGridView>  
>   
>  Questi controlli nel form ereditato sono sempre di sola lettura, indipendentemente dai modificatori usati (`private`, `protected` o `public`).  
  
## <a name="scenario-steps"></a>Passaggi dello scenario  
 Il primo passaggio consiste nella creazione del form di base.  
  
#### <a name="to-create-a-class-library-project-containing-a-base-form"></a>Per creare un progetto di libreria di classi contenente un form di base  
  
1.  Dal **File** menu, scegliere **New**e quindi **progetto** per aprire la **nuovo progetto** la finestra di dialogo.  
  
2.  Creare un'applicazione Windows Form denominata `BaseFormLibrary`.  
  
3.  Per creare una libreria di classi anziché un'applicazione Windows Form standard, in **Esplora**, fare doppio clic su di **BaseFormLibrary** nodo del progetto e quindi selezionare **proprietà**.  
  
4.  Nelle proprietà del progetto, modificare il **tipo di Output** da **applicazione Windows** a **libreria di classi**.  
  
5.  Dal **File** menu, scegliere **Salva tutto** per salvare il file di progetto e nel percorso predefinito.  
  
 Le due procedure seguenti consentono di aggiungere pulsanti al form di base. Per dimostrare l'ereditarietà visiva, si assegneranno ai pulsanti livelli di accesso diversi impostando le relative proprietà `Modifiers`.  
  
#### <a name="to-add-a-button-that-inheritors-of-the-base-form-can-modify"></a>Per aggiungere un pulsante che gli eredi del form di base possono modificare  
  
1.  Aprire **Form1** nella finestra di progettazione.  
  
2.  Nel **tutti i Windows Form** scheda della finestra di **della casella degli strumenti**, fare doppio clic su **pulsante** per aggiungere un pulsante al form. Usare il mouse per posizionare e ridimensionare il pulsante.  
  
3.  Nella finestra Proprietà impostare le seguenti proprietà del pulsante:  
  
    -   Impostare il **testo** proprietà **Say Hello**.  
  
    -   Impostare il **(nome)** proprietà **btnProtected**.  
  
    -   Impostare il**modificatori** proprietà **Protected**. Questo rende possibile per i form che ereditano da **Form1** per modificare le proprietà di **btnProtected**.  
  
4.  Fare doppio clic su di **Say Hello** pulsante per aggiungere un gestore eventi per il **fare clic su** evento.  
  
5.  Aggiungere la riga di codice seguente al gestore eventi:  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### <a name="to-add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a>Per aggiungere un pulsante che non può essere modificato dagli eredi del form di base  
  
1.  Passare alla visualizzazione Progettazione fare clic su di **Form1. vb [Design], Form1. cs [Design] o Form1.jsl [Progettazione]** scheda sopra l'editor di codice o premendo F7.  
  
2.  Aggiungere un secondo pulsante e impostarne le proprietà come indicato di seguito:  
  
    -   Impostare il **testo** proprietà **Say Goodbye**.  
  
    -   Impostare il **(nome)** proprietà **btnPrivate**.  
  
    -   Impostare il **modificatori** proprietà **privata**. Questo rende impossibile form che ereditano da **Form1** per modificare le proprietà di **btnPrivate**.  
  
3.  Fare doppio clic su di **Say Goodbye** pulsante per aggiungere un gestore eventi per il **fare clic su** evento. Inserire la riga di codice seguente nella routine evento:  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  Dal **compilare** menu, scegliere **BaseFormLibrary** per compilare la libreria di classi.  
  
     Dopo aver compilato la libreria, è possibile creare un nuovo progetto che eredita dal form appena creato.  
  
#### <a name="to-create-a-project-containing-a-form-that-inherits-from-the-base-form"></a>Per creare un progetto contenente un form che eredita dal form di base  
  
1.  Dal **File** menu, scegliere **Aggiungi** e quindi **nuovo progetto** per aprire la **Aggiungi nuovo progetto** la finestra di dialogo.  
  
2.  Creare un'applicazione Windows Form denominata `InheritanceTest`.  
  
#### <a name="to-add-an-inherited-form"></a>Per aggiungere un form ereditato  
  
1.  In **Esplora**, fare doppio clic sul **InheritanceTest** progetto, selezionare **Aggiungi**, quindi selezionare**nuovo elemento**.  
  
2.  Nel **Aggiungi nuovo elemento** la finestra di dialogo, seleziona il **Windows Form** categoria (se si dispone di un elenco di categorie) e quindi selezionare il **Form ereditato** modello.  
  
3.  Lasciare il nome predefinito di `Form2` e quindi fare clic su **Aggiungi**.  
  
4.  Nel **Selezione ereditarietà** nella finestra di dialogo **Form1** dal **BaseFormLibrary** progetto come form da cui ereditare e fare clic su **OK** .  
  
     Verrà creato un form nel **InheritanceTest** progetto da cui deriva il form in **BaseFormLibrary**.  
  
5.  Aprire il form ereditato (**Form2**) nella finestra di progettazione facendo doppio clic su esso, se non è già aperto.  
  
     Nella finestra di progettazione, i pulsanti ereditati dispongono di un simbolo (![Schermata VisualBasicInheritanceSymbol](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "vbInheritanceGlyph")) nell'angolo superiore, che indica che vengono ereditate.  
  
6.  Selezionare il **Say Hello** pulsante e osservare i quadratini di ridimensionamento. Poiché questo pulsante è protetto, gli eredi possono spostarlo, ridimensionarlo, modificarne la didascalia e apportare altre modifiche.  
  
7.  Selezionare privato **Say Goodbye** pulsante e notare che non dispone di quadratini di ridimensionamento. Inoltre, nel **proprietà** finestra, le proprietà di questo pulsante vengono visualizzate in grigio per indicare che non possono essere modificate.  
  
8.  Se si usa [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]:  
  
    1.  In **Esplora**, fare doppio clic su **Form1** nel **InheritanceTest** del progetto e quindi scegliere **eliminare**. Nella finestra di messaggio che viene visualizzato, fare clic su **OK** per confermare l'eliminazione.  
  
    2.  Aprire il file Program.cs e modificare la riga `Application.Run(new Form1());` in `Application.Run(new Form2());`.  
  
9. In **Esplora**, fare doppio clic su di **InheritanceTest** del progetto e selezionare **imposta come progetto di avvio**.  
  
10. In **Esplora**, fare doppio clic su di **InheritanceTest** del progetto e selezionare **proprietà**.  
  
11. Nel **InheritanceTest** pagine delle proprietà, impostare il **oggetto di avvio** per il form ereditato (**Form2**).  
  
12. Premere F5 per eseguire l'applicazione e osservare il comportamento del form ereditato.  
  
## <a name="next-steps"></a>Passaggi successivi  
 L'ereditarietà per i controlli utente funziona in modo analogo. Aprire un nuovo progetto di libreria di classi e aggiungere un controllo utente. Inserire controlli costitutivi e compilare il progetto. Aprire un altro progetto di libreria di classi e aggiungere un riferimento alla libreria di classi compilata. Inoltre, provare ad aggiungere un controllo ereditato (tramite il **aggiungere nuovi elementi** la finestra di dialogo) al progetto e l'utilizzo di **Selezione ereditarietà**. Aggiungere un controllo utente e modificare l'istruzione `Inherits` (`:` in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]). Per ulteriori informazioni, vedere [procedura: ereditare Windows Form](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: ereditare Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [Ereditarietà visiva di Windows Form](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [Windows Form](../../../../docs/framework/winforms/index.md)
