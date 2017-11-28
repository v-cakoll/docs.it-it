---
title: 'Procedura: visualizzare i dati associati in un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 770003c8879661bfc1ce683f5b6ed84483cf47ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="15813-102">Procedura: visualizzare i dati associati in un controllo DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="15813-102">How to: Display Bound Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="15813-103">L'utilizzo più comune del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo consiste nel visualizzare i dati associati da un database o un'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="15813-103">The most common use of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control is to display bound data from a database or other data source.</span></span>  
  
 <span data-ttu-id="15813-104">Oltre a controlli con associazione, si desidera aggiungere altri controlli, ad esempio un'etichetta statica o di un'immagine che viene ripetuta in ogni elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.</span><span class="sxs-lookup"><span data-stu-id="15813-104">In addition to bound controls, you may want to add other controls, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="15813-105">Per ulteriori informazioni, vedere [procedura: visualizzare i controlli non associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="15813-105">For more information, see [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
 <span data-ttu-id="15813-106">È anche possibile associare a un'origine dati in fase di esecuzione impostando la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> proprietà `True` e l'assegnazione di un'origine dati per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="15813-106">You can also bind to a data source at run time by setting the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> property to `True` and assigning a data source to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> property.</span></span> <span data-ttu-id="15813-107">In questo caso, è necessario gestire tutte le interazioni con l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="15813-107">In this case, you will need to manage all interaction with the data source.</span></span> <span data-ttu-id="15813-108">Per ulteriori informazioni, vedere [modalità virtuale nel controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="15813-108">For more information, see [Virtual Mode in the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a><span data-ttu-id="15813-109">Per creare un oggetto con associazione a dati DataRepeater</span><span class="sxs-lookup"><span data-stu-id="15813-109">To create a data-bound DataRepeater</span></span>  
  
1.  <span data-ttu-id="15813-110">Trascinare un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo il **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** a un controllo form o del contenitore.</span><span class="sxs-lookup"><span data-stu-id="15813-110">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="15813-111">Trascinare i quadratini di ridimensionamento e la posizione per dimensioni e posizione del controllo.</span><span class="sxs-lookup"><span data-stu-id="15813-111">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="15813-112">Si noti che il controllo dispone di due aree rettangolari.</span><span class="sxs-lookup"><span data-stu-id="15813-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="15813-113">L'area superiore è il *modello di elemento*; i controlli aggiunti al modello verranno ripetuti in ogni voce di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="15813-113">The upper region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="15813-114">L'area inferiore è la *viewport*, in cui verranno visualizzati gli elementi.</span><span class="sxs-lookup"><span data-stu-id="15813-114">The lower region is the *viewport*, where the items will be displayed.</span></span>  
  
     <span data-ttu-id="15813-115">È possibile ridimensionare e posizionare il controllo o il modello di elemento tramite la modifica anche il **dimensioni** e **posizione** proprietà nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="15813-115">You can also size and position the control or the item template by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="15813-116">Scegliere **Mostra origini dati** dal menu **Dati**.</span><span class="sxs-lookup"><span data-stu-id="15813-116">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15813-117">Se il **origini dati** finestra è vuota, aggiungere un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="15813-117">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="15813-118">Per altre informazioni, vedere [Add new data sources](/visualstudio/data-tools/add-new-data-sources) (Aggiungere nuove origini dati).</span><span class="sxs-lookup"><span data-stu-id="15813-118">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="15813-119">Nel **origini dati** finestra, selezionare il nodo di livello superiore per la tabella che contiene i dati che si desidera associare.</span><span class="sxs-lookup"><span data-stu-id="15813-119">In the **Data Sources** window, select the top-level node for the table that contains the data that you want to bind.</span></span>  
  
5.  <span data-ttu-id="15813-120">Modificare il tipo di rilascio della tabella da `Details` facendo `Details` nell'elenco a discesa nel nodo della tabella.</span><span class="sxs-lookup"><span data-stu-id="15813-120">Change the drop type of the table to `Details` by clicking `Details` in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="15813-121">Selezionare il nodo della tabella e trascinarlo sull'area del modello di elemento del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.</span><span class="sxs-lookup"><span data-stu-id="15813-121">Select the table node and drag it onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="15813-122">È possibile specificare i tipi di controlli che vengono visualizzati per ogni campo.</span><span class="sxs-lookup"><span data-stu-id="15813-122">You can specify which types of controls are displayed for each field.</span></span> <span data-ttu-id="15813-123">Per ulteriori informazioni, vedere [impostare il controllo da creare durante il trascinamento dalla finestra Origini dati](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span><span class="sxs-lookup"><span data-stu-id="15813-123">For more information, see [Set the control to be created when dragging from the Data Sources window](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15813-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15813-124">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="15813-125">Introduzione al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="15813-125">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="15813-126">Procedura: Visualizzare i controlli non associati in un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="15813-126">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="15813-127">Procedura: creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="15813-127">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="15813-128">Procedura: Modificare l'aspetto di un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="15813-128">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="15813-129">Risoluzione dei problemi relativi al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="15813-129">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
