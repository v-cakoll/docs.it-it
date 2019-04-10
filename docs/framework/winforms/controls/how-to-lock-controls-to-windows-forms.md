---
title: 'Procedura: Bloccare i controlli di Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: ac5fbf33564ed2dd1a030132a35b36164f777519
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301698"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="84298-102">Procedura: Bloccare i controlli di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="84298-102">How to: Lock Controls to Windows Forms</span></span>
<span data-ttu-id="84298-103">Quando si progetta l'interfaccia utente (UI) dell'applicazione Windows, è possibile bloccare i controlli di una volta posizionati in modo corretto, in modo che non vengano spostati o li ridimensiono quando si impostano altre proprietà non inavvertitamente.</span><span class="sxs-lookup"><span data-stu-id="84298-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>  
  
 <span data-ttu-id="84298-104">Inoltre, è possibile bloccare e sbloccare tutti i controlli del form in una sola volta, ciò è utile per i moduli con molti controlli, oppure è possibile sbloccare singoli controlli.</span><span class="sxs-lookup"><span data-stu-id="84298-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="84298-105">Dopo avere impostato tutti i controlli in cui si desidera utilizzarle sul form, bloccarli in unica posizione per evitare lo spostamento non corretti.</span><span class="sxs-lookup"><span data-stu-id="84298-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84298-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="84298-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="84298-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="84298-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="84298-108">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="84298-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-lock-a-control"></a><span data-ttu-id="84298-109">Per bloccare un controllo</span><span class="sxs-lookup"><span data-stu-id="84298-109">To lock a control</span></span>  
  
1. <span data-ttu-id="84298-110">Nel **delle proprietà** finestra, fare clic sul **Locked** proprietà e selezionare `true`.</span><span class="sxs-lookup"><span data-stu-id="84298-110">In the **Properties** window, click the **Locked** property and select `true`.</span></span> <span data-ttu-id="84298-111">(Fare doppio clic sul nome attiva o disattiva l'impostazione della proprietà.)</span><span class="sxs-lookup"><span data-stu-id="84298-111">(Double-clicking the name toggles the property setting.)</span></span>  
  
     <span data-ttu-id="84298-112">In alternativa, il pulsante destro del controllo e scegliere **controlli di blocco**.</span><span class="sxs-lookup"><span data-stu-id="84298-112">Alternatively, right-click the control and choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="84298-113">Il blocco dei controlli ne impedisce che viene trascinato in un percorso o nuove dimensioni nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="84298-113">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="84298-114">Tuttavia, è possibile comunque modificare le dimensioni o la posizione dei controlli per mezzo del **proprietà** finestra o nel codice.</span><span class="sxs-lookup"><span data-stu-id="84298-114">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>  
  
### <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="84298-115">Per bloccare tutti i controlli in un form</span><span class="sxs-lookup"><span data-stu-id="84298-115">To lock all the controls on a form</span></span>  
  
1. <span data-ttu-id="84298-116">Dal **formato** menu, scegliere **Blocca controlli**.</span><span class="sxs-lookup"><span data-stu-id="84298-116">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="84298-117">Questo comando Blocca le dimensioni del form, perché un form è un controllo.</span><span class="sxs-lookup"><span data-stu-id="84298-117">This command locks the form's size as well, because a form is a control.</span></span>  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="84298-118">Per sbloccare tutti i controlli bloccati in un form</span><span class="sxs-lookup"><span data-stu-id="84298-118">To unlock all locked controls on a form</span></span>  
  
1. <span data-ttu-id="84298-119">Dal **formato** menu, scegliere **Blocca controlli**.</span><span class="sxs-lookup"><span data-stu-id="84298-119">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
     <span data-ttu-id="84298-120">Tutti i controlli precedentemente bloccati nel form sono ora sbloccato.</span><span class="sxs-lookup"><span data-stu-id="84298-120">All previously locked controls on the form are now unlocked.</span></span>  
  
### <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="84298-121">Per sbloccare i controlli bloccati singolarmente</span><span class="sxs-lookup"><span data-stu-id="84298-121">To unlock locked controls individually</span></span>  
  
1. <span data-ttu-id="84298-122">Nel **delle proprietà** finestra, fare clic sul **Locked** proprietà e selezionare `false`.</span><span class="sxs-lookup"><span data-stu-id="84298-122">In the **Properties** window, click the **Locked** property and select `false`.</span></span> <span data-ttu-id="84298-123">(Fare doppio clic sul nome attiva o disattiva l'impostazione della proprietà.)</span><span class="sxs-lookup"><span data-stu-id="84298-123">(Double-clicking the name toggles the property setting.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84298-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84298-124">See also</span></span>

- [<span data-ttu-id="84298-125">Controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="84298-125">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="84298-126">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="84298-126">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="84298-127">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="84298-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="84298-128">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="84298-128">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="84298-129">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="84298-129">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
