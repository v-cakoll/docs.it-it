---
title: 'Procedura: Raggruppare i controlli con il controllo Panel di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 662343af42f72816a5a673d2cd6d839a5dca9190
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59341400"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="aee34-102">Procedura: Raggruppare i controlli con il controllo Panel di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="aee34-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="aee34-103">Windows Form <xref:System.Windows.Forms.Panel> controlli vengono utilizzati per raggruppare altri controlli.</span><span class="sxs-lookup"><span data-stu-id="aee34-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="aee34-104">Esistono tre motivi per i controlli di gruppo.</span><span class="sxs-lookup"><span data-stu-id="aee34-104">There are three reasons to group controls.</span></span> <span data-ttu-id="aee34-105">Uno è visual raggruppamento di elementi di form per un'interfaccia utente non crittografato. un vantaggio è a livello di codice di raggruppamento, dei pulsanti di opzione, ad esempio; l'ultimo è per spostare i controlli in un'unità in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="aee34-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aee34-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="aee34-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="aee34-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="aee34-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="aee34-108">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="aee34-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="aee34-109">Per creare un gruppo di controlli</span><span class="sxs-lookup"><span data-stu-id="aee34-109">To create a group of controls</span></span>  
  
1. <span data-ttu-id="aee34-110">Trascinare un <xref:System.Windows.Forms.Panel> controllare dal **Windows Forms** scheda della casella degli strumenti in un form.</span><span class="sxs-lookup"><span data-stu-id="aee34-110">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>  
  
2. <span data-ttu-id="aee34-111">Aggiungere altri controlli nel pannello per ognuno all'interno del Pannello di disegno.</span><span class="sxs-lookup"><span data-stu-id="aee34-111">Add other controls to the panel, drawing each inside the panel.</span></span>  
  
     <span data-ttu-id="aee34-112">Se si dispone di controlli esistenti che si desidera inserire in un pannello, è possibile selezionare tutti i controlli, li tagliare negli Appunti, selezionare il <xref:System.Windows.Forms.Panel> controllare e quindi incollarli nella casella di gruppo.</span><span class="sxs-lookup"><span data-stu-id="aee34-112">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="aee34-113">È anche possibile trascinarli nel pannello.</span><span class="sxs-lookup"><span data-stu-id="aee34-113">You can also drag them into the panel.</span></span>  
  
3. <span data-ttu-id="aee34-114">(Facoltativo) Se si desidera aggiungere un bordo a un pannello, impostare il <xref:System.Windows.Forms.BorderStyle> proprietà.</span><span class="sxs-lookup"><span data-stu-id="aee34-114">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="aee34-115">Sono disponibili tre opzioni: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, e <xref:System.Windows.Forms.BorderStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="aee34-115">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aee34-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aee34-116">See also</span></span>

- [<span data-ttu-id="aee34-117">Controllo Panel</span><span class="sxs-lookup"><span data-stu-id="aee34-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="aee34-118">Panoramica del controllo Panel</span><span class="sxs-lookup"><span data-stu-id="aee34-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="aee34-119">Procedura: Impostare lo sfondo di un controllo Panel</span><span class="sxs-lookup"><span data-stu-id="aee34-119">How to: Set the Background of a Panel</span></span>](how-to-set-the-background-of-a-windows-forms-panel.md)
