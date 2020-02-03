---
title: Cenni preliminari sul componente ContextMenu
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 83740221894941d09d1014585513043851a518e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746191"
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="46e25-102">Cenni preliminari sul componente ContextMenu (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="46e25-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="46e25-103">Anche se <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituiscono e aggiungono funzionalità ai controlli <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="46e25-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="46e25-104">Con il componente Windows Forms <xref:System.Windows.Forms.ContextMenu>, è possibile fornire agli utenti un menu di scelta rapida facilmente accessibile dei comandi utilizzati di frequente associati all'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="46e25-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="46e25-105">Gli elementi in un menu di scelta rapida sono spesso un subset degli elementi dei menu principali che vengono visualizzati altrove nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="46e25-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="46e25-106">Un utente può in genere accedere a un menu di scelta rapida facendo clic con il pulsante destro del mouse.</span><span class="sxs-lookup"><span data-stu-id="46e25-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="46e25-107">In Windows Forms i menu di scelta rapida sono associati ai controlli.</span><span class="sxs-lookup"><span data-stu-id="46e25-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="46e25-108">Proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="46e25-108">Key Properties</span></span>  
 <span data-ttu-id="46e25-109">È possibile associare un menu di scelta rapida a un controllo impostando la proprietà <xref:System.Windows.Forms.Control.ContextMenu%2A> del controllo sul componente <xref:System.Windows.Forms.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="46e25-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="46e25-110">Un unico menu di scelta rapida può essere associato a più controlli, ma ogni controllo può avere un solo menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="46e25-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="46e25-111">La proprietà chiave del componente <xref:System.Windows.Forms.ContextMenu> è la proprietà <xref:System.Windows.Forms.Menu.MenuItems%2A>.</span><span class="sxs-lookup"><span data-stu-id="46e25-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="46e25-112">È possibile aggiungere voci di menu a livello di codice creando <xref:System.Windows.Forms.MenuItem> oggetti e aggiungendoli al <xref:System.Windows.Forms.Menu.MenuItemCollection> del menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="46e25-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="46e25-113">Poiché gli elementi in un menu di scelta rapida vengono in genere creati da altri menu, si aggiungono spesso elementi a un menu di scelta rapida copiando tali elementi.</span><span class="sxs-lookup"><span data-stu-id="46e25-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e25-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46e25-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
