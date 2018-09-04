---
title: 'Procedura: aggiungere e rimuovere schede con il controllo TabControl Windows Form mediante la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: 51f84a1272749b92f8ef4a74771c84e01511a678
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521326"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="f5f12-102">Procedura: aggiungere e rimuovere schede con il controllo TabControl Windows Form mediante la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f5f12-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="f5f12-103">Quando si inserisce un <xref:System.Windows.Forms.TabControl> controllo sul form, contiene due schede per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f5f12-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="f5f12-104">È possibile aggiungere o rimuovere schede tramite la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="f5f12-104">You can add or remove tabs using the designer.</span></span>  
  
 <span data-ttu-id="f5f12-105">La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.TabControl> controllo.</span><span class="sxs-lookup"><span data-stu-id="f5f12-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="f5f12-106">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto di applicazione Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f5f12-106">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5f12-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="f5f12-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f5f12-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="f5f12-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f5f12-109">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f5f12-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="f5f12-110">Per aggiungere o rimuovere una scheda usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f5f12-110">To add or remove a tab using the designer</span></span>  
  
-   <span data-ttu-id="f5f12-111">Nello smart tag del controllo, fare clic su **Aggiungi scheda** o **Rimuovi scheda**</span><span class="sxs-lookup"><span data-stu-id="f5f12-111">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>  
  
     <span data-ttu-id="f5f12-112">oppure</span><span class="sxs-lookup"><span data-stu-id="f5f12-112">-or-</span></span>  
  
     <span data-ttu-id="f5f12-113">Nel **delle proprietà** finestra, fare clic sul **puntini di sospensione** pulsante (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto a il <xref:System.Windows.Forms.TabControl.TabPages%2A> per aprire la **Editor della raccolta controllo TabPage**.</span><span class="sxs-lookup"><span data-stu-id="f5f12-113">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="f5f12-114">Fare clic sui **Add** oppure **rimuovere** pulsante.</span><span class="sxs-lookup"><span data-stu-id="f5f12-114">Click the **Add** or **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f12-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5f12-115">See Also</span></span>  
 [<span data-ttu-id="f5f12-116">Controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="f5f12-116">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="f5f12-117">Panoramica del controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="f5f12-117">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="f5f12-118">Procedura: Aggiungere un controllo a un oggetto TabPage</span><span class="sxs-lookup"><span data-stu-id="f5f12-118">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="f5f12-119">Procedura: Disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="f5f12-119">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="f5f12-120">Procedura: Modificare l'aspetto del controllo TabControl di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f5f12-120">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
