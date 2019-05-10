---
title: Sviluppo di un controllo Windows Form composto
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: 2d6220a95d20cc0ab8ea1cdeb396804dfbcef8a1
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211483"
---
# <a name="develop-a-composite-windows-forms-control"></a><span data-ttu-id="0558d-102">Sviluppare un controllo Windows Forms composito</span><span class="sxs-lookup"><span data-stu-id="0558d-102">Develop a composite Windows Forms control</span></span>

<span data-ttu-id="0558d-103">È possibile sviluppare un controllo Windows Form composito combinando altri controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="0558d-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="0558d-104">I controlli compositi che derivano da <xref:System.Web.UI.UserControl> sono denominati controlli utente.</span><span class="sxs-lookup"><span data-stu-id="0558d-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="0558d-105">La classe base, <xref:System.Windows.Forms.UserControl>, fornisce il routing della tastiera per i controlli figlio, garantendo così che i controlli figlio possano ricevere lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0558d-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="0558d-106">Per un esempio di un controllo utente, vedere la <xref:System.Windows.Forms.UserControl> esempio in [come: Applicare attributi nei controlli di Windows Form](how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="0558d-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>

<span data-ttu-id="0558d-107">Progettazione Windows Form in Visual Studio offre supporto avanzato in fase di progettazione per la creazione di controlli utente.</span><span class="sxs-lookup"><span data-stu-id="0558d-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>

- [<span data-ttu-id="0558d-108">Procedura: Visualizzare un controllo nella finestra di dialogo elementi della casella degli strumenti scegliere</span><span class="sxs-lookup"><span data-stu-id="0558d-108">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)

- [<span data-ttu-id="0558d-109">Procedura dettagliata: Serializzazione di raccolte di tipi Standard tramite DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="0558d-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)

- [<span data-ttu-id="0558d-110">Procedura dettagliata: Eredità da un controllo di Windows Forms con VisualC#</span><span class="sxs-lookup"><span data-stu-id="0558d-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

- [<span data-ttu-id="0558d-111">Procedura: Specificare una Bitmap nella casella degli strumenti per un controllo</span><span class="sxs-lookup"><span data-stu-id="0558d-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)

- [<span data-ttu-id="0558d-112">Procedura: Ereditare da esistenti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0558d-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)

- [<span data-ttu-id="0558d-113">Procedura dettagliata: Debug di controlli di Windows Form personalizzati in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="0558d-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

- [<span data-ttu-id="0558d-114">Procedura: Ereditare dalla classe Control</span><span class="sxs-lookup"><span data-stu-id="0558d-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)

- [<span data-ttu-id="0558d-115">Procedura: Testare il comportamento in fase di esecuzione di UserControl</span><span class="sxs-lookup"><span data-stu-id="0558d-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

- [<span data-ttu-id="0558d-116">Procedura: Allineare un controllo ai bordi dei form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="0558d-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)

- [<span data-ttu-id="0558d-117">Procedura: Ereditare dalla classe UserControl</span><span class="sxs-lookup"><span data-stu-id="0558d-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)

- [<span data-ttu-id="0558d-118">Procedura: Creare controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="0558d-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)

- [<span data-ttu-id="0558d-119">Procedura: Modificare controlli compositi</span><span class="sxs-lookup"><span data-stu-id="0558d-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)

- [<span data-ttu-id="0558d-120">Procedura dettagliata: Modifica di un controllo composito con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0558d-120">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)

- [<span data-ttu-id="0558d-121">Procedura dettagliata: Modifica di un controllo composito con VisualC#</span><span class="sxs-lookup"><span data-stu-id="0558d-121">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)

- [<span data-ttu-id="0558d-122">Procedura dettagliata: Eredità da un controllo di Windows Forms con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0558d-122">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)

- [<span data-ttu-id="0558d-123">Procedura dettagliata: Creazione di un controllo di Windows Form che consente di sfruttare le funzionalità in fase di progettazione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0558d-123">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

- <span data-ttu-id="0558d-124">[Procedura: Creare un controllo di Windows Form che sfrutta i vantaggi della funzionalità Design-Time](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="0558d-124">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>

## <a name="see-also"></a><span data-ttu-id="0558d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0558d-125">See also</span></span>

- [<span data-ttu-id="0558d-126">Procedura: Applicare attributi nei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0558d-126">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="0558d-127">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0558d-127">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="0558d-128">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="0558d-128">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
