---
title: Cenni preliminari sul componente MainMenu
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745120"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="d82a4-102">Cenni preliminari sul componente MainMenu (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="d82a4-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="d82a4-103">Anche se <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituiscono e aggiungono funzionalità ai controlli <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="d82a4-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="d82a4-104">Il componente Windows Forms <xref:System.Windows.Forms.MainMenu> Visualizza un menu in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d82a4-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="d82a4-105">Tutti i sottomenu del menu principale e dei singoli elementi sono <xref:System.Windows.Forms.MenuItem> oggetti.</span><span class="sxs-lookup"><span data-stu-id="d82a4-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="d82a4-106">Proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="d82a4-106">Key Properties</span></span>  
 <span data-ttu-id="d82a4-107">Una voce di menu può essere designata come elemento predefinito impostando la proprietà <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="d82a4-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="d82a4-108">Quando si fa clic sul menu, l'elemento predefinito viene visualizzato in grassetto.</span><span class="sxs-lookup"><span data-stu-id="d82a4-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="d82a4-109">La proprietà <xref:System.Windows.Forms.MenuItem.Checked%2A> della voce di menu è `true` o `false`e indica se la voce di menu è selezionata.</span><span class="sxs-lookup"><span data-stu-id="d82a4-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="d82a4-110">La proprietà <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> della voce di menu consente di personalizzare l'aspetto dell'elemento selezionato: se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostato su `true`, viene visualizzato un pulsante di opzione accanto all'elemento; Se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostato su `false`, accanto all'elemento viene visualizzato un segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="d82a4-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d82a4-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d82a4-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="d82a4-112">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="d82a4-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
