---
title: Cenni preliminari sul controllo TabControl (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- TabControl
helpviewer_keywords:
- TabControl control [Windows Forms], about TabControl control
- tab pages [Windows Forms], about tab pages
- property pages [Windows Forms], Windows Forms
- Windows Forms dialog boxes [Windows Forms], tabs
ms.assetid: 2b4ea784-a39d-463c-81d8-af74ce068476
ms.openlocfilehash: 4511882aa4c7804e535f228dd150c26a8f7689f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140881"
---
# <a name="tabcontrol-control-overview-windows-forms"></a><span data-ttu-id="011b2-102">Cenni preliminari sul controllo TabControl (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="011b2-102">TabControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="011b2-103">Il controllo <xref:System.Windows.Forms.TabControl> di Windows Form consente di visualizzare più schede, come i divisori di un raccoglitore o le etichette di una serie di cartelle da archivio.</span><span class="sxs-lookup"><span data-stu-id="011b2-103">The Windows Forms <xref:System.Windows.Forms.TabControl> displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="011b2-104">Le schede possono contenere immagini e altri controlli.</span><span class="sxs-lookup"><span data-stu-id="011b2-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="011b2-105">È possibile usare il controllo struttura a schede per produrre il tipo di finestra di dialogo di più pagine che viene visualizzato molte posizioni nel sistema operativo Windows, ad esempio le proprietà di visualizzazione del Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="011b2-105">You can use the tab control to produce the kind of multiple-page dialog box that appears many places in the Windows operating system, such as the Control Panel Display Properties.</span></span> <span data-ttu-id="011b2-106">Inoltre, il <xref:System.Windows.Forms.TabControl> può essere utilizzato per creare pagine delle proprietà, vengono usate per impostare un gruppo di proprietà correlate.</span><span class="sxs-lookup"><span data-stu-id="011b2-106">Additionally, the <xref:System.Windows.Forms.TabControl> can be used to create property pages, which are used to set a group of related properties.</span></span>  
  
## <a name="working-with-tabcontrol"></a><span data-ttu-id="011b2-107">Utilizzo di TabControl</span><span class="sxs-lookup"><span data-stu-id="011b2-107">Working with TabControl</span></span>  
 <span data-ttu-id="011b2-108">La proprietà più importante del <xref:System.Windows.Forms.TabControl> è <xref:System.Windows.Forms.TabControl.TabPages%2A>, che contiene le singole schede.</span><span class="sxs-lookup"><span data-stu-id="011b2-108">The most important property of the <xref:System.Windows.Forms.TabControl> is <xref:System.Windows.Forms.TabControl.TabPages%2A>, which contains the individual tabs.</span></span> <span data-ttu-id="011b2-109">Ciascuna scheda è un <xref:System.Windows.Forms.TabPage> oggetto.</span><span class="sxs-lookup"><span data-stu-id="011b2-109">Each individual tab is a <xref:System.Windows.Forms.TabPage> object.</span></span> <span data-ttu-id="011b2-110">Quando si fa clic su una scheda, viene generata la <xref:System.Windows.Forms.Control.Click> eventi per tale <xref:System.Windows.Forms.TabPage> oggetto.</span><span class="sxs-lookup"><span data-stu-id="011b2-110">When a tab is clicked, it raises the <xref:System.Windows.Forms.Control.Click> event for that <xref:System.Windows.Forms.TabPage> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="011b2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="011b2-111">See also</span></span>

- <xref:System.Windows.Forms.TabControl>
- [<span data-ttu-id="011b2-112">Controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="011b2-112">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="011b2-113">Procedura: Modificare l'aspetto di TabControl di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="011b2-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="011b2-114">Procedura: Aggiungere un controllo a una scheda</span><span class="sxs-lookup"><span data-stu-id="011b2-114">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="011b2-115">Procedura: Aggiungere e rimuovere schede con TabControl di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="011b2-115">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="011b2-116">Procedura: Disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="011b2-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="011b2-117">Finestre di dialogo in Windows Form</span><span class="sxs-lookup"><span data-stu-id="011b2-117">Dialog Boxes in Windows Forms</span></span>](../dialog-boxes-in-windows-forms.md)
