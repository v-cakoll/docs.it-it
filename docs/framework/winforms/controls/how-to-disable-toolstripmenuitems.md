---
title: 'Procedura: Disabilitare ToolStripMenuItems'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
ms.openlocfilehash: f86a2934e799e4604693491dacbecc517d44d810
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046218"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="90192-102">Procedura: Disabilitare ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="90192-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="90192-103">È possibile limitare o ampliare i comandi che un utente può eseguire abilitando e disabilitando le voci di menu in risposta alle attività dell'utente.</span><span class="sxs-lookup"><span data-stu-id="90192-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="90192-104">Le voci di menu sono abilitate per impostazione predefinita al momento della creazione, ma possono essere <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> modificate tramite la proprietà.</span><span class="sxs-lookup"><span data-stu-id="90192-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="90192-105">È possibile modificare questa proprietà in fase di progettazione nella finestra **Proprietà** o a livello di codice impostando tale proprietà nel codice.</span><span class="sxs-lookup"><span data-stu-id="90192-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="90192-106">Per disabilitare una voce di menu a livello di codice</span><span class="sxs-lookup"><span data-stu-id="90192-106">To disable a menu item programmatically</span></span>  
  
- <span data-ttu-id="90192-107">All'interno del metodo in cui si impostano le proprietà della voce di menu, aggiungere <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> il codice `false`su cui impostare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="90192-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="90192-108">La disabilitazione della prima o della voce di menu di primo livello in un menu nasconde tutte le voci di menu contenute nel menu, ma non le Disabilita.</span><span class="sxs-lookup"><span data-stu-id="90192-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="90192-109">Analogamente, la disabilitazione di una voce di menu con voci di sottomenu nasconde le voci di sottomenu, ma non le Disabilita.</span><span class="sxs-lookup"><span data-stu-id="90192-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="90192-110">Se tutti i comandi di un determinato menu non sono disponibili per l'utente, viene considerata una procedura di programmazione efficace per nascondere e disabilitare l'intero menu, in quanto presenta un'interfaccia utente pulita.</span><span class="sxs-lookup"><span data-stu-id="90192-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="90192-111">È necessario nascondere e disabilitare il menu e disabilitare tutti gli elementi e le voci di sottomenu nel menu, perché la sola maschera non impedisce l'accesso a un comando di menu tramite un tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="90192-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="90192-112">Impostare la <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di una voce di menu di primo livello `false` su per nascondere l'intero menu.</span><span class="sxs-lookup"><span data-stu-id="90192-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90192-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90192-113">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="90192-114">Procedura: Nascondi ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="90192-114">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="90192-115">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="90192-115">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
