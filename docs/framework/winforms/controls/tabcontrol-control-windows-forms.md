---
title: Controllo TabControl (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TabControl control [Windows Forms]
- tab controls
- tab controls [Windows Forms], creating
- multipage dialog boxes
- dialog boxes [Windows Forms], creating multipage
- property pages [Windows Forms], creating
- tab dialog boxes
ms.assetid: 915091af-93ac-4d3d-8283-738dd2d21ea7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fdeb5011e5f44eb45d553045c2f89b97f9e4d100
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="tabcontrol-control-windows-forms"></a><span data-ttu-id="114c3-102">Controllo TabControl (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="114c3-102">TabControl Control (Windows Forms)</span></span>
<span data-ttu-id="114c3-103">Il controllo `TabControl` di Windows Form consente di visualizzare più schede, come i divisori di un raccoglitore o le etichette di una serie di cartelle da archivio.</span><span class="sxs-lookup"><span data-stu-id="114c3-103">The Windows Forms `TabControl` displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="114c3-104">Le schede possono contenere immagini e altri controlli.</span><span class="sxs-lookup"><span data-stu-id="114c3-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="114c3-105">Il controllo `TabControl` può essere usato per creare pagine delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="114c3-105">Use the `TabControl` to create property pages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="114c3-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="114c3-106">In This Section</span></span>  
 [<span data-ttu-id="114c3-107">Panoramica del controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="114c3-107">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="114c3-108">Definisce il controllo e ne illustra le funzionalità chiave e le proprietà.</span><span class="sxs-lookup"><span data-stu-id="114c3-108">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="114c3-109">Procedura: Aggiungere un controllo a un oggetto TabPage</span><span class="sxs-lookup"><span data-stu-id="114c3-109">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 <span data-ttu-id="114c3-110">Fornisce indicazioni per la visualizzazione dei controlli in schede.</span><span class="sxs-lookup"><span data-stu-id="114c3-110">Gives directions for displaying controls on tab pages.</span></span>  
  
 [<span data-ttu-id="114c3-111">Procedura: Aggiungere e rimuovere schede con il controllo TabControl di Windows Form</span><span class="sxs-lookup"><span data-stu-id="114c3-111">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 <span data-ttu-id="114c3-112">Fornisce indicazioni per l'aggiunta e rimozione di schede nella finestra di progettazione o nel codice.</span><span class="sxs-lookup"><span data-stu-id="114c3-112">Gives directions for adding and removing tabs in the designer or in code.</span></span>  
  
 [<span data-ttu-id="114c3-113">Procedura: Modificare l'aspetto del controllo TabControl di Windows Form</span><span class="sxs-lookup"><span data-stu-id="114c3-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 <span data-ttu-id="114c3-114">Fornisce indicazioni per la regolazione delle proprietà che influiscono sull'aspetto delle singole schede.</span><span class="sxs-lookup"><span data-stu-id="114c3-114">Gives directions for adjusting properties that affect the appearance of individual tabs.</span></span>  
  
 [<span data-ttu-id="114c3-115">Procedura: Disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="114c3-115">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 <span data-ttu-id="114c3-116">Illustra come limitare l'accesso a una pagina della scheda, eventualmente in base alle credenziali utente.</span><span class="sxs-lookup"><span data-stu-id="114c3-116">Explains how to restrict access to a tab page, possibly based on user credentials.</span></span>  
  
 <span data-ttu-id="114c3-117">Vedere anche [procedura: aggiungere e rimuovere schede con Windows Form TabControl usando la finestra di progettazione](http://msdn.microsoft.com/library/ms233654\(v=vs.110\)), [procedura: aggiungere un controllo a una pagina della scheda mediante la finestra di progettazione](http://msdn.microsoft.com/library/ms233668\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="114c3-117">Also see [How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer](http://msdn.microsoft.com/library/ms233654\(v=vs.110\)), [How to: Add a Control to a Tab Page Using the Designer](http://msdn.microsoft.com/library/ms233668\(v=vs.110\))</span></span>  
  
## <a name="reference"></a><span data-ttu-id="114c3-118">Riferimento</span><span class="sxs-lookup"><span data-stu-id="114c3-118">Reference</span></span>  
 <span data-ttu-id="114c3-119">Classe <xref:System.Windows.Forms.TabControl></span><span class="sxs-lookup"><span data-stu-id="114c3-119"><xref:System.Windows.Forms.TabControl> class</span></span>  
 <span data-ttu-id="114c3-120">Descrive la classe e fornisce i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="114c3-120">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="114c3-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="114c3-121">Related Sections</span></span>  
 [<span data-ttu-id="114c3-122">Finestre di dialogo in Windows Form</span><span class="sxs-lookup"><span data-stu-id="114c3-122">Dialog Boxes in Windows Forms</span></span>](../../../../docs/framework/winforms/dialog-boxes-in-windows-forms.md)  
 <span data-ttu-id="114c3-123">Fornisce un elenco di attività per le finestre di dialogo, che spesso contengono schede.</span><span class="sxs-lookup"><span data-stu-id="114c3-123">Provides a list of tasks for dialog boxes, which often display tabs.</span></span>  
  
 [<span data-ttu-id="114c3-124">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="114c3-124">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="114c3-125">Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.</span><span class="sxs-lookup"><span data-stu-id="114c3-125">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
