---
title: Cenni preliminari sul controllo TabControl (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TabControl
helpviewer_keywords:
- TabControl control [Windows Forms], about TabControl control
- tab pages [Windows Forms], about tab pages
- property pages [Windows Forms], Windows Forms
- Windows Forms dialog boxes [Windows Forms], tabs
ms.assetid: 2b4ea784-a39d-463c-81d8-af74ce068476
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 707fb08e487acc8a585e9fe9a246e7485d5e2749
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="tabcontrol-control-overview-windows-forms"></a><span data-ttu-id="5903e-102">Cenni preliminari sul controllo TabControl (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="5903e-102">TabControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="5903e-103">Il controllo <xref:System.Windows.Forms.TabControl> di Windows Form consente di visualizzare più schede, come i divisori di un raccoglitore o le etichette di una serie di cartelle da archivio.</span><span class="sxs-lookup"><span data-stu-id="5903e-103">The Windows Forms <xref:System.Windows.Forms.TabControl> displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="5903e-104">Le schede possono contenere immagini e altri controlli.</span><span class="sxs-lookup"><span data-stu-id="5903e-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="5903e-105">Per generare il tipo di più pagine finestra di dialogo visualizzata da molte posizioni nel sistema operativo Windows, ad esempio le proprietà di visualizzazione del Pannello di controllo, è possibile utilizzare il controllo struttura a schede.</span><span class="sxs-lookup"><span data-stu-id="5903e-105">You can use the tab control to produce the kind of multiple-page dialog box that appears many places in the Windows operating system, such as the Control Panel Display Properties.</span></span> <span data-ttu-id="5903e-106">Inoltre, il <xref:System.Windows.Forms.TabControl> può essere utilizzato per creare pagine delle proprietà, vengono utilizzate per impostare un gruppo di proprietà correlate.</span><span class="sxs-lookup"><span data-stu-id="5903e-106">Additionally, the <xref:System.Windows.Forms.TabControl> can be used to create property pages, which are used to set a group of related properties.</span></span>  
  
## <a name="working-with-tabcontrol"></a><span data-ttu-id="5903e-107">Utilizzo di TabControl</span><span class="sxs-lookup"><span data-stu-id="5903e-107">Working with TabControl</span></span>  
 <span data-ttu-id="5903e-108">La proprietà più importante del <xref:System.Windows.Forms.TabControl> è <xref:System.Windows.Forms.TabControl.TabPages%2A>, che contiene le singole schede.</span><span class="sxs-lookup"><span data-stu-id="5903e-108">The most important property of the <xref:System.Windows.Forms.TabControl> is <xref:System.Windows.Forms.TabControl.TabPages%2A>, which contains the individual tabs.</span></span> <span data-ttu-id="5903e-109">Ciascuna scheda è un <xref:System.Windows.Forms.TabPage> oggetto.</span><span class="sxs-lookup"><span data-stu-id="5903e-109">Each individual tab is a <xref:System.Windows.Forms.TabPage> object.</span></span> <span data-ttu-id="5903e-110">Quando viene fatto clic su una scheda, viene generato il <xref:System.Windows.Forms.Control.Click> evento per cui <xref:System.Windows.Forms.TabPage> oggetto.</span><span class="sxs-lookup"><span data-stu-id="5903e-110">When a tab is clicked, it raises the <xref:System.Windows.Forms.Control.Click> event for that <xref:System.Windows.Forms.TabPage> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5903e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5903e-111">See Also</span></span>  
 <xref:System.Windows.Forms.TabControl>  
 [<span data-ttu-id="5903e-112">Controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="5903e-112">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="5903e-113">Procedura: Modificare l'aspetto del controllo TabControl di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5903e-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="5903e-114">Procedura: Aggiungere un controllo a un oggetto TabPage</span><span class="sxs-lookup"><span data-stu-id="5903e-114">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="5903e-115">Procedura: Aggiungere e rimuovere schede con il controllo TabControl di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5903e-115">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="5903e-116">Procedura: Disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="5903e-116">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="5903e-117">Finestre di dialogo in Windows Form</span><span class="sxs-lookup"><span data-stu-id="5903e-117">Dialog Boxes in Windows Forms</span></span>](../../../../docs/framework/winforms/dialog-boxes-in-windows-forms.md)
