---
title: 'Procedura: Creare elenchi Master-Details con il controllo DataGrid di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: 46825eeb2befab7f11a87451da53a773a6ce2ad2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648220"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Procedura: Creare elenchi Master-Details con il controllo DataGrid di Windows Forms usando la finestra di progettazione

> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Se il <xref:System.Data.DataSet> contiene una serie di tabelle correlate, è possibile utilizzare due <xref:System.Windows.Forms.DataGrid> controlli per visualizzare i dati in un formato master / dettaglio. Uno <xref:System.Windows.Forms.DataGrid> designato come la griglia principale, e il secondo può essere tuttavia designato nella griglia dei dettagli. Quando si seleziona una voce nell'elenco master, tutte le voci figlio correlati vengono visualizzate nell'elenco di dettagli. Ad esempio, se il <xref:System.Data.DataSet> contiene una tabella Customers e una tabella di ordini correlata, si specificherà la tabella Customers a griglia principale e la tabella Orders alla griglia dei dettagli. Quando un cliente viene selezionato nella griglia principale, tutti gli ordini associati a tale cliente nella tabella Orders verrebbero visualizzati nella griglia dettagli.  
  
 La procedura seguente richiede un **applicazione di Windows** progetto (**File** > **nuovo** > **progetto**  >  **Visual c#** oppure **Visual Basic** > **Desktop classico** > **Windows Form Applicazione**).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a>Per creare un elenco master-dettagli nella finestra di progettazione  
  
1. Aggiungere due <xref:System.Windows.Forms.DataGrid> controlli al form. Per altre informazioni, vedere [Procedura: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md). In Visual Studio 2005, il <xref:System.Windows.Forms.DataGrid> controllo non è nel **casella degli strumenti** per impostazione predefinita. Per altre informazioni, vedere [Procedura: Aggiungere elementi alla casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).  
  
    > [!NOTE]
    >  I passaggi seguenti non sono applicabili a Visual Studio 2005, che usa il **Zdroje dat** finestra per l'associazione dati design-time. Per altre informazioni, vedere [associare controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) e [come: Visualizzare correlati i dati in una Windows Forms Application](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).  
  
2. Trascinare due o più tabelle da **Esplora Server** al form.  
  
3. Dal **Data** dal menu **Genera DataSet**.  
  
4. Impostare le relazioni tra le tabelle utilizzando la finestra di progettazione XML. Per informazioni dettagliate, vedere "procedura: Creare relazioni uno-a-molti in XML schema e i set di dati"in MSDN.  
  
5. Salvare le relazioni selezionando **Salva tutto** dalle **File** menu.  
  
6. Configurare il <xref:System.Windows.Forms.DataGrid> controllo che si desidera designare come griglia principale, come indicato di seguito:  
  
    1. Selezionare il <xref:System.Data.DataSet> dall'elenco nell'elenco a discesa di <xref:System.Windows.Forms.DataGrid.DataSource%2A> proprietà.  
  
    2. Selezionare la tabella principale (ad esempio, "Customers") dall'elenco nell'elenco a discesa di <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà.  
  
7. Configurare il <xref:System.Windows.Forms.DataGrid> controllo che si vuole designare nella griglia dei dettagli, come indicato di seguito:  
  
    1. Selezionare il <xref:System.Data.DataSet> dall'elenco nell'elenco a discesa di <xref:System.Windows.Forms.DataGrid.DataSource%2A> proprietà.  
  
    2. Selezionare la relazione (ad esempio, "CustOrd") tra le tabelle master e i dettagli nell'elenco a discesa nel <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà. Per visualizzare la relazione, espandere il nodo, fare clic sul segno più (**+**) segno più accanto alla tabella master nell'elenco a discesa.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo DataGrid](datagrid-control-windows-forms.md)
- [Cenni preliminari sul controllo DataGrid](datagrid-control-overview-windows-forms.md)
- [Procedura: Associare il controllo DataGrid di Windows Form a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [Associare controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
