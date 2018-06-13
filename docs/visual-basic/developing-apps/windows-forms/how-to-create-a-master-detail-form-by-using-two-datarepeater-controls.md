---
title: 'Procedura: creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590907"
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a><span data-ttu-id="c8ed6-102">Procedura: creare un form Master-Details mediante due controlli DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="c8ed6-102">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>
<span data-ttu-id="c8ed6-103">È possibile visualizzare dati correlati utilizzando due o più <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controlli per creare un form master-details.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-103">You can display related data by using two or more <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls to create a master/detail form.</span></span> <span data-ttu-id="c8ed6-104">Potrebbe ad esempio, si desidera visualizzare un elenco di clienti in uno <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>e quando l'utente seleziona un cliente, è possibile visualizzare un elenco di ordini del cliente in un secondo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-104">For example, you might want to display a list of customers in one <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and when the user selects a customer, display a list of that customer's orders in a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
 <span data-ttu-id="c8ed6-105">È possibile visualizzare dati correlati trascinando gli elementi di dettaglio che condividono lo stesso nodo di tabella master dal **origini dati** finestra un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-105">You can display related data by dragging detail items that share the same master table node from the **Data Sources** window onto a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="c8ed6-106">Ad esempio, se si dispone di un'origine dati che dispone di una tabella Customers e una tabella correlata Orders, vedrai entrambe le tabelle come nodi di primo livello nella visualizzazione struttura ad albero di **origini dati** finestra.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-106">For example, if you have a data source that has a Customers table and a related Orders table, you see both tables as top-level nodes in the tree view in the **Data Sources** window.</span></span> <span data-ttu-id="c8ed6-107">Espandere il nodo di clienti in modo che è possibile visualizzare le colonne.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-107">Expand the Customers node so that you can see the columns.</span></span> <span data-ttu-id="c8ed6-108">Si noti che l'ultima colonna nell'elenco è un nodo che rappresenta la tabella Orders.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-108">Notice that the last column in the list is an expandable node that represents the Orders table.</span></span> <span data-ttu-id="c8ed6-109">Questo nodo rappresenta gli ordini relativi a un cliente.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-109">This node represents the related orders for a customer.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a><span data-ttu-id="c8ed6-110">Per visualizzare dati correlati in due controlli DataRepeater</span><span class="sxs-lookup"><span data-stu-id="c8ed6-110">To display related data in two DataRepeater controls</span></span>  
  
1.  <span data-ttu-id="c8ed6-111">Trascinare due <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> dei controlli di **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** a un controllo form o del contenitore.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-111">Drag two <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="c8ed6-112">Trascinare i quadratini di ridimensionamento e la posizione per ridimensionare i controlli e posizionarli side-by-side.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-112">Drag the sizing and position handles to size the controls and position them side-by-side.</span></span>  
  
3.  <span data-ttu-id="c8ed6-113">Scegliere **Mostra origini dati** dal menu **Dati**.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-113">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c8ed6-114">Se il **origini dati** finestra è vuota, aggiungere un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-114">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="c8ed6-115">Per altre informazioni, vedere [Add new data sources](/visualstudio/data-tools/add-new-data-sources) (Aggiungere nuove origini dati).</span><span class="sxs-lookup"><span data-stu-id="c8ed6-115">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="c8ed6-116">Nel **origini dati** finestra, selezionare il nodo di livello superiore per la tabella master.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-116">In the **Data Sources** window, select the top-level node for the master table.</span></span>  
  
5.  <span data-ttu-id="c8ed6-117">Modificare il tipo di rilascio della tabella master per i dettagli, fare clic su **dettagli** nell'elenco a discesa nel nodo della tabella.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-117">Change the drop type of the master table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="c8ed6-118">Trascinare il nodo di tabella master area modello dell'elemento del primo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-118">Drag the master table node onto the item template region of the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
7.  <span data-ttu-id="c8ed6-119">Espandere il nodo della tabella master e selezionare il nodo dettaglio della tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-119">Expand the master table node and select the detail node for the related table.</span></span>  
  
8.  <span data-ttu-id="c8ed6-120">Modificare il tipo di rilascio della tabella dettagli per informazioni dettagliate, fare clic su **dettagli** nell'elenco a discesa nel nodo della tabella.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-120">Change the drop type of the detail table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
9. <span data-ttu-id="c8ed6-121">Selezionare il nodo della tabella e trascinarlo sull'area del modello di elemento della seconda <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.</span><span class="sxs-lookup"><span data-stu-id="c8ed6-121">Select this table node and drag it onto the item template region of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8ed6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8ed6-122">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="c8ed6-123">Introduzione al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="c8ed6-123">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="c8ed6-124">Procedura: Visualizzare i dati associati in un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="c8ed6-124">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="c8ed6-125">Procedura: Visualizzare dati correlati in un'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8ed6-125">How to: Display Related Data in a Windows Forms Application</span></span>](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [<span data-ttu-id="c8ed6-126">Procedura: Modificare l'aspetto di un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="c8ed6-126">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="c8ed6-127">Risoluzione dei problemi relativi al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="c8ed6-127">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
