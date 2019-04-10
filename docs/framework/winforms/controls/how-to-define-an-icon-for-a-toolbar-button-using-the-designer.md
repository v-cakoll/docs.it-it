---
title: "Procedura: Definire un'icona per un pulsante della barra degli strumenti usando la finestra di progettazione"
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 19d0b284238ed662b25627d6077c1ebe6ecc6e86
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323707"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="3e5e5-102">Procedura: Definire un'icona per un pulsante della barra degli strumenti usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="3e5e5-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="3e5e5-103">Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="3e5e5-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <xref:System.Windows.Forms.ToolBar> <span data-ttu-id="3e5e5-104">i pulsanti sono in grado di visualizzare icone all'interno di essi per facilitare l'identificazione da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="3e5e5-104">buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="3e5e5-105">Questo risultato viene ottenuto tramite l'aggiunta di immagini per le <xref:System.Windows.Forms.ImageList> componenti e associandolo al <xref:System.Windows.Forms.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="3e5e5-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
 <span data-ttu-id="3e5e5-106">La procedura seguente richiede un **dell'applicazione Windows** progetto con un form contenente una <xref:System.Windows.Forms.ToolBar> controllo e un <xref:System.Windows.Forms.ImageList> componente.</span><span class="sxs-lookup"><span data-stu-id="3e5e5-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="3e5e5-107">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3e5e5-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e5e5-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="3e5e5-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3e5e5-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="3e5e5-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3e5e5-110">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="3e5e5-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="3e5e5-111">Per impostare un'icona per un pulsante della barra degli strumenti in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="3e5e5-111">To set an icon for a toolbar button at design time</span></span>  
  
1. <span data-ttu-id="3e5e5-112">Aggiungere immagini al <xref:System.Windows.Forms.ImageList> componente.</span><span class="sxs-lookup"><span data-stu-id="3e5e5-112">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="3e5e5-113">Per altre informazioni, vedere [Procedura: Aggiungere o rimuovere immagini ImageList con la finestra di progettazione](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="3e5e5-113">For more information, see [How to: Add or Remove ImageList Images with the Designer](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>  
  
2. <span data-ttu-id="3e5e5-114">Selezionare il <xref:System.Windows.Forms.ToolBar> controllo sul form.</span><span class="sxs-lookup"><span data-stu-id="3e5e5-114">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>  
  
3. <span data-ttu-id="3e5e5-115">Nel **proprietà** impostare nella finestra di <xref:System.Windows.Forms.ToolBar> del controllo <xref:System.Windows.Forms.ToolBar.ImageList%2A> proprietà per il <xref:System.Windows.Forms.ImageList> componente.</span><span class="sxs-lookup"><span data-stu-id="3e5e5-115">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
4. <span data-ttu-id="3e5e5-116">Fare clic sui <xref:System.Windows.Forms.ToolBar> del controllo <xref:System.Windows.Forms.ToolBar.Buttons%2A> proprietà per selezionarlo, quindi fare clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) per aprire la **Insieme ToolBarButton**.</span><span class="sxs-lookup"><span data-stu-id="3e5e5-116">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **ToolBarButton Collection Editor**.</span></span>  
  
5. <span data-ttu-id="3e5e5-117">Usare il **Add** per aggiungere i pulsanti per il <xref:System.Windows.Forms.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="3e5e5-117">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
6. <span data-ttu-id="3e5e5-118">Nel **delle proprietà** finestra visualizzata nel riquadro a destra del **insieme ToolBarButton**, impostare il <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> proprietà dei pulsanti della barra degli strumenti a uno dei valori nell'elenco, che viene disegnato da immagini di cui è stato aggiunto per il <xref:System.Windows.Forms.ImageList> componente.</span><span class="sxs-lookup"><span data-stu-id="3e5e5-118">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e5e5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e5e5-119">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="3e5e5-120">Procedura: Attivare eventi di menu per i pulsanti della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="3e5e5-120">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="3e5e5-121">Controllo ToolBar</span><span class="sxs-lookup"><span data-stu-id="3e5e5-121">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="3e5e5-122">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="3e5e5-122">ImageList Component</span></span>](imagelist-component-windows-forms.md)
