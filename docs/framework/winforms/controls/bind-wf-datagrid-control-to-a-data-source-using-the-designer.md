---
title: Associare il controllo DataGrid a un'origine dati tramite la finestra di progettazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: cc0a74eca40e34f06b065980d25d922b919b0c3c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744095"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a>Procedura: associare il controllo DataGrid Windows Form a un'origine dati mediante la finestra di progettazione

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

 Il controllo Windows Forms <xref:System.Windows.Forms.DataGrid> è progettato in modo specifico per visualizzare le informazioni provenienti da un'origine dati. Per associare il controllo in fase di progettazione, è necessario impostare le proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> oppure in fase di esecuzione chiamando il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>. Sebbene sia possibile visualizzare i dati da un'ampia gamma di origini dati, le origini più tipiche sono i set di dati e le visualizzazioni dati.

 Se l'origine dati è disponibile in fase di progettazione, ad esempio se il form contiene un'istanza di un set di dati o una vista dati, è possibile associare la griglia all'origine dati in fase di progettazione. Sarà quindi possibile visualizzare l'anteprima dei dati nella griglia.

 È anche possibile associare la griglia a livello di codice, in fase di esecuzione. Questa operazione è utile quando si vuole impostare un'origine dati in base alle informazioni che si ottengono in fase di esecuzione. Ad esempio, l'applicazione potrebbe consentire all'utente di specificare il nome di una tabella da visualizzare. È anche necessario nelle situazioni in cui l'origine dati non esiste in fase di progettazione. Sono incluse origini dati quali matrici, raccolte, set di dati non tipizzati e lettori di dati.

 Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.DataGrid>. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md). In Visual Studio 2005, per impostazione predefinita, il controllo <xref:System.Windows.Forms.DataGrid> non è presente nella **casella degli strumenti** . Per informazioni sull'aggiunta, vedere [procedura: aggiungere elementi alla casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)). Inoltre, in Visual Studio 2005 è possibile utilizzare la finestra **origini dati** per la data binding in fase di progettazione. Per altre informazioni, vedere [associare i controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).

## <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a>Per associare il controllo DataGrid a una singola tabella nella finestra di progettazione

1. Impostare la proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> del controllo sull'oggetto contenente gli elementi di dati a cui si desidera eseguire l'associazione.

2. Se l'origine dati è un set di dati, impostare la proprietà <xref:System.Windows.Forms.DataGrid.DataMember%2A> sul nome della tabella a cui eseguire l'associazione.

3. Se l'origine dati è un set di dati o una vista dati basata su una tabella del set di dati, aggiungere il codice al form per riempire il set di dati.

     Il codice esatto utilizzato dipende dalla posizione in cui il set di dati recupera i dati. Se il set di dati viene popolato direttamente da un database, in genere si chiama il metodo `Fill` di un adattatore dati, come nell'esempio di codice seguente, che popola un set di dati denominato `DsCategories1`:

    ```vb
    sqlDataAdapter1.Fill(DsCategories1)
    ```

    ```csharp
    sqlDataAdapter1.Fill(DsCategories1);
    ```

    ```cpp
    sqlDataAdapter1->Fill(dsCategories1);
    ```

4. Opzionale Aggiungere gli stili di tabella e gli stili di colonna appropriati alla griglia.

     Se non sono presenti stili di tabella, verrà visualizzata la tabella, ma con la formattazione minima e con tutte le colonne visibili.

## <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a>Per associare il controllo DataGrid a più tabelle in un set di dati nella finestra di progettazione

1. Impostare la proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> del controllo sull'oggetto contenente gli elementi di dati a cui si desidera eseguire l'associazione.

2. Se il set di dati contiene tabelle correlate (ovvero se contiene un oggetto Relation), impostare la proprietà <xref:System.Windows.Forms.DataGrid.DataMember%2A> sul nome della tabella padre.

3. Scrivere il codice per riempire il set di dati.

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sul controllo DataGrid](datagrid-control-overview-windows-forms.md)
- [Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Controllo DataGrid](datagrid-control-windows-forms.md)
- [Data binding in Windows Form](../windows-forms-data-binding.md)
- [Accesso ai dati in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
