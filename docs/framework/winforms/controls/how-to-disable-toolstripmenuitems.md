---
title: 'Procedura: disabilitare ToolStripMenuItems'
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
ms.openlocfilehash: 20d0e13642aac3004a31ff416318cf6723207379
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532028"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="3d960-102">Procedura: disabilitare ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="3d960-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="3d960-103">È possibile limitare o ampliare i comandi di che un utente può eseguire mediante l'abilitazione e disabilitazione di voci di menu in risposta alle attività dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3d960-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="3d960-104">Voci di menu sono attivate per impostazione predefinita quando vengono creati, ma ciò può essere modificata tramite il <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="3d960-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="3d960-105">È possibile modificare questa proprietà in fase di progettazione nel **proprietà** finestra o a livello di codice mediante l'impostazione nel codice.</span><span class="sxs-lookup"><span data-stu-id="3d960-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="3d960-106">Per disabilitare una voce di menu a livello di codice</span><span class="sxs-lookup"><span data-stu-id="3d960-106">To disable a menu item programmatically</span></span>  
  
-   <span data-ttu-id="3d960-107">All'interno del metodo in cui si impostano le proprietà della voce di menu, aggiungere codice per impostare il <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="3d960-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
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
    >  <span data-ttu-id="3d960-108">La voce di menu prima di primo livello in un menu di disabilitazione nasconde tutte le voci di menu contenute all'interno del menu, ma non li disabilita.</span><span class="sxs-lookup"><span data-stu-id="3d960-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="3d960-109">Analogamente, la disabilitazione di una voce di menu che contiene voci di sottomenu nasconde le voci di sottomenu, ma non li disabilita.</span><span class="sxs-lookup"><span data-stu-id="3d960-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="3d960-110">Se non sono disponibili all'utente tutti i comandi di un menu, buona norma di programmazione per nascondere e disabilitare l'intero menu, viene considerato come l'interfaccia utente pulita.</span><span class="sxs-lookup"><span data-stu-id="3d960-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="3d960-111">Nascondere e disabilitare il menu e disattivare ogni elemento e la voce di sottomenu nel menu, in quanto nasconderlo solamente non impedisce l'accesso a un comando di menu tramite un tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="3d960-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="3d960-112">Impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di una voce di menu di primo livello per `false` per nascondere l'intero menu.</span><span class="sxs-lookup"><span data-stu-id="3d960-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d960-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d960-113">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="3d960-114">Procedura: Nascondere ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="3d960-114">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [<span data-ttu-id="3d960-115">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="3d960-115">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
