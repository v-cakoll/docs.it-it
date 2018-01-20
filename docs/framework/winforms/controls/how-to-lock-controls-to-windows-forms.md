---
title: 'Procedura: bloccare i controlli di un Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f5cd70e71a4a8bc48a3240055117dadc1086a50
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="1db83-102">Procedura: bloccare i controlli di un Windows Form</span><span class="sxs-lookup"><span data-stu-id="1db83-102">How to: Lock Controls to Windows Forms</span></span>
<span data-ttu-id="1db83-103">Quando si progetta l'interfaccia utente (UI) dell'applicazione Windows, è possibile bloccare i controlli di una volta posizionati correttamente, in modo che non vengano spostati o ridimensionati quando si impostano altre proprietà inavvertitamente.</span><span class="sxs-lookup"><span data-stu-id="1db83-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>  
  
 <span data-ttu-id="1db83-104">Inoltre, è possibile bloccare e sbloccare tutti i controlli del form in una sola volta, che è utile per i moduli con molti controlli, o è possibile sbloccare singoli controlli.</span><span class="sxs-lookup"><span data-stu-id="1db83-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="1db83-105">Dopo aver posizionato tutti i controlli in cui si desidera utilizzarle sul form, bloccarle tutte per evitare lo spostamento errato.</span><span class="sxs-lookup"><span data-stu-id="1db83-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1db83-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="1db83-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1db83-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="1db83-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1db83-108">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="1db83-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-lock-a-control"></a><span data-ttu-id="1db83-109">Per bloccare un controllo</span><span class="sxs-lookup"><span data-stu-id="1db83-109">To lock a control</span></span>  
  
1.  <span data-ttu-id="1db83-110">Nel **proprietà** finestra, fare clic su di **bloccato** proprietà e selezionare `true`.</span><span class="sxs-lookup"><span data-stu-id="1db83-110">In the **Properties** window, click the **Locked** property and select `true`.</span></span> <span data-ttu-id="1db83-111">(Fare doppio clic sul nome attiva o disattiva l'impostazione della proprietà.)</span><span class="sxs-lookup"><span data-stu-id="1db83-111">(Double-clicking the name toggles the property setting.)</span></span>  
  
     <span data-ttu-id="1db83-112">In alternativa, il pulsante destro del controllo e scegliere **Blocca controlli**.</span><span class="sxs-lookup"><span data-stu-id="1db83-112">Alternatively, right-click the control and choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1db83-113">Il blocco dei controlli impedisce trascinati nell'area di progettazione in un percorso o la nuova dimensione.</span><span class="sxs-lookup"><span data-stu-id="1db83-113">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="1db83-114">Tuttavia, è possibile comunque modificare dimensioni o la posizione dei controlli mediante il **proprietà** finestra o nel codice.</span><span class="sxs-lookup"><span data-stu-id="1db83-114">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>  
  
### <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="1db83-115">Per bloccare tutti i controlli in un form</span><span class="sxs-lookup"><span data-stu-id="1db83-115">To lock all the controls on a form</span></span>  
  
1.  <span data-ttu-id="1db83-116">Dal **formato** menu, scegliere **Blocca controlli**.</span><span class="sxs-lookup"><span data-stu-id="1db83-116">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1db83-117">Questo comando Blocca le dimensioni del form, poiché un form è un controllo.</span><span class="sxs-lookup"><span data-stu-id="1db83-117">This command locks the form's size as well, because a form is a control.</span></span>  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="1db83-118">Per sbloccare tutti i controlli bloccati in un form</span><span class="sxs-lookup"><span data-stu-id="1db83-118">To unlock all locked controls on a form</span></span>  
  
1.  <span data-ttu-id="1db83-119">Dal **formato** menu, scegliere **Blocca controlli**.</span><span class="sxs-lookup"><span data-stu-id="1db83-119">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
     <span data-ttu-id="1db83-120">Tutti i controlli precedentemente bloccati nel form vengono sbloccate.</span><span class="sxs-lookup"><span data-stu-id="1db83-120">All previously locked controls on the form are now unlocked.</span></span>  
  
### <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="1db83-121">Per sbloccare singolarmente i controlli bloccati</span><span class="sxs-lookup"><span data-stu-id="1db83-121">To unlock locked controls individually</span></span>  
  
1.  <span data-ttu-id="1db83-122">Nel **proprietà** finestra, fare clic su di **bloccato** proprietà e selezionare `false`.</span><span class="sxs-lookup"><span data-stu-id="1db83-122">In the **Properties** window, click the **Locked** property and select `false`.</span></span> <span data-ttu-id="1db83-123">(Fare doppio clic sul nome attiva o disattiva l'impostazione della proprietà.)</span><span class="sxs-lookup"><span data-stu-id="1db83-123">(Double-clicking the name toggles the property setting.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db83-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1db83-124">See Also</span></span>  
 [<span data-ttu-id="1db83-125">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="1db83-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="1db83-126">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1db83-126">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="1db83-127">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="1db83-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="1db83-128">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1db83-128">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="1db83-129">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="1db83-129">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
