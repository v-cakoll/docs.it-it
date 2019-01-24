---
title: 'Procedura: Disabilitare i ToolStripMenuItems'
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
ms.openlocfilehash: 2516080708bba207c3a1d028f2e5a2411974ae5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705336"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="3f378-102">Procedura: Disabilitare i ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="3f378-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="3f378-103">È possibile limitare o estendere i comandi di che un utente può eseguire l'abilitazione e disabilitazione di voci di menu in risposta alle attività dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3f378-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="3f378-104">Voci di menu sono abilitate per impostazione predefinita quando vengono creati, ma ciò può essere modificato tramite la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="3f378-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="3f378-105">È possibile modificare questa proprietà in fase di progettazione nel **proprietà** finestra o a livello di codice mediante l'impostazione nel codice.</span><span class="sxs-lookup"><span data-stu-id="3f378-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="3f378-106">Per disabilitare una voce di menu a livello di codice</span><span class="sxs-lookup"><span data-stu-id="3f378-106">To disable a menu item programmatically</span></span>  
  
-   <span data-ttu-id="3f378-107">All'interno del metodo in cui si impostano le proprietà della voce di menu, aggiungere il codice per impostare il <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="3f378-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
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
    >  <span data-ttu-id="3f378-108">Disabilitare la voce di menu di primo livello o prima in un menu nasconde tutte le voci di menu contenute all'interno del menu, ma non li disabilita.</span><span class="sxs-lookup"><span data-stu-id="3f378-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="3f378-109">Analogamente, la disabilitazione di una voce di menu che contiene voci di sottomenu nasconde le voci di sottomenu, ma non li disabilita.</span><span class="sxs-lookup"><span data-stu-id="3f378-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="3f378-110">Se tutti i comandi in un determinato menu non sono disponibili all'utente, viene considerata buona norma di programmazione per nascondere e disabilitare l'intero menu, come questa operazione presenta un'interfaccia utente pulita.</span><span class="sxs-lookup"><span data-stu-id="3f378-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="3f378-111">Si deve nascondere e disabilitare il menu di scelta e disabilitare ogni elemento e una voce di sottomenu del menu, perché nascondere da solo non impedisce l'accesso a un comando di menu tramite un tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="3f378-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="3f378-112">Impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di una voce di menu di primo livello a `false` per nascondere l'intero menu.</span><span class="sxs-lookup"><span data-stu-id="3f378-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f378-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f378-113">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="3f378-114">Procedura: Nascondere ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="3f378-114">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="3f378-115">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="3f378-115">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
