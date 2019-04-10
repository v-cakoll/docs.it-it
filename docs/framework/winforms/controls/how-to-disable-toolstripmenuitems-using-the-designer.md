---
title: 'Procedura: Disabilitare ToolStripMenuItems usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 9965825458afcd50b29699c3b89ed506078e04d9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338059"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="313b6-102">Procedura: Disabilitare ToolStripMenuItems usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="313b6-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="313b6-103">È possibile limitare o estendere i comandi di che un utente può eseguire l'abilitazione e disabilitazione di voci di menu in risposta alle attività dell'utente.</span><span class="sxs-lookup"><span data-stu-id="313b6-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="313b6-104">Voci di menu sono abilitate per impostazione predefinita quando vengono creati, ma ciò può essere modificato tramite la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="313b6-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="313b6-105">È possibile modificare questa proprietà in fase di progettazione nel **proprietà** finestra o a livello di codice mediante l'impostazione nel codice.</span><span class="sxs-lookup"><span data-stu-id="313b6-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="313b6-106">Per altre informazioni, vedere [Procedura: Disabilitare i ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span><span class="sxs-lookup"><span data-stu-id="313b6-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="313b6-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="313b6-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="313b6-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="313b6-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="313b6-109">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="313b6-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="313b6-110">Per disabilitare una voce di menu in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="313b6-110">To disable a menu item at design time</span></span>  
  
1. <span data-ttu-id="313b6-111">Con la voce di menu selezionata nel form, impostare il <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="313b6-111">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="313b6-112">La voce di menu di primo livello o prima in un menu di disabilitazione disabilita tutte le voci di menu contenute all'interno del menu.</span><span class="sxs-lookup"><span data-stu-id="313b6-112">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="313b6-113">La disabilitazione di una voce di menu che contiene voci di sottomenu disabilita in modo analogo, le voci di sottomenu.</span><span class="sxs-lookup"><span data-stu-id="313b6-113">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="313b6-114">Se tutti i comandi in un determinato menu non sono disponibili all'utente, viene considerata buona norma di programmazione per nascondere e disabilitare l'intero menu, come questa operazione presenta un'interfaccia utente pulita.</span><span class="sxs-lookup"><span data-stu-id="313b6-114">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="313b6-115">Si deve nascondere e disabilitare il menu di scelta, come nascondere da solo non impedisce l'accesso a un comando di menu tramite un tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="313b6-115">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="313b6-116">Impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di una voce di menu di primo livello a `false` per nascondere l'intero menu.</span><span class="sxs-lookup"><span data-stu-id="313b6-116">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="313b6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="313b6-117">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="313b6-118">Procedura: Nascondere ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="313b6-118">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="313b6-119">Panoramica del controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="313b6-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
