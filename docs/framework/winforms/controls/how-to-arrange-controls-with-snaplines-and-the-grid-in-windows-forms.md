---
title: 'Procedura: disporre i controlli con guide di allineamento e la griglia in Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: GridSize
helpviewer_keywords:
- snap to grid [Windows Forms], Windows Forms Designer
- Windows Forms, grid options in designer
- controls [Windows Forms], aligning
ms.assetid: bb54bce5-880f-4a36-af68-8cf92058dc1c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7e3754df2930503e7e7a123ffdb4d4b787338c20
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms"></a><span data-ttu-id="67efc-102">Procedura: disporre i controlli con guide di allineamento e la griglia in Windows Form</span><span class="sxs-lookup"><span data-stu-id="67efc-102">How to: Arrange Controls with Snaplines and the Grid in Windows Forms</span></span>
<span data-ttu-id="67efc-103">Utilizzando le funzionalità di layout di [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], è possibile indirizzare in modo preciso in cui vengono collocati i controlli in un form.</span><span class="sxs-lookup"><span data-stu-id="67efc-103">Using the layout features of [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], you can precisely direct where controls are placed on a form.</span></span> <span data-ttu-id="67efc-104">I controlli aggiunti a un form o spostati in un form possono essere allineati automaticamente per le righe e colonne della griglia di progettazione Windows Form oppure è possibile allineare i controlli usando la funzionalità di guide di allineamento.</span><span class="sxs-lookup"><span data-stu-id="67efc-104">Controls added to a form or moved on a form can be automatically aligned to the rows and columns of the Windows Forms Designer's grid, or you can align controls by using the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67efc-105">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="67efc-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="67efc-106">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="67efc-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="67efc-107">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="67efc-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-snap-all-controls-to-the-grid"></a><span data-ttu-id="67efc-108">Per bloccare tutti i controlli alla griglia</span><span class="sxs-lookup"><span data-stu-id="67efc-108">To snap all controls to the grid</span></span>  
  
-   <span data-ttu-id="67efc-109">Selezionare il **SnapToGrid** modalità layout di progettazione Windows Form **opzioni** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="67efc-109">Select the **SnapToGrid** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="67efc-110">Per ulteriori informazioni, vedere [generale, Progettazione Windows Form, la finestra di dialogo Opzioni](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834).</span><span class="sxs-lookup"><span data-stu-id="67efc-110">For more information, see [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834).</span></span> <span data-ttu-id="67efc-111">Tutti i controlli verranno allineano lungo i punti della griglia.</span><span class="sxs-lookup"><span data-stu-id="67efc-111">All controls now align themselves along the points on the grid.</span></span>  
  
     <span data-ttu-id="67efc-112">È possibile bloccare i singoli controlli per la griglia da bloccarli sul posto.</span><span class="sxs-lookup"><span data-stu-id="67efc-112">You can snap individual controls to the grid by locking them in place.</span></span> <span data-ttu-id="67efc-113">Tuttavia, mentre sono bloccati, essi non è da spostare o ridimensionare.</span><span class="sxs-lookup"><span data-stu-id="67efc-113">However, while they are locked, they cannot be moved or resized.</span></span> <span data-ttu-id="67efc-114">Per ulteriori informazioni sul blocco dei controlli, vedere [come: blocca i controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="67efc-114">For more information about locking controls, see [How to: Lock Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span></span>  
  
### <a name="to-align-controls-using-snaplines"></a><span data-ttu-id="67efc-115">Per allineare i controlli usando le guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="67efc-115">To align controls using snaplines</span></span>  
  
-   <span data-ttu-id="67efc-116">Selezionare il **le guide di allineamento** modalità layout di progettazione Windows Form **opzioni** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="67efc-116">Select the **SnapLines** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="67efc-117">Per ulteriori informazioni, vedere [procedura dettagliata: disposizione dei controlli in Windows Form usando guide di allineamento](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="67efc-117">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span> <span data-ttu-id="67efc-118">È ora possibile utilizzare le guide di allineamento per allineare e disporre controlli nel form.</span><span class="sxs-lookup"><span data-stu-id="67efc-118">You can now use snaplines to align and arrange controls on your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67efc-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67efc-119">See Also</span></span>  
 [<span data-ttu-id="67efc-120">Generale, finestra di progettazione Windows Form, la finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="67efc-120">General, Windows Forms Designer, Options Dialog Box</span></span>](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="67efc-121">Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="67efc-121">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="67efc-122">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="67efc-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="67efc-123">Procedura: Aggiungere controlli a un Windows Forms</span><span class="sxs-lookup"><span data-stu-id="67efc-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="67efc-124">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="67efc-124">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="67efc-125">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="67efc-125">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="67efc-126">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="67efc-126">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="67efc-127">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="67efc-127">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
