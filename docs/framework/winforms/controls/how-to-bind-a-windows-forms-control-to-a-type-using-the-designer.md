---
title: Associare il controllo a un tipo utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 2257489e123ceeea819ad3538952db51b726c7e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742024"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a>Procedura: associare un controllo Windows Form a un tipo mediante la finestra di progettazione

Quando si compilano controlli che interagiscono con i dati, a volte è necessario associare un controllo a un tipo anziché a un oggetto. Di solito è necessario associare un controllo a un tipo in fase di progettazione, quando i dati potrebbero non essere disponibili, ma i controlli associati ai dati devono comunque visualizzare i dati provenienti dall'interfaccia pubblica di un tipo. Nelle procedure riportate di seguito viene illustrato come creare un nuovo <xref:System.Windows.Forms.BindingSource> associato a un tipo, quindi come associare una delle proprietà del tipo alla proprietà <xref:System.Windows.Forms.TextBox.Text%2A> di un <xref:System.Windows.Forms.TextBox>.

### <a name="to-bind-the-bindingsource-to-a-type"></a>Per associare BindingSource a un tipo

1. Creare un progetto di Windows Forms (**file** > **nuovo** **progetto** >  > **Visual C#**  o **Visual Basic** > **desktop classico** > Windows Forms **applicazione**).

2. In visualizzazione **progettazione** trascinare un componente <xref:System.Windows.Forms.BindingSource> sul form.

3. Nella finestra **Proprietà** fare clic sulla freccia per la proprietà <xref:System.Windows.Forms.BindingSource.DataSource%2A>.

4. Nell'**editor di tipo con interfaccia utente DataSource** fare clic su **Aggiungi origine dati progetto**.

5. Nella pagina **Selezionare un tipo di origine dati** selezionare **Oggetto** e fare clic su **Avanti**.

6. Selezionare il tipo da associare:

    - Se il tipo da associare è nel progetto corrente o l'assembly che contiene il tipo è già stato aggiunto come riferimento, espandere i nodi per trovare il tipo desiderato e quindi selezionarlo.

      \-oppure-

    - Se il tipo a cui si desidera eseguire l'associazione si trova in un altro assembly, non attualmente nell'elenco dei riferimenti, fare clic su **Aggiungi riferimento**, quindi fare clic sulla scheda **progetti** . Selezionare il progetto che contiene l'oggetto business desiderato e fare clic su **OK**. Il progetto verrà visualizzato nell'elenco di assembly e sarà possibile espandere i nodi per trovare il tipo desiderato e quindi selezionarlo.

      > [!NOTE]
      > Se si vuole associare un tipo in un framework o assembly Microsoft, deselezionare la casella di controllo **Nascondi assembly che iniziano con Microsoft o System**.

7. Scegliere **Avanti**e quindi fare clic su **Fine**.

### <a name="to-bind-the-control-to-the-bindingsource"></a>Per associare il controllo a BindingSource

1. Aggiungere un tipo <xref:System.Windows.Forms.TextBox> al form.

2. Nella finestra **Proprietà** espandere il nodo **(DataBindings)** .

3. Fare clic sulla freccia accanto alla proprietà <xref:System.Windows.Forms.TextBox.Text%2A>.

4. Nell' **editor di tipo dell'interfaccia utente DataSource**espandere il nodo per il <xref:System.Windows.Forms.BindingSource> aggiunto in precedenza e selezionare la proprietà del tipo associato che si desidera associare alla proprietà <xref:System.Windows.Forms.TextBox.Text%2A> dell'<xref:System.Windows.Forms.TextBox>.

## <a name="see-also"></a>Vedere anche

- [Componente BindingSource](bindingsource-component.md)
- [Procedura: associare un controllo Windows Form a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Associare controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
