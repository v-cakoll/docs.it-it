---
title: Cenni preliminari sul componente ContextMenu (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 6ae7817bc158f30fbf55b5f6228ecdf134d6657d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962178"
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="9147d-102">Cenni preliminari sul componente ContextMenu (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="9147d-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="9147d-103">Anche <xref:System.Windows.Forms.MenuStrip> se <xref:System.Windows.Forms.ContextMenuStrip> e sostituiscono e aggiungono <xref:System.Windows.Forms.MainMenu> funzionalità <xref:System.Windows.Forms.ContextMenu> ai controlli e delle versioni precedenti <xref:System.Windows.Forms.ContextMenu> e vengono conservati per compatibilità con le versioni precedenti e per un uso futuro, <xref:System.Windows.Forms.MainMenu> se si sceglie.</span><span class="sxs-lookup"><span data-stu-id="9147d-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="9147d-104">Con il componente <xref:System.Windows.Forms.ContextMenu> Windows Forms, è possibile fornire agli utenti un menu di scelta rapida facilmente accessibile dei comandi utilizzati di frequente associati all'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="9147d-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="9147d-105">Gli elementi in un menu di scelta rapida sono spesso un subset degli elementi dei menu principali che vengono visualizzati altrove nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9147d-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="9147d-106">Un utente può in genere accedere a un menu di scelta rapida facendo clic con il pulsante destro del mouse.</span><span class="sxs-lookup"><span data-stu-id="9147d-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="9147d-107">In Windows Forms i menu di scelta rapida sono associati ai controlli.</span><span class="sxs-lookup"><span data-stu-id="9147d-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="9147d-108">Proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="9147d-108">Key Properties</span></span>  
 <span data-ttu-id="9147d-109">È possibile associare un menu di scelta rapida a un controllo impostando la <xref:System.Windows.Forms.Control.ContextMenu%2A> proprietà <xref:System.Windows.Forms.ContextMenu> del controllo sul componente.</span><span class="sxs-lookup"><span data-stu-id="9147d-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="9147d-110">Un unico menu di scelta rapida può essere associato a più controlli, ma ogni controllo può avere un solo menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="9147d-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="9147d-111">La proprietà chiave del <xref:System.Windows.Forms.ContextMenu> componente è la <xref:System.Windows.Forms.Menu.MenuItems%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9147d-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="9147d-112">È possibile aggiungere voci di menu a livello di <xref:System.Windows.Forms.MenuItem> codice creando oggetti e aggiungendoli <xref:System.Windows.Forms.Menu.MenuItemCollection> a del menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="9147d-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="9147d-113">Poiché gli elementi in un menu di scelta rapida vengono in genere creati da altri menu, si aggiungono spesso elementi a un menu di scelta rapida copiando tali elementi.</span><span class="sxs-lookup"><span data-stu-id="9147d-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9147d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9147d-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
