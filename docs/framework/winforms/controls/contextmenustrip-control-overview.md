---
title: Cenni preliminari sul controllo ContextMenuStrip
ms.date: 03/30/2017
f1_keywords:
- ContextMenuStrip
helpviewer_keywords:
- context menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- shortcut menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- ContextMenuStrip control [Windows Forms], about ContextMenuStrip control
ms.assetid: 9787cdb3-88f1-4198-972f-eefd9524ce39
ms.openlocfilehash: e4a6add5297ba7db606ca1891e9279141f8d6d20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962162"
---
# <a name="contextmenustrip-control-overview"></a><span data-ttu-id="a56ce-102">Cenni preliminari sul controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="a56ce-102">ContextMenuStrip Control Overview</span></span>
> [!NOTE]
> <span data-ttu-id="a56ce-103">Il <xref:System.Windows.Forms.ContextMenuStrip> controllo sostituisce e aggiunge funzionalità <xref:System.Windows.Forms.ContextMenu> al controllo; tuttavia, il <xref:System.Windows.Forms.ContextMenu> controllo viene mantenuto per compatibilità con le versioni precedenti e per un uso futuro, se lo si sceglie.</span><span class="sxs-lookup"><span data-stu-id="a56ce-103">The <xref:System.Windows.Forms.ContextMenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> control; however, the <xref:System.Windows.Forms.ContextMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="a56ce-104">I menu di scelta rapida, detti anche menu di scelta rapida, vengono visualizzati nella posizione del mouse quando l'utente fa clic con il pulsante destro del mouse.</span><span class="sxs-lookup"><span data-stu-id="a56ce-104">Shortcut menus, also called context menus, appear at the mouse position when the user clicks the right mouse button.</span></span> <span data-ttu-id="a56ce-105">I *menu* di scelta rapida forniscono le opzioni per l'area client o il controllo nella posizione del puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="a56ce-105">Shortcut *menus* provide options for the client area or the control at the mouse pointer location.</span></span>  
  
 <span data-ttu-id="a56ce-106">Il <xref:System.Windows.Forms.ContextMenuStrip> controllo è progettato per funzionare senza problemi con i <xref:System.Windows.Forms.ToolStrip> nuovi controlli e correlati, ma è possibile associare <xref:System.Windows.Forms.ContextMenuStrip> un oggetto ad altri controlli in modo altrettanto semplice.</span><span class="sxs-lookup"><span data-stu-id="a56ce-106">The <xref:System.Windows.Forms.ContextMenuStrip> control is designed to work seamlessly with the new <xref:System.Windows.Forms.ToolStrip> and related controls, but you can associate a <xref:System.Windows.Forms.ContextMenuStrip> with other controls just as easily.</span></span>  
  
 <span data-ttu-id="a56ce-107">Nella tabella seguente vengono illustrate <xref:System.Windows.Forms.ContextMenuStrip> le principali classi complementari.</span><span class="sxs-lookup"><span data-stu-id="a56ce-107">The following table shows the important <xref:System.Windows.Forms.ContextMenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="a56ce-108">Classe</span><span class="sxs-lookup"><span data-stu-id="a56ce-108">Class</span></span>|<span data-ttu-id="a56ce-109">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="a56ce-109">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="a56ce-110">Rappresenta un'opzione selezionabile visualizzata in un <xref:System.Windows.Forms.MenuStrip> oggetto <xref:System.Windows.Forms.ContextMenuStrip>o.</span><span class="sxs-lookup"><span data-stu-id="a56ce-110">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="a56ce-111">Rappresenta un controllo che consente all'utente di selezionare un singolo elemento da un elenco visualizzato quando l'utente fa clic su <xref:System.Windows.Forms.ToolStripDropDownButton> o su una voce di menu di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="a56ce-111">Represents a control that enables the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="a56ce-112">Fornisce la funzionalità di base per i <xref:System.Windows.Forms.ToolStripItem> controlli derivati da che visualizzano gli elementi a discesa quando vengono selezionate.</span><span class="sxs-lookup"><span data-stu-id="a56ce-112">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a56ce-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a56ce-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
