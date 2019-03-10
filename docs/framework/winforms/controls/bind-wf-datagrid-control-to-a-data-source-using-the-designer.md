---
title: "Procedura: Associare il controllo DataGrid di Windows Form a un'origine dati tramite la finestra di progettazione"
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
ms.openlocfilehash: 9386ca229894cff61da32289f2d78a7016ea00e0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720465"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a>Procedura: Associare il controllo DataGrid di Windows Form a un'origine dati tramite la finestra di progettazione

> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 I moduli di Windows <xref:System.Windows.Forms.DataGrid> controllo è appositamente progettato per visualizzare le informazioni da un'origine dati. Si associa il controllo in fase di progettazione, impostando il <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> le proprietà, o in fase di esecuzione chiamando il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> (metodo). Sebbene sia possibile visualizzare i dati da un'ampia gamma di origini dati, le cause più comuni sono i set di dati e le visualizzazioni dati.  
  
 Se l'origine dati è disponibile in fase di progettazione, ad esempio, se il form contiene un'istanza di un set di dati o una vista dati, è possibile associare la griglia per l'origine dati in fase di progettazione. È quindi possibile visualizzare in anteprima i dati di aspetto della griglia.  
  
 È anche possibile associare la griglia a livello di codice in fase di esecuzione. Ciò è utile quando si desidera impostare un'origine dati basata su informazioni ottenute in fase di esecuzione. Ad esempio, l'applicazione potrebbe consentire all'utente specificare il nome di una tabella da visualizzare. È inoltre necessario in situazioni in cui l'origine dati non esiste in fase di progettazione. Ciò include le origini dati, ad esempio matrici, raccolte, i set di dati non tipizzato e lettori di dati.  
  
 La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGrid> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md). In Visual Studio 2005, il <xref:System.Windows.Forms.DataGrid> controllo non è nel **casella degli strumenti** per impostazione predefinita. Per informazioni su come aggiungerlo, vedere [come: Aggiungere elementi alla casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)). In Visual Studio 2005, è inoltre possibile usare la **Zdroje dat** finestra per l'associazione dati design-time. Per altre informazioni, vedere [associare controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a>Per associare il controllo DataGrid a una singola tabella nella finestra di progettazione  
  
1.  Impostare il controllo <xref:System.Windows.Forms.DataGrid.DataSource%2A> all'oggetto che contiene gli elementi di dati da associare alla proprietà.  
  
2.  Se l'origine dati è un set di dati, impostare il <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà sul nome della tabella a cui associarsi.  
  
3.  Se l'origine dati è un set di dati o una vista di dati basato su una tabella di set di dati, aggiungere codice al form per riempire il set di dati.  
  
     Il codice esatto che è usare dipende in cui il set di dati stia ottenendo i dati. In genere se il set di dati viene popolato direttamente da un database, si chiama il `Fill` metodo di un adattatore di dati, come nell'esempio di codice seguente, che consente di popolare un set di dati denominato `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  (Facoltativo) Aggiungere gli stili tabella appropriata e gli stili di colonna nella griglia.  
  
     Se non sono presenti stili di tabella, verrà visualizzato nella tabella, ma con una formattazione minima e con tutte le colonne visibili.  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a>Per associare il controllo DataGrid a più tabelle in un set di dati nella finestra di progettazione  
  
1.  Impostare il controllo <xref:System.Windows.Forms.DataGrid.DataSource%2A> all'oggetto che contiene gli elementi di dati da associare alla proprietà.  
  
2.  Se il set di dati contiene tabelle correlate (vale a dire, se contiene un oggetto relazione), impostare il <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà sul nome della tabella padre.  
  
3.  Scrivere codice per riempire il set di dati.  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sul controllo DataGrid](datagrid-control-overview-windows-forms.md)
- [Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Controllo DataGrid](datagrid-control-windows-forms.md)
- [Data binding in Windows Form](../windows-forms-data-binding.md)
- [Accesso ai dati in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
