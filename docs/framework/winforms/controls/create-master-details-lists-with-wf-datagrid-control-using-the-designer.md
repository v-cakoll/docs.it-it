---
title: 'Procedura: creare elenchi Master-Details mediante il controllo DataGrid Windows Form nella finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: aec02e38fbe80302108397543144b1cc9c3ea346
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48266785"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Procedura: creare elenchi Master-Details mediante il controllo DataGrid Windows Form nella finestra di progettazione

> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Se il <xref:System.Data.DataSet> contiene una serie di tabelle correlate, è possibile utilizzare due <xref:System.Windows.Forms.DataGrid> controlli per visualizzare i dati in un formato master / dettaglio. Uno <xref:System.Windows.Forms.DataGrid> designato come la griglia principale, e il secondo può essere tuttavia designato nella griglia dei dettagli. Quando si seleziona una voce nell'elenco master, tutte le voci figlio correlati vengono visualizzate nell'elenco di dettagli. Ad esempio, se il <xref:System.Data.DataSet> contiene una tabella Customers e una tabella di ordini correlata, si specificherà la tabella Customers a griglia principale e la tabella Orders alla griglia dei dettagli. Quando un cliente viene selezionato nella griglia principale, tutti gli ordini associati a tale cliente nella tabella Orders verrebbero visualizzati nella griglia dettagli.  
  
 La procedura seguente richiede un **applicazione di Windows** progetto (**File** > **nuovo** > **progetto**  >  **Visual c#** oppure **Visual Basic** > **Desktop classico** > **Windows Form Applicazione**).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a>Per creare un elenco master-dettagli nella finestra di progettazione  
  
1.  Aggiungere due <xref:System.Windows.Forms.DataGrid> controlli al form. Per altre informazioni, vedere [procedura: aggiungere i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). In Visual Studio 2005, il <xref:System.Windows.Forms.DataGrid> controllo non è nel **casella degli strumenti** per impostazione predefinita. Per altre informazioni, vedere [procedura: aggiungere elementi alla casella degli strumenti](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
    > [!NOTE]
    >  I passaggi seguenti non sono applicabili a Visual Studio 2005, che usa il **Zdroje dat** finestra per l'associazione dati design-time. Per altre informazioni, vedere [associare controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) e [procedura: visualizzare dati correlati in una Windows Forms Application](https://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).  
  
2.  Trascinare due o più tabelle da **Esplora Server** al form.  
  
3.  Dal **Data** dal menu **Genera DataSet**.  
  
4.  Impostare le relazioni tra le tabelle utilizzando la finestra di progettazione XML. Per informazioni dettagliate, vedere "procedura: creare uno-a-molti relazioni nei DataSet e XML Schema" in MSDN.  
  
5.  Salvare le relazioni selezionando **Salva tutto** dalle **File** menu.  
  
6.  Configurare il <xref:System.Windows.Forms.DataGrid> controllo che si desidera designare come griglia principale, come indicato di seguito:  
  
    1.  Selezionare il <xref:System.Data.DataSet> dall'elenco nell'elenco a discesa di <xref:System.Windows.Forms.DataGrid.DataSource%2A> proprietà.  
  
    2.  Selezionare la tabella principale (ad esempio, "Customers") dall'elenco nell'elenco a discesa di <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà.  
  
7.  Configurare il <xref:System.Windows.Forms.DataGrid> controllo che si vuole designare nella griglia dei dettagli, come indicato di seguito:  
  
    1.  Selezionare il <xref:System.Data.DataSet> dall'elenco nell'elenco a discesa di <xref:System.Windows.Forms.DataGrid.DataSource%2A> proprietà.  
  
    2.  Selezionare la relazione (ad esempio, "CustOrd") tra le tabelle master e i dettagli nell'elenco a discesa nel <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà. Per visualizzare la relazione, espandere il nodo, fare clic sul segno più (**+**) segno più accanto alla tabella master nell'elenco a discesa.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Cenni preliminari sul controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Procedura: Associare il controllo DataGrid Windows Form a un'origine dati](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [Associare controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
