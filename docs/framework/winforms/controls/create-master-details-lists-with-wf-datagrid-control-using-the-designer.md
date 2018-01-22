---
title: 'Procedura: creare elenchi Master-Details mediante il controllo DataGrid Windows Form nella finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1526a6e54078ea3dc0500c39a8fc2feda44d901
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Procedura: creare elenchi Master-Details mediante il controllo DataGrid Windows Form nella finestra di progettazione
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Se il <xref:System.Data.DataSet> contiene una serie di tabelle correlate, è possibile utilizzare due <xref:System.Windows.Forms.DataGrid> controlli per visualizzare i dati in un formato master-details. Uno <xref:System.Windows.Forms.DataGrid> designato come griglia principale, e il secondo è designato come griglia dei dettagli. Quando si seleziona una voce nell'elenco master, tutte le voci figlio correlati vengono visualizzate nell'elenco dei dettagli. Ad esempio, se il <xref:System.Data.DataSet> contiene una tabella Customers e una tabella correlata Orders, specificare la tabella Customers come griglia principale e la tabella Orders come griglia dei dettagli. Quando un cliente è selezionato nella griglia principale, tutti gli ordini associati al cliente nella tabella Orders verrebbero visualizzati nella griglia dettagli.  
  
 La procedura seguente richiede un **applicazione Windows** progetto. Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a>Per creare un elenco master-dettagli nella finestra di progettazione  
  
1.  Aggiungere due <xref:System.Windows.Forms.DataGrid> controlli al form. Per ulteriori informazioni, vedere [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> controllo non sarà il **della casella degli strumenti** per impostazione predefinita. Per ulteriori informazioni, vedere [procedura: aggiungere elementi alla casella degli strumenti](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
    > [!NOTE]
    >  I passaggi seguenti non sono applicabili alle [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], che utilizza il **origini dati** finestra per l'associazione dati in fase di progettazione. Per ulteriori informazioni, vedere [associare i controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) e [procedura: visualizzare i dati correlati in un'applicazione Windows Forms](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).  
  
2.  Trascinare due o più tabelle da **Esplora Server** al form.  
  
3.  Dal **dati** dal menu **Genera DataSet**.  
  
4.  Impostare le relazioni tra le tabelle utilizzando la finestra di progettazione XML. Per informazioni dettagliate, vedere "procedura: creare uno-a-molti relazioni nei DataSet e gli schemi XML" in MSDN.  
  
5.  Salvare le relazioni selezionando **Salva tutto** dal **File** menu.  
  
6.  Configurare il <xref:System.Windows.Forms.DataGrid> controllo che si desidera designare come griglia principale, come indicato di seguito:  
  
    1.  Selezionare il <xref:System.Data.DataSet> dall'elenco a discesa nella <xref:System.Windows.Forms.DataGrid.DataSource%2A> proprietà.  
  
    2.  Selezionare la tabella principale (ad esempio, "Customers") nell'elenco a discesa nel <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà.  
  
7.  Configurare il <xref:System.Windows.Forms.DataGrid> controllo che si desidera designare come griglia dei dettagli, come indicato di seguito:  
  
    1.  Selezionare il <xref:System.Data.DataSet> dall'elenco a discesa nella <xref:System.Windows.Forms.DataGrid.DataSource%2A> proprietà.  
  
    2.  Selezionare la relazione (ad esempio, "CustOrd") tra le tabelle master e di dettaglio dall'elenco a discesa nella <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà. Per visualizzare la relazione, espandere il nodo facendo clic sul segno più (**+**) accanto alla tabella master nell'elenco a discesa.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Cenni preliminari sul controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Procedura: Associare il controllo DataGrid Windows Form a un'origine dati](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [Associare controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
