---
title: 'Procedura: disabilitare i ToolStripMenuItems con la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f704e99622900d8c37c8ddd5054a3c5ad920bc6b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="2aa4d-102">Procedura: disabilitare i ToolStripMenuItems con la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="2aa4d-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="2aa4d-103">È possibile limitare o ampliare i comandi di che un utente può eseguire mediante l'abilitazione e disabilitazione di voci di menu in risposta alle attività dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2aa4d-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="2aa4d-104">Voci di menu sono attivate per impostazione predefinita quando vengono creati, ma ciò può essere modificata tramite il <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="2aa4d-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="2aa4d-105">È possibile modificare questa proprietà in fase di progettazione nel **proprietà** finestra o a livello di codice mediante l'impostazione nel codice.</span><span class="sxs-lookup"><span data-stu-id="2aa4d-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="2aa4d-106">Per ulteriori informazioni, vedere [procedura: disabilitare ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md).</span><span class="sxs-lookup"><span data-stu-id="2aa4d-106">For more information, see [How to: Disable ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2aa4d-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="2aa4d-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2aa4d-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="2aa4d-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2aa4d-109">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="2aa4d-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="2aa4d-110">Per disabilitare una voce di menu in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="2aa4d-110">To disable a menu item at design time</span></span>  
  
1.  <span data-ttu-id="2aa4d-111">La voce di menu selezionata sul form, impostare il <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="2aa4d-111">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="2aa4d-112">La voce di menu prima di primo livello in un menu di disabilitazione disabilita tutte le voci di menu contenute all'interno del menu.</span><span class="sxs-lookup"><span data-stu-id="2aa4d-112">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="2aa4d-113">La disabilitazione di una voce di menu che contiene voci di sottomenu disabilita in modo analogo, le voci di sottomenu.</span><span class="sxs-lookup"><span data-stu-id="2aa4d-113">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="2aa4d-114">Se non sono disponibili all'utente tutti i comandi di un menu, buona norma di programmazione per nascondere e disabilitare l'intero menu, viene considerato come l'interfaccia utente pulita.</span><span class="sxs-lookup"><span data-stu-id="2aa4d-114">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="2aa4d-115">È necessario nascondere e disabilitare il menu, come nasconderlo solamente non impedisce l'accesso a un comando di menu tramite un tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="2aa4d-115">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="2aa4d-116">Impostare il <xref:System.Windows.Forms.ToolStripItem.Visible%2A> proprietà di una voce di menu di primo livello per `false` per nascondere l'intero menu.</span><span class="sxs-lookup"><span data-stu-id="2aa4d-116">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa4d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2aa4d-117">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="2aa4d-118">Procedura: Nascondere ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="2aa4d-118">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [<span data-ttu-id="2aa4d-119">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="2aa4d-119">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
