---
title: 'Procedura: Visualizzare i controlli non associati in un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: a20e1ba83d1963bc3d4c135817767ee02fcbdeda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730789"
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="ed36c-102">Procedura: Visualizzare i controlli non associati in un controllo DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="ed36c-102">How to: Display Unbound Controls in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="ed36c-103">Oltre ai controlli associati, è possibile aggiungere altri controlli a un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, ad esempio un'etichetta statica o di un'immagine che viene ripetuta in ogni elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.</span><span class="sxs-lookup"><span data-stu-id="ed36c-103">In addition to bound controls, you may want to add other controls to a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed36c-104">È anche necessario almeno un controllo associato <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> o non verrà visualizzata in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ed36c-104">You must also have at least one bound control on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> or nothing will be displayed at run time.</span></span>  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a><span data-ttu-id="ed36c-105">Per aggiungere i controlli non associati a un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="ed36c-105">To add unbound controls to a DataRepeater</span></span>  
  
1.  <span data-ttu-id="ed36c-106">Trascinare un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllare dal **Visual Basic Power Packs** scheda il **casella degli strumenti** a un form o un controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="ed36c-106">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="ed36c-107">Trascinare i quadratini di ridimensionamento e la posizione per le dimensioni e posizionare il controllo.</span><span class="sxs-lookup"><span data-stu-id="ed36c-107">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="ed36c-108">È anche possibile ridimensionare e posizionare il controllo modificando la **dimensioni** e **posizione** proprietà nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="ed36c-108">You can also size and position the control by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="ed36c-109">Aggiungere almeno un controllo con associazione a dati per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.</span><span class="sxs-lookup"><span data-stu-id="ed36c-109">Add at least one data-bound control to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="ed36c-110">Per altre informazioni, vedere [Procedura: Visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="ed36c-110">For more information, see [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
4.  <span data-ttu-id="ed36c-111">Trascinare un controllo dal **casella degli strumenti** nell'area modello dell'elemento del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.</span><span class="sxs-lookup"><span data-stu-id="ed36c-111">Drag a control from the **Toolbox** onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="ed36c-112">Si noti che il controllo dispone di due aree rettangolari.</span><span class="sxs-lookup"><span data-stu-id="ed36c-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="ed36c-113">L'area interna è il *modello di elemento*; i controlli aggiunti al modello verranno ripetuti in ciascun elemento di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ed36c-113">The inner region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="ed36c-114">L'area esterna è il *viewport*, in cui gli elementi verranno visualizzati; controlli che vengono aggiunti a questa area non verranno visualizzati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ed36c-114">The outer region is the *viewport*, where the items will be displayed; controls that are added to this region will not be displayed at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed36c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed36c-115">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [<span data-ttu-id="ed36c-116">Introduzione al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="ed36c-116">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="ed36c-117">Risoluzione dei problemi relativi al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="ed36c-117">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="ed36c-118">Procedura: Visualizzare i dati associati in un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="ed36c-118">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="ed36c-119">Procedura: Creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="ed36c-119">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
- [<span data-ttu-id="ed36c-120">Procedura: Modificare l'aspetto di un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="ed36c-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
