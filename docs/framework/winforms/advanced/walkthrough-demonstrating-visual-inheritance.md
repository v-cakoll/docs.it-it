---
title: "Procedura dettagliata: Dimostrazione dell'ereditarietà visiva"
ms.date: 03/30/2017
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
ms.openlocfilehash: 6fd504269ae9afbfd02b58276582a644674e1e0f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040317"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a>Procedura dettagliata: Dimostrazione dell'ereditarietà visiva

L'ereditarietà visiva consente di visualizzare i controlli nel form di base e di aggiungere nuovi controlli. In questa procedura dettagliata verrà creato un form di base che verrà compilato in una libreria di classi. La libreria di classi verrà importata in un altro progetto e verrà creato un nuovo form che eredita dal form di base. Durante questa procedura dettagliata, si apprenderà come:

- Creare un progetto di libreria di classi contenente un form di base.

- Aggiungere un pulsante con proprietà che le classi derivate del form di base possono modificare.

- Aggiungere un pulsante che non può essere modificato dagli eredi del form di base.

- Creare un progetto contenente un form che eredita da `BaseForm`.

Infine, questa procedura dettagliata illustrerà la differenza tra controlli privati e protetti in un form ereditato.

> [!CAUTION]
> Non tutti i controlli supportano l'ereditarietà visiva da un form di base. I controlli seguenti non supportano lo scenario descritto in questa procedura dettagliata:
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

## <a name="create-a-class-library-project-containing-a-base-form"></a>Creare un progetto di libreria di classi contenente un form di base

1. In Visual Studio scegliere **nuovo** > **progetto** dal menu **file** per aprire la finestra di dialogo **nuovo progetto** .

2. Creare una Windows Forms Application denominata `BaseFormLibrary`.

3. Per creare una libreria di classi anziché una Windows Forms Application standard, in **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo del progetto **BaseFormLibrary** , quindi scegliere **proprietà**.

4. Nelle proprietà del progetto modificare il **tipo di output** da **applicazione Windows** a libreria di **classi**.

5. Scegliere **Salva tutto** dal menu **file** per salvare il progetto e i file nel percorso predefinito.

 Le due procedure seguenti consentono di aggiungere pulsanti al form di base. Per dimostrare l'ereditarietà visiva, si assegneranno ai pulsanti livelli di accesso diversi impostando le relative proprietà `Modifiers`.

## <a name="add-a-button-that-inheritors-of-the-base-form-can-modify"></a>Aggiungere un pulsante che gli eredi del form di base possono modificare

1. Aprire **Form1** nella finestra di progettazione.

2. Nella scheda **tutti Windows Forms** della **casella degli strumenti**fare doppio clic sul **pulsante** per aggiungere un pulsante al form. Usare il mouse per posizionare e ridimensionare il pulsante.

3. Nella finestra Proprietà impostare le seguenti proprietà del pulsante:

    - Impostare la proprietà **Text** su **Say Hello**.

    - Impostare la proprietà **(Name)** su **btnProtected**.

    - Impostare la proprietà Modifiers su **protected**. Ciò rende possibile per i form che ereditano da **Form1** per modificare le proprietà di **btnProtected**.

4. Fare doppio clic sul pulsante **Say Hello** per aggiungere un gestore eventi per l'evento **Click** .

5. Aggiungere la riga di codice seguente al gestore eventi:

    ```vb
    MessageBox.Show("Hello, World!")
    ```

    ```csharp
    MessageBox.Show("Hello, World!");
    ```

## <a name="add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a>Aggiungere un pulsante che non può essere modificato dagli eredi del form di base

1. Passare alla visualizzazione progettazione facendo clic sulla scheda **Form1. vb [Design], Form1.cs [Design] o Form1. jsl [Progettazione]** sopra l'editor di codice o premendo F7.

2. Aggiungere un secondo pulsante e impostarne le proprietà come indicato di seguito:

    - Impostare la proprietà **Text** su **Say Goodbye**.

    - Impostare la proprietà **(Name)** su **btnPrivate**.

    - Impostare la proprietà Modifiers su **private**. Ciò rende impossibile per i form che ereditano da **Form1** per modificare le proprietà di **btnPrivate**.

