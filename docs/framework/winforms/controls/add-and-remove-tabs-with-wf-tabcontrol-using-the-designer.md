---
title: 'Procedura: Aggiungere e rimuovere schede con il controllo TabControl di Windows Form usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: f58121455c346b2b615a5cf6e617e916618b4d6e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720319"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="d61b0-102">Procedura: Aggiungere e rimuovere schede con il controllo TabControl di Windows Form usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="d61b0-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="d61b0-103">Quando si inserisce un <xref:System.Windows.Forms.TabControl> controllo sul form, contiene due schede per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d61b0-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="d61b0-104">È possibile aggiungere o rimuovere schede tramite la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d61b0-104">You can add or remove tabs using the designer.</span></span>  
  
 <span data-ttu-id="d61b0-105">La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.TabControl> controllo.</span><span class="sxs-lookup"><span data-stu-id="d61b0-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="d61b0-106">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d61b0-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d61b0-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="d61b0-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d61b0-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="d61b0-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d61b0-109">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="d61b0-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="d61b0-110">Per aggiungere o rimuovere una scheda usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="d61b0-110">To add or remove a tab using the designer</span></span>  
  
-   <span data-ttu-id="d61b0-111">Nello smart tag del controllo, fare clic su **Aggiungi scheda** o **Rimuovi scheda**</span><span class="sxs-lookup"><span data-stu-id="d61b0-111">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>  
  
     <span data-ttu-id="d61b0-112">-oppure-</span><span class="sxs-lookup"><span data-stu-id="d61b0-112">-or-</span></span>  
  
     <span data-ttu-id="d61b0-113">Nel **delle proprietà** finestra, fare clic sul **puntini di sospensione** pulsante (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) accanto a il <xref:System.Windows.Forms.TabControl.TabPages%2A> per aprire la **Editor della raccolta controllo TabPage**.</span><span class="sxs-lookup"><span data-stu-id="d61b0-113">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="d61b0-114">Fare clic sui **Add** oppure **rimuovere** pulsante.</span><span class="sxs-lookup"><span data-stu-id="d61b0-114">Click the **Add** or **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d61b0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d61b0-115">See also</span></span>
- [<span data-ttu-id="d61b0-116">Controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="d61b0-116">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="d61b0-117">Panoramica del controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="d61b0-117">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="d61b0-118">Procedura: Aggiungere un controllo a un oggetto TabPage</span><span class="sxs-lookup"><span data-stu-id="d61b0-118">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="d61b0-119">Procedura: Disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="d61b0-119">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="d61b0-120">Procedura: Modificare l'aspetto del controllo TabControl Windows Form</span><span class="sxs-lookup"><span data-stu-id="d61b0-120">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
