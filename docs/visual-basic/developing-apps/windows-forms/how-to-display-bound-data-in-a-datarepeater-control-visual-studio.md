---
title: 'Procedura: visualizzare i dati associati in un controllo DataRepeater (Visual Studio) | Documenti di Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: 11
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
ms.openlocfilehash: 677c964ee9ebbad6ec712a29c8b9c8920aa7e7ec
ms.contentlocale: it-it
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="859fa-102">Procedura: visualizzare i dati associati in un controllo DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="859fa-102">How to: Display Bound Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="859fa-103">L'utilizzo più comune del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo consiste nel visualizzare i dati associati da un database o altra origine dati.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="859fa-103">The most common use of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control is to display bound data from a database or other data source.</span></span>  
  
 <span data-ttu-id="859fa-104">Oltre ai controlli associati, si desidera aggiungere altri controlli, ad esempio un'etichetta statica o un'immagine che viene ripetuta in ogni elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="859fa-104">In addition to bound controls, you may want to add other controls, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="859fa-105">Per ulteriori informazioni, vedere [procedura: visualizzare i controlli non associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="859fa-105">For more information, see [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
 <span data-ttu-id="859fa-106">È inoltre possibile associare a un'origine dati in fase di esecuzione impostando la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>proprietà `True` e l'assegnazione di un'origine dati per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A>proprietà.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A></span><span class="sxs-lookup"><span data-stu-id="859fa-106">You can also bind to a data source at run time by setting the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> property to `True` and assigning a data source to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> property.</span></span> <span data-ttu-id="859fa-107">In questo caso, è necessario gestire l'interazione con l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="859fa-107">In this case, you will need to manage all interaction with the data source.</span></span> <span data-ttu-id="859fa-108">Per ulteriori informazioni, vedere [modalità virtuale nel controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="859fa-108">For more information, see [Virtual Mode in the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a><span data-ttu-id="859fa-109">Per creare un oggetto DataRepeater con associazione a dati</span><span class="sxs-lookup"><span data-stu-id="859fa-109">To create a data-bound DataRepeater</span></span>  
  
1.  <span data-ttu-id="859fa-110">Trascinare un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>da controllare il **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** a un form o un controllo contenitore.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="859fa-110">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="859fa-111">Trascinare i quadratini di ridimensionamento e la posizione di dimensioni e posizione del controllo.</span><span class="sxs-lookup"><span data-stu-id="859fa-111">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="859fa-112">Si noti che il controllo dispone di due aree rettangolari.</span><span class="sxs-lookup"><span data-stu-id="859fa-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="859fa-113">L'area superiore è il *modello di elemento*; i controlli aggiunti al modello verranno ripetuti in ogni voce di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo in fase di esecuzione.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="859fa-113">The upper region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="859fa-114">L'area inferiore è il *viewport*, in cui verranno visualizzati gli elementi.</span><span class="sxs-lookup"><span data-stu-id="859fa-114">The lower region is the *viewport*, where the items will be displayed.</span></span>  
  
     <span data-ttu-id="859fa-115">È anche possibile ridimensionare e posizionare il controllo o il modello di elemento modificando il **dimensioni** e **posizione** proprietà nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="859fa-115">You can also size and position the control or the item template by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="859fa-116">Scegliere **Mostra origini dati** dal menu **Dati**.</span><span class="sxs-lookup"><span data-stu-id="859fa-116">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="859fa-117">Se il **origini dati** finestra è vuota, aggiungere un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="859fa-117">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="859fa-118">Per ulteriori informazioni, vedere [aggiungere nuove origini dati](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="859fa-118">For more information, see [Add new data sources](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="859fa-119">Nel **origini dati** finestra, selezionare il nodo di primo livello per la tabella che contiene i dati che si desidera associare.</span><span class="sxs-lookup"><span data-stu-id="859fa-119">In the **Data Sources** window, select the top-level node for the table that contains the data that you want to bind.</span></span>  
  
5.  <span data-ttu-id="859fa-120">Modificare il tipo di visualizzazione della tabella da `Details` facendo `Details` nell'elenco a discesa del nodo della tabella.</span><span class="sxs-lookup"><span data-stu-id="859fa-120">Change the drop type of the table to `Details` by clicking `Details` in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="859fa-121">Selezionare il nodo della tabella e trascinarlo nell'area del modello di elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="859fa-121">Select the table node and drag it onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="859fa-122">È possibile specificare tipi di controlli che vengono visualizzati per ogni campo.</span><span class="sxs-lookup"><span data-stu-id="859fa-122">You can specify which types of controls are displayed for each field.</span></span> <span data-ttu-id="859fa-123">Per ulteriori informazioni, vedere [impostare il controllo da creare durante il trascinamento dalla finestra Origini dati](https://docs.microsoft.com/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span><span class="sxs-lookup"><span data-stu-id="859fa-123">For more information, see [Set the control to be created when dragging from the Data Sources window](https://docs.microsoft.com/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="859fa-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="859fa-124">See Also</span></span>  
 <span data-ttu-id="859fa-125"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="859fa-125"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span></span>   
<span data-ttu-id="859fa-126"> [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="859fa-126"> [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="859fa-127"> [Procedura: visualizzazione controlli non associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="859fa-127"> [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="859fa-128"> [Procedura: creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span><span class="sxs-lookup"><span data-stu-id="859fa-128"> [How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span></span>  
<span data-ttu-id="859fa-129"> [Procedura: modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="859fa-129"> [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="859fa-130"> [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="859fa-130"> [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span></span>
