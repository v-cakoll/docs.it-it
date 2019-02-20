---
title: Sviluppo di un controllo Windows Form composto
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: 1d2c6419e19aee73717bed6cfc17782d2a3f5a4a
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "56442739"
---
# <a name="developing-a-composite-windows-forms-control"></a><span data-ttu-id="a8f33-102">Sviluppo di un controllo Windows Form composto</span><span class="sxs-lookup"><span data-stu-id="a8f33-102">Developing a Composite Windows Forms Control</span></span>
<span data-ttu-id="a8f33-103">È possibile sviluppare un controllo Windows Form composito combinando altri controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="a8f33-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="a8f33-104">I controlli compositi che derivano da <xref:System.Web.UI.UserControl> sono denominati controlli utente.</span><span class="sxs-lookup"><span data-stu-id="a8f33-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="a8f33-105">La classe base, <xref:System.Windows.Forms.UserControl>, fornisce il routing della tastiera per i controlli figlio, garantendo così che i controlli figlio possano ricevere lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a8f33-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="a8f33-106">Per un esempio di un controllo utente, vedere la <xref:System.Windows.Forms.UserControl> esempio in [come: Applicare attributi nei controlli di Windows Form](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="a8f33-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="a8f33-107">Progettazione Windows Form in Visual Studio offre supporto avanzato in fase di progettazione per la creazione di controlli utente.</span><span class="sxs-lookup"><span data-stu-id="a8f33-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>  
  
-   [<span data-ttu-id="a8f33-108">Procedura: Visualizzare un controllo nella finestra di dialogo elementi della casella degli strumenti scegliere</span><span class="sxs-lookup"><span data-stu-id="a8f33-108">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
  
-   [<span data-ttu-id="a8f33-109">Procedura dettagliata: Serializzazione di raccolte di tipi Standard tramite DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="a8f33-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)  
  
-   [<span data-ttu-id="a8f33-110">Procedura dettagliata: Eredità da un controllo di Windows Forms con VisualC#</span><span class="sxs-lookup"><span data-stu-id="a8f33-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
  
-   [<span data-ttu-id="a8f33-111">Procedura: Specificare una Bitmap nella casella degli strumenti per un controllo</span><span class="sxs-lookup"><span data-stu-id="a8f33-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)  
  
-   [<span data-ttu-id="a8f33-112">Procedura: Ereditare da esistenti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a8f33-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)  
  
-   [<span data-ttu-id="a8f33-113">Procedura dettagliata: Debug di controlli di Windows Form personalizzati in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="a8f33-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
  
-   [<span data-ttu-id="a8f33-114">Procedura: Ereditare dalla classe Control</span><span class="sxs-lookup"><span data-stu-id="a8f33-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)  
  
-   [<span data-ttu-id="a8f33-115">Procedura: Testare il comportamento in fase di esecuzione di UserControl</span><span class="sxs-lookup"><span data-stu-id="a8f33-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
  
-   [<span data-ttu-id="a8f33-116">Procedura: Allineare un controllo ai bordi dei form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="a8f33-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
  
-   [<span data-ttu-id="a8f33-117">Procedura: Ereditare dalla classe UserControl</span><span class="sxs-lookup"><span data-stu-id="a8f33-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)  
  
-   [<span data-ttu-id="a8f33-118">Procedura: Creare controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="a8f33-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)  
  
-   [<span data-ttu-id="a8f33-119">Procedura: Modificare controlli compositi</span><span class="sxs-lookup"><span data-stu-id="a8f33-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)  
  
-   [<span data-ttu-id="a8f33-120">Procedura dettagliata: Modifica di un controllo composito con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8f33-120">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)  
  
-   [<span data-ttu-id="a8f33-121">Procedura dettagliata: Modifica di un controllo composito con VisualC#</span><span class="sxs-lookup"><span data-stu-id="a8f33-121">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
  
-   [<span data-ttu-id="a8f33-122">Procedura dettagliata: Eredità da un controllo di Windows Forms con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8f33-122">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
  
-   [<span data-ttu-id="a8f33-123">Procedura dettagliata: Creazione di un controllo di Windows Form che consente di sfruttare le funzionalità in fase di progettazione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a8f33-123">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)  
  
-   <span data-ttu-id="a8f33-124">[Procedura: Creare un controllo di Windows Form che sfrutta i vantaggi della funzionalità Design-Time](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a8f33-124">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f33-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8f33-125">See also</span></span>
- [<span data-ttu-id="a8f33-126">Procedura: Applicare attributi nei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a8f33-126">How to: Apply Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="a8f33-127">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a8f33-127">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="a8f33-128">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="a8f33-128">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
