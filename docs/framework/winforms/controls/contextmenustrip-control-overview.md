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
ms.openlocfilehash: fdd23324a521ac697b7ffcd4ba134e9d3c1f8e11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526738"
---
# <a name="contextmenustrip-control-overview"></a><span data-ttu-id="cd38d-102">Cenni preliminari sul controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="cd38d-102">ContextMenuStrip Control Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="cd38d-103">Il <xref:System.Windows.Forms.ContextMenuStrip> controllo sostituisce e aggiunge la funzionalità per il <xref:System.Windows.Forms.ContextMenu> controllo, tuttavia, il <xref:System.Windows.Forms.ContextMenu> controllo viene mantenuto per compatibilità con le versioni precedenti e per utilizzo futuro, se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="cd38d-103">The <xref:System.Windows.Forms.ContextMenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> control; however, the <xref:System.Windows.Forms.ContextMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="cd38d-104">Menu di scelta rapida, l'acronimo di menu di scelta rapida, vengono visualizzati in corrispondenza della posizione del mouse quando l'utente sceglie il pulsante destro del mouse.</span><span class="sxs-lookup"><span data-stu-id="cd38d-104">Shortcut menus, also called context menus, appear at the mouse position when the user clicks the right mouse button.</span></span> <span data-ttu-id="cd38d-105">Scelta rapida *menu* forniscono opzioni per l'area client o il controllo sulla posizione del puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="cd38d-105">Shortcut *menus* provide options for the client area or the control at the mouse pointer location.</span></span>  
  
 <span data-ttu-id="cd38d-106">Il <xref:System.Windows.Forms.ContextMenuStrip> controllo è progettato per integrarsi perfettamente con il nuovo <xref:System.Windows.Forms.ToolStrip> e controlli correlati, ma è possibile associare un <xref:System.Windows.Forms.ContextMenuStrip> con altrettanto facilmente ad altri controlli.</span><span class="sxs-lookup"><span data-stu-id="cd38d-106">The <xref:System.Windows.Forms.ContextMenuStrip> control is designed to work seamlessly with the new <xref:System.Windows.Forms.ToolStrip> and related controls, but you can associate a <xref:System.Windows.Forms.ContextMenuStrip> with other controls just as easily.</span></span>  
  
 <span data-ttu-id="cd38d-107">La tabella seguente illustra l'importante <xref:System.Windows.Forms.ContextMenuStrip> classi correlate.</span><span class="sxs-lookup"><span data-stu-id="cd38d-107">The following table shows the important <xref:System.Windows.Forms.ContextMenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="cd38d-108">Classe</span><span class="sxs-lookup"><span data-stu-id="cd38d-108">Class</span></span>|<span data-ttu-id="cd38d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd38d-109">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="cd38d-110">Rappresenta un'opzione selezionabile visualizzata in un <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="cd38d-110">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="cd38d-111">Rappresenta un controllo che consente all'utente di selezionare un singolo elemento da un elenco che viene visualizzato quando l'utente sceglie un <xref:System.Windows.Forms.ToolStripDropDownButton> o una voce di menu di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="cd38d-111">Represents a control that enables the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="cd38d-112">Fornisce funzionalità di base per i controlli derivano da <xref:System.Windows.Forms.ToolStripItem> che visualizzano gli elementi di elenco a discesa quando si fa clic.</span><span class="sxs-lookup"><span data-stu-id="cd38d-112">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd38d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd38d-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
