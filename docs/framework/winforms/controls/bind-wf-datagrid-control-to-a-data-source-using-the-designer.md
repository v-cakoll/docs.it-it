---
title: 'Procedura: associare il controllo DataGrid Windows Form a un''origine dati mediante la finestra di progettazione'
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
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3913ffe046bb55e31d8be223061af61371a47418
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a>Procedura: associare il controllo DataGrid Windows Form a un'origine dati mediante la finestra di progettazione
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Windows Form <xref:System.Windows.Forms.DataGrid> controllo è progettato specificamente per visualizzare le informazioni da un'origine dati. Per associare il controllo in fase di progettazione impostando il <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> , proprietà o in fase di esecuzione chiamando il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo. Sebbene sia possibile visualizzare i dati da un'ampia gamma di origini dati, le cause più comuni sono i set di dati e le visualizzazioni dati.  
  
 Se l'origine dati è disponibile in fase di progettazione, ad esempio, se il form contiene un'istanza di un set di dati o una vista dati, è possibile associare la griglia per l'origine dati in fase di progettazione. È quindi possibile visualizzare in anteprima l'aspetto dei dati nella griglia.  
  
 È anche possibile associare la griglia a livello di codice in fase di esecuzione. Ciò è utile quando si desidera impostare un'origine dati in base alle informazioni ottenute in fase di esecuzione. Ad esempio, l'applicazione potrebbe consentire all'utente di specificare il nome di una tabella da visualizzare. È inoltre necessaria nelle situazioni in cui l'origine dati non esiste in fase di progettazione. Sono incluse origini dati, ad esempio matrici, raccolte, dataset non tipizzati e lettori di dati.  
  
 La procedura seguente richiede un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGrid> controllo. Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> controllo non sarà il **della casella degli strumenti** per impostazione predefinita. Per informazioni su come aggiungerlo, vedere [procedura: aggiungere elementi alla casella degli strumenti](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0). Inoltre in [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], è possibile utilizzare il **origini dati** finestra per l'associazione dati in fase di progettazione. Per ulteriori informazioni vedere [associare i controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a>Per associare il controllo DataGrid a una singola tabella nella finestra di progettazione  
  
1.  Impostare il controllo <xref:System.Windows.Forms.DataGrid.DataSource%2A> proprietà all'oggetto contenente gli elementi di dati a cui si desidera associare.  
  
2.  Se l'origine dati è un set di dati, impostare il <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà sul nome della tabella da associare.  
  
3.  Se l'origine dati è un set di dati o una vista di dati basato su una tabella di set di dati, aggiungere codice al form per riempire il set di dati.  
  
     Il codice esatto che è utilizzare dipende in cui il set di dati Ottiene i dati. Se il set di dati viene popolato direttamente da un database, si chiama in genere il `Fill` metodo di un adattatore di dati, come nell'esempio di codice seguente, che popola un set di dati denominato `DsCategories1`:  
  
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
  
     Se sono presenti nessuno stile di tabella, verrà visualizzato nella tabella, ma con una formattazione minima e con tutte le colonne visibili.  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a>Per associare il controllo DataGrid a più tabelle in un set di dati nella finestra di progettazione  
  
1.  Impostare il controllo <xref:System.Windows.Forms.DataGrid.DataSource%2A> proprietà all'oggetto contenente gli elementi di dati a cui si desidera associare.  
  
2.  Se il set di dati contiene tabelle correlate (ovvero, se contiene un oggetto relation), impostare il <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà sul nome della tabella padre.  
  
3.  Scrivere codice per riempire il set di dati.  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sul controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Data binding in Windows Form](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Accesso ai dati in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
