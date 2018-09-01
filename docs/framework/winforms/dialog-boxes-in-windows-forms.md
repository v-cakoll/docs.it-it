---
title: Finestre di dialogo in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- dialog boxes [Windows Forms], Windows Forms
- Windows Forms dialog boxes
- dialogs [Windows Forms], using in Windows Forms
ms.assetid: d43d022b-451b-490d-9386-dc79d98fbf8a
ms.openlocfilehash: ef07c087ca43efaf99231453fcb56af0db24234a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43387741"
---
# <a name="dialog-boxes-in-windows-forms"></a><span data-ttu-id="4317a-102">Finestre di dialogo in Windows Form</span><span class="sxs-lookup"><span data-stu-id="4317a-102">Dialog Boxes in Windows Forms</span></span>
<span data-ttu-id="4317a-103">Le finestre di dialogo sono usate per interagire con l'utente e recuperare informazioni.</span><span class="sxs-lookup"><span data-stu-id="4317a-103">Dialog boxes are used to interact with the user and retrieve information.</span></span> <span data-ttu-id="4317a-104">Detto semplicemente, una finestra di dialogo è un form con la proprietà dell'enumerazione <xref:System.Windows.Forms.FormBorderStyle> impostata su `FixedDialog`.</span><span class="sxs-lookup"><span data-stu-id="4317a-104">In simple terms, a dialog box is a form with its <xref:System.Windows.Forms.FormBorderStyle> enumeration property set to `FixedDialog`.</span></span> <span data-ttu-id="4317a-105">È possibile costruire il proprio finestre di dialogo personalizzate usando Progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4317a-105">You can construct your own custom dialog boxes by using the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="4317a-106">Per personalizzare le finestre di dialogo in base a esigenze specifiche, aggiungere controlli come `Label`, `Textbox` e `Button`.</span><span class="sxs-lookup"><span data-stu-id="4317a-106">Add controls such as `Label`, `Textbox`, and `Button` to customize dialog boxes to your specific needs.</span></span> <span data-ttu-id="4317a-107">Il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] include anche finestre di dialogo predefinite, ad esempio **Apri File** e finestre di messaggio, che è possibile adattare le proprie applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4317a-107">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] also includes predefined dialog boxes, such as **File Open** and message boxes, which you can adapt for your own applications.</span></span> <span data-ttu-id="4317a-108">Per altre informazioni, vedere [componenti e controlli di finestra di dialogo](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4317a-108">For more information, see [Dialog-Box Controls and Components](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4317a-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="4317a-109">In This Section</span></span>  
 [<span data-ttu-id="4317a-110">Procedura: Visualizzare le finestre di dialogo per Windows Form</span><span class="sxs-lookup"><span data-stu-id="4317a-110">How to: Display Dialog Boxes for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-display-dialog-boxes-for-windows-forms.md)  
 <span data-ttu-id="4317a-111">Fornisce indicazioni per la visualizzazione delle finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="4317a-111">Gives directions for showing dialog boxes.</span></span>  
  
-   <span data-ttu-id="4317a-112">[Procedura: recuperare informazioni in modo selettivo usando più proprietà finestra](https://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="4317a-112">[How to: Retrieve Dialog Box Information Selectively Using Multiple Properties](https://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="4317a-113">[Procedura: recuperare informazioni dal Form padre di una finestra di dialogo](https://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="4317a-113">[How to: Retrieve Information from the Parent Form of a Dialog Box](https://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="4317a-114">[Input dell'utente alle finestre di dialogo](https://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="4317a-114">[User Input to Dialog Boxes](https://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="4317a-115">[Procedura: recuperare il risultato delle finestre di dialogo](https://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="4317a-115">[How to: Retrieve the Result for Dialog Boxes](https://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="4317a-116">[Procedura dettagliata: Recupero di informazioni collettivamente utilizzando gli oggetti finestra](https://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="4317a-116">[Walkthrough: Retrieving Dialog Box Information Collectively Using Objects](https://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="4317a-117">[Procedura: chiudere finestre di dialogo e mantenere l'Input dell'utente](https://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="4317a-117">[How to: Close Dialog Boxes and Retain User Input](https://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="4317a-118">[Procedura: creare finestre di dialogo in fase di progettazione](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="4317a-118">[How to: Create Dialog Boxes at Design Time](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="4317a-119">[Procedura: visualizzare le finestre di messaggio](https://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="4317a-119">[How to: Display Message Boxes](https://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4317a-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="4317a-120">Related Sections</span></span>  
 [<span data-ttu-id="4317a-121">Controlli e componenti della finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="4317a-121">Dialog-Box Controls and Components</span></span>](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 <span data-ttu-id="4317a-122">Elenca i controlli predefiniti della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="4317a-122">Lists the predefined dialog box controls.</span></span>  
  
 [<span data-ttu-id="4317a-123">Modifica dell'aspetto di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4317a-123">Changing the Appearance of Windows Forms</span></span>](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)  
 <span data-ttu-id="4317a-124">Contiene collegamenti ad argomenti che spiegano come cambiare l'aspetto delle applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4317a-124">Contains links to topics that describe how to change the appearance of Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="4317a-125">Panoramica del controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="4317a-125">TabControl Control Overview</span></span>](../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="4317a-126">Spiega come incorporare il controllo Struttura a schede in una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="4317a-126">Explains how you incorporate the tab control into a dialog box.</span></span>
