---
title: 'Procedura: Associare un controllo di Windows Forms a un tipo usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 5069d7d3b5ef4c5b05159dac521d32f5be8abdd1
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046036"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a>Procedura: Associare un controllo di Windows Forms a un tipo usando la finestra di progettazione

Quando si compilano controlli che interagiscono con i dati, a volte è necessario associare un controllo a un tipo anziché a un oggetto. Di solito è necessario associare un controllo a un tipo in fase di progettazione, quando i dati potrebbero non essere disponibili, ma i controlli associati ai dati devono comunque visualizzare i dati provenienti dall'interfaccia pubblica di un tipo. Nelle procedure riportate di seguito viene illustrato <xref:System.Windows.Forms.BindingSource> come creare un nuovo oggetto associato a un tipo, quindi come associare una delle proprietà del tipo <xref:System.Windows.Forms.TextBox.Text%2A> alla proprietà di un oggetto <xref:System.Windows.Forms.TextBox>.

### <a name="to-bind-the-bindingsource-to-a-type"></a>Per associare BindingSource a un tipo

1. Creazione di un progetto di Windows Forms (**file** > **nuovo** > oggetto**visivo C#**  **progetto** > o **Visual Basic** > **desktop classico**  >   **Applicazione Windows Forms**).

2. In visualizzazione **progettazione** trascinare un <xref:System.Windows.Forms.BindingSource> componente nel form.

3. Nella finestra **Proprietà** fare clic sulla freccia per la <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà.

4. Nell'**editor di tipo con interfaccia utente DataSource** fare clic su **Aggiungi origine dati progetto**.

5. Nella pagina **Selezionare un tipo di origine dati** selezionare **Oggetto** e fare clic su **Avanti**.

6. Selezionare il tipo da associare:

    - Se il tipo da associare è nel progetto corrente o l'assembly che contiene il tipo è già stato aggiunto come riferimento, espandere i nodi per trovare il tipo desiderato e quindi selezionarlo.

      \-oppure-

    - Se il tipo da associare è in un altro assembly, attualmente non presente nell'elenco di riferimenti, fare clic su **Aggiungi riferimento**, quindi fare clic sulla scheda **Progetti**. Selezionare il progetto che contiene l'oggetto business desiderato e fare clic su **OK**. Il progetto verrà visualizzato nell'elenco di assembly e sarà possibile espandere i nodi per trovare il tipo desiderato e quindi selezionarlo.

      > [!NOTE]
      > Se si vuole associare un tipo in un framework o assembly Microsoft, deselezionare la casella di controllo **Nascondi assembly che iniziano con Microsoft o System**.

7. Scegliere **Avanti**e quindi fare clic su **Fine**.

### <a name="to-bind-the-control-to-the-bindingsource"></a>Per associare il controllo a BindingSource

1. Aggiungere un tipo <xref:System.Windows.Forms.TextBox> al form.

2. Nella finestra **Proprietà** espandere il nodo **(DataBindings)** .

3. Fare clic sulla freccia accanto alla <xref:System.Windows.Forms.TextBox.Text%2A> proprietà.

4. Nell' **editor di tipo dell'interfaccia utente DataSource**espandere il nodo per <xref:System.Windows.Forms.BindingSource> l'oggetto aggiunto in precedenza e selezionare la proprietà del tipo associato che si desidera associare alla <xref:System.Windows.Forms.TextBox.Text%2A> proprietà di <xref:System.Windows.Forms.TextBox>.

## <a name="see-also"></a>Vedere anche

- [Componente BindingSource](bindingsource-component.md)
- [Procedura: Associare un controllo Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Associare controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
