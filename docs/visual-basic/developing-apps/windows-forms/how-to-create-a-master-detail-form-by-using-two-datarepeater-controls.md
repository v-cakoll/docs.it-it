---
title: 'Procedura: creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio) | Documenti di Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 4ed0b1fa0e7fac96cef3bde61efac66681f2507b
ms.contentlocale: it-it
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a><span data-ttu-id="87b95-102">Procedura: creare un form Master-Details mediante due controlli DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="87b95-102">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>
<span data-ttu-id="87b95-103">È possibile visualizzare dati correlati utilizzando due o più <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controlli per creare un form master-details.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="87b95-103">You can display related data by using two or more <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls to create a master/detail form.</span></span> <span data-ttu-id="87b95-104">Potrebbe ad esempio, si desidera visualizzare un elenco di clienti in uno <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>e quando l'utente seleziona un cliente, visualizzare un elenco di ordini del cliente in un secondo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="87b95-104">For example, you might want to display a list of customers in one <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and when the user selects a customer, display a list of that customer's orders in a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
 <span data-ttu-id="87b95-105">È possibile visualizzare dati correlati mediante il trascinamento degli elementi di dettaglio che condividono lo stesso nodo tabella master dal **origini dati** finestra un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="87b95-105">You can display related data by dragging detail items that share the same master table node from the **Data Sources** window onto a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="87b95-106">Ad esempio, se si dispone di un'origine dati che dispone di una tabella Customers e una tabella correlata Orders, noterete entrambe le tabelle come nodi di primo livello nella visualizzazione struttura ad albero di **origini dati** finestra.</span><span class="sxs-lookup"><span data-stu-id="87b95-106">For example, if you have a data source that has a Customers table and a related Orders table, you see both tables as top-level nodes in the tree view in the **Data Sources** window.</span></span> <span data-ttu-id="87b95-107">Espandere il nodo di clienti in modo che è possibile visualizzare le colonne.</span><span class="sxs-lookup"><span data-stu-id="87b95-107">Expand the Customers node so that you can see the columns.</span></span> <span data-ttu-id="87b95-108">Si noti che l'ultima colonna nell'elenco è un nodo che rappresenta la tabella Orders.</span><span class="sxs-lookup"><span data-stu-id="87b95-108">Notice that the last column in the list is an expandable node that represents the Orders table.</span></span> <span data-ttu-id="87b95-109">Questo nodo rappresenta gli ordini correlati per un cliente.</span><span class="sxs-lookup"><span data-stu-id="87b95-109">This node represents the related orders for a customer.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a><span data-ttu-id="87b95-110">Per visualizzare dati correlati in due controlli DataRepeater</span><span class="sxs-lookup"><span data-stu-id="87b95-110">To display related data in two DataRepeater controls</span></span>  
  
1.  <span data-ttu-id="87b95-111">Trascinare due <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>dei controlli di **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** a un form o un controllo contenitore.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="87b95-111">Drag two <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controls from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="87b95-112">Trascinare i quadratini di ridimensionamento e la posizione per le dimensioni dei controlli e posizionarli side-by-side.</span><span class="sxs-lookup"><span data-stu-id="87b95-112">Drag the sizing and position handles to size the controls and position them side-by-side.</span></span>  
  
3.  <span data-ttu-id="87b95-113">Scegliere **Mostra origini dati** dal menu **Dati**.</span><span class="sxs-lookup"><span data-stu-id="87b95-113">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="87b95-114">Se il **origini dati** finestra è vuota, aggiungere un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="87b95-114">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="87b95-115">Per ulteriori informazioni, vedere [aggiungere nuove origini dati](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="87b95-115">For more information, see [Add new data sources](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="87b95-116">Nel **origini dati** finestra, selezionare il nodo di primo livello per la tabella master.</span><span class="sxs-lookup"><span data-stu-id="87b95-116">In the **Data Sources** window, select the top-level node for the master table.</span></span>  
  
5.  <span data-ttu-id="87b95-117">Modificare il tipo di visualizzazione della tabella master per i dettagli, fare clic su **dettagli** nell'elenco a discesa del nodo della tabella.</span><span class="sxs-lookup"><span data-stu-id="87b95-117">Change the drop type of the master table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="87b95-118">Trascinare il nodo della tabella master sull'area del modello di elemento del primo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="87b95-118">Drag the master table node onto the item template region of the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
7.  <span data-ttu-id="87b95-119">Espandere il nodo della tabella master e selezionare il nodo dettaglio per la tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="87b95-119">Expand the master table node and select the detail node for the related table.</span></span>  
  
8.  <span data-ttu-id="87b95-120">Modificare il tipo di visualizzazione della tabella dettagli per i dettagli, fare clic su **dettagli** nell'elenco a discesa del nodo della tabella.</span><span class="sxs-lookup"><span data-stu-id="87b95-120">Change the drop type of the detail table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
9. <span data-ttu-id="87b95-121">Selezionare il nodo della tabella e trascinarlo nell'area del modello di elemento della seconda <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="87b95-121">Select this table node and drag it onto the item template region of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b95-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87b95-122">See Also</span></span>  
 <span data-ttu-id="87b95-123"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="87b95-123"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span></span>   
<span data-ttu-id="87b95-124"> [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="87b95-124"> [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="87b95-125"> [Procedura: visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="87b95-125"> [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="87b95-126"> [Procedura: visualizzare correlati i dati in un Windows Form dell'applicazione](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd) </span><span class="sxs-lookup"><span data-stu-id="87b95-126"> [How to: Display Related Data in a Windows Forms Application](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd) </span></span>  
<span data-ttu-id="87b95-127"> [Procedura: modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="87b95-127"> [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="87b95-128"> [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="87b95-128"> [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span></span>
