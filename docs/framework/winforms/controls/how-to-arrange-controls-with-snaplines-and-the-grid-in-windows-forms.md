---
title: 'Procedura: disporre i controlli con guide di allineamento e la griglia in Windows Form'
ms.date: 03/30/2017
f1_keywords:
- GridSize
helpviewer_keywords:
- snap to grid [Windows Forms], Windows Forms Designer
- Windows Forms, grid options in designer
- controls [Windows Forms], aligning
ms.assetid: bb54bce5-880f-4a36-af68-8cf92058dc1c
ms.openlocfilehash: bbe6ae2adfe364e41f6627e6b067aa8e18e6e079
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43488080"
---
# <a name="how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms"></a><span data-ttu-id="86b9a-102">Procedura: disporre i controlli con guide di allineamento e la griglia in Windows Form</span><span class="sxs-lookup"><span data-stu-id="86b9a-102">How to: Arrange Controls with Snaplines and the Grid in Windows Forms</span></span>
<span data-ttu-id="86b9a-103">Tramite le caratteristiche di layout di Visual Studio è possibile indicare precisamente in cui i controlli vengono posizionati in un form.</span><span class="sxs-lookup"><span data-stu-id="86b9a-103">Using the layout features of Visual Studio, you can precisely direct where controls are placed on a form.</span></span> <span data-ttu-id="86b9a-104">I controlli aggiunti a un form o spostati in un form possono essere automaticamente allineati a righe e colonne della griglia di Windows Form della finestra di progettazione oppure è possibile allineare i controlli usando la funzionalità di guide di allineamento.</span><span class="sxs-lookup"><span data-stu-id="86b9a-104">Controls added to a form or moved on a form can be automatically aligned to the rows and columns of the Windows Forms Designer's grid, or you can align controls by using the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86b9a-105">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="86b9a-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="86b9a-106">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="86b9a-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="86b9a-107">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="86b9a-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-snap-all-controls-to-the-grid"></a><span data-ttu-id="86b9a-108">Per tutti i controlli alla griglia di allineamento</span><span class="sxs-lookup"><span data-stu-id="86b9a-108">To snap all controls to the grid</span></span>  
  
-   <span data-ttu-id="86b9a-109">Selezionare il **SnapToGrid** modalità di layout in Progettazione Windows Form **opzioni** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="86b9a-109">Select the **SnapToGrid** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="86b9a-110">Per altre informazioni, vedere [generale, finestra di progettazione Windows Form, finestra di dialogo Opzioni](https://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834).</span><span class="sxs-lookup"><span data-stu-id="86b9a-110">For more information, see [General, Windows Forms Designer, Options Dialog Box](https://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834).</span></span> <span data-ttu-id="86b9a-111">Tutti i controlli verranno allineano lungo i punti della griglia.</span><span class="sxs-lookup"><span data-stu-id="86b9a-111">All controls now align themselves along the points on the grid.</span></span>  
  
     <span data-ttu-id="86b9a-112">È possibile agganciare singoli controlli alla griglia bloccandoli posto.</span><span class="sxs-lookup"><span data-stu-id="86b9a-112">You can snap individual controls to the grid by locking them in place.</span></span> <span data-ttu-id="86b9a-113">Tuttavia, anche se sono bloccati, essi non può essere spostati o ridimensionati.</span><span class="sxs-lookup"><span data-stu-id="86b9a-113">However, while they are locked, they cannot be moved or resized.</span></span> <span data-ttu-id="86b9a-114">Per altre informazioni sul blocco dei controlli, vedere [procedura: blocco i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="86b9a-114">For more information about locking controls, see [How to: Lock Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span></span>  
  
### <a name="to-align-controls-using-snaplines"></a><span data-ttu-id="86b9a-115">Per allineare i controlli usando le guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="86b9a-115">To align controls using snaplines</span></span>  
  
-   <span data-ttu-id="86b9a-116">Selezionare il **guide di allineamento** modalità di layout in Progettazione Windows Form **opzioni** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="86b9a-116">Select the **SnapLines** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="86b9a-117">Per altre informazioni, vedere [procedura dettagliata: disposizione dei controlli in Windows Form usando guide di allineamento](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="86b9a-117">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span> <span data-ttu-id="86b9a-118">È ora possibile usare le guide di allineamento per allineare e disporre i controlli sul form.</span><span class="sxs-lookup"><span data-stu-id="86b9a-118">You can now use snaplines to align and arrange controls on your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86b9a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86b9a-119">See Also</span></span>  
 [<span data-ttu-id="86b9a-120">Generale, finestra di progettazione di Windows Form, finestra di dialogo Opzioni</span><span class="sxs-lookup"><span data-stu-id="86b9a-120">General, Windows Forms Designer, Options Dialog Box</span></span>](https://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="86b9a-121">Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="86b9a-121">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="86b9a-122">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="86b9a-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="86b9a-123">Procedura: Aggiungere controlli a un Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86b9a-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="86b9a-124">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="86b9a-124">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="86b9a-125">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="86b9a-125">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="86b9a-126">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="86b9a-126">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="86b9a-127">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="86b9a-127">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