3. Fare doppio clic sul pulsante **Say Goodbye** per aggiungere un gestore eventi per l'evento **Click** . Inserire la riga di codice seguente nella routine evento:

    ```vb
    MessageBox.Show("Goodbye!")
    ```

    ```csharp
    MessageBox.Show("Goodbye!");
    ```

4. Dal menu **Compila** scegliere **Compila libreria BaseFormLibrary** per compilare la libreria di classi.

     Dopo aver compilato la libreria, è possibile creare un nuovo progetto che eredita dal form appena creato.

## <a name="create-a-project-containing-a-form-that-inherits-from-the-base-form"></a>Creare un progetto contenente un form che eredita dal form di base

1. Dal menu **file** scegliere **Aggiungi** , quindi **nuovo progetto** per aprire la finestra di dialogo **Aggiungi nuovo progetto** .

2. Creare una Windows Forms Application denominata `InheritanceTest`.

## <a name="add-an-inherited-form"></a>Aggiungere un form ereditato

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **InheritanceTest** , scegliere **Aggiungi**, quindi selezionare **nuovo elemento**.

2. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare la categoria **Windows Forms** (se si dispone di un elenco di categorie), quindi selezionare il modello di **modulo ereditato** .

3. Lasciare il nome `Form2` predefinito e quindi fare clic su **Aggiungi**.

4. Nella finestra di dialogo **Selezione ereditarietà** selezionare **Form1** dal progetto **BaseFormLibrary** come modulo da cui ereditare e fare clic su **OK**.

     In questo modo viene creato un modulo nel progetto **InheritanceTest** che deriva dal form in **BaseFormLibrary**.

5. Aprire il form ereditato (**Form2**) nella finestra di progettazione facendo doppio clic su di esso, se non è già aperto.

     Nella finestra di progettazione i pulsanti ereditati hanno un simbolo (![Screenshot del simbolo di ereditarietà del Visual Basic.](./media/walkthrough-demonstrating-visual-inheritance/visual-basic-inheritance-glyph.gif)) nell'angolo superiore, a indicare che vengono ereditate.

6. Selezionare il pulsante **Say Hello** e osservare i quadratini di ridimensionamento. Poiché questo pulsante è protetto, gli eredi possono spostarlo, ridimensionarlo, modificarne la didascalia e apportare altre modifiche.

7. Selezionare il pulsante privato **Say Goodbye** e notare che non sono presenti handle di ridimensionamento. Inoltre, nella finestra **Proprietà** le proprietà del pulsante sono visualizzate in grigio per indicare che non possono essere modificate.

8. Se si usa Visual C#:

    1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **Form1** nel progetto **InheritanceTest** , quindi scegliere **Elimina**. Nella finestra di messaggio visualizzata fare clic su **OK** per confermare l'eliminazione.

    2. Aprire il file Program.cs e modificare la riga `Application.Run(new Form1());` in `Application.Run(new Form2());`.

9. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **InheritanceTest** e selezionare **Imposta come progetto di avvio**.

10. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **InheritanceTest** e scegliere **proprietà**.

11. Nelle pagine delle proprietà di **InheritanceTest** impostare l' **oggetto di avvio** in modo che sia il formato ereditato (**Form2**).

12. Premere **F5** per eseguire l'applicazione e osservare il comportamento del form ereditato.

## <a name="next-steps"></a>Passaggi successivi

L'ereditarietà per i controlli utente funziona in modo analogo. Aprire un nuovo progetto di libreria di classi e aggiungere un controllo utente. Inserire controlli costitutivi e compilare il progetto. Aprire un altro progetto di libreria di classi e aggiungere un riferimento alla libreria di classi compilata. Provare anche ad aggiungere un controllo ereditato (tramite la finestra di dialogo **Aggiungi nuovi elementi** ) al progetto e a usare la **Selezione ereditarietà**. Aggiungere un controllo utente e modificare l' `Inherits` istruzione (`:` in Visual C#). Per altre informazioni, vedere [Procedura: Eredita Windows Forms](how-to-inherit-windows-forms.md).

## <a name="see-also"></a>Vedere anche

- [Procedura: Eredita Windows Forms](how-to-inherit-windows-forms.md)
- [Ereditarietà visiva di Windows Form](windows-forms-visual-inheritance.md)
- [Windows Form](../index.md)
