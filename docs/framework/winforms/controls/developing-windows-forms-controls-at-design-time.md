---
title: Sviluppo di controlli Windows Form in fase di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1eebca72b8c564e6d846eba69b6b59139754738e
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015985"
---
# <a name="develop-windows-forms-controls-at-design-time"></a><span data-ttu-id="c21cc-102">Sviluppare controlli Windows Forms in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="c21cc-102">Develop Windows Forms controls at design time</span></span>

<span data-ttu-id="c21cc-103">.NET Framework offre agli autori di controlli numerose tecnologie di creazione dei controlli.</span><span class="sxs-lookup"><span data-stu-id="c21cc-103">For control authors, the .NET Framework provides a wealth of control authoring technology.</span></span> <span data-ttu-id="c21cc-104">Gli autori non devono più limitarsi alla progettazione di controlli compositi che fungono da raccolta dei controlli preesistenti.</span><span class="sxs-lookup"><span data-stu-id="c21cc-104">Authors are no longer limited to designing composite controls that act as a collection of preexisting controls.</span></span> <span data-ttu-id="c21cc-105">Grazie all'ereditarietà, è possibile creare i propri controlli da controlli compositi preesistenti o da controlli Windows Form preesistenti.</span><span class="sxs-lookup"><span data-stu-id="c21cc-105">Through inheritance, you can create your own controls from preexisting composite controls or preexisting Windows Forms controls.</span></span> <span data-ttu-id="c21cc-106">È anche possibile progettare propri controlli che implementano il disegno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c21cc-106">You can also design your own controls that implement custom painting.</span></span> <span data-ttu-id="c21cc-107">Queste opzioni offrono una grande flessibilità per la progettazione e la funzionalità dell'interfaccia visiva.</span><span class="sxs-lookup"><span data-stu-id="c21cc-107">These options enable a great deal of flexibility to the design and functionality of the visual interface.</span></span> <span data-ttu-id="c21cc-108">Per sfruttare queste funzionalità, è preferibile avere familiarità con i concetti della programmazione basata su oggetti.</span><span class="sxs-lookup"><span data-stu-id="c21cc-108">To take advantage of these features, you should be familiar with object-based programming concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="c21cc-109">Non è necessario avere una conoscenza approfondita dell'ereditarietà, ma può essere utile fare riferimento a [nozioni fondamentali sull'ereditarietà (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="c21cc-109">It is not necessary to have a thorough understanding of inheritance, but you may find it useful to refer to [Inheritance basics (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>

<span data-ttu-id="c21cc-110">Per creare controlli personalizzati da usare nei Web Form, vedere [Sviluppo di controlli server ASP.NET personalizzati](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c21cc-110">If you want to create custom controls to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c21cc-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c21cc-111">In this section</span></span>

<span data-ttu-id="c21cc-112">[Procedura dettagliata: Creazione di un controllo composito](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-112">[Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="c21cc-113">Illustra come creare un controllo composito semplice in C#.</span><span class="sxs-lookup"><span data-stu-id="c21cc-113">Shows how to create a simple composite control in C#.</span></span>

<span data-ttu-id="c21cc-114">[Procedura dettagliata: Eredità da un controllo Windows Forms](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-114">[Walkthrough: Inheriting from a Windows Forms Control](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="c21cc-115">Illustra come creare un controllo Windows Form semplice usando l'ereditarietà in C#.</span><span class="sxs-lookup"><span data-stu-id="c21cc-115">Shows how to create a simple Windows Forms control using inheritance in C#.</span></span>

<span data-ttu-id="c21cc-116">[Procedura dettagliata: Esecuzione di attività comuni tramite smart tag sui controlli Windows Forms](performing-common-tasks-using-smart-tags-on-wf-controls.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-116">[Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](performing-common-tasks-using-smart-tags-on-wf-controls.md)</span></span>\
<span data-ttu-id="c21cc-117">Illustra come usare la funzionalità di smart tag nei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c21cc-117">Shows how to use the smart tag feature on Windows Forms controls.</span></span>

<span data-ttu-id="c21cc-118">[Procedura dettagliata: Serializzazione di raccolte di tipi standard con DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-118">[Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)</span></span>\
<span data-ttu-id="c21cc-119">Viene illustrato come utilizzare l' <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attributo per serializzare una raccolta.</span><span class="sxs-lookup"><span data-stu-id="c21cc-119">Shows how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attribute to serialize a collection.</span></span>

<span data-ttu-id="c21cc-120">[Procedura dettagliata: Debug di controlli di Windows Forms personalizzati in fase di progettazione](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-120">[Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span></span>\
<span data-ttu-id="c21cc-121">Illustra come eseguire il debug del comportamento in fase di progettazione di un controllo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c21cc-121">Shows how to debug the design-time behavior of a Windows Forms control.</span></span>

<span data-ttu-id="c21cc-122">[Procedura dettagliata: Creazione di un controllo Windows Forms che sfrutta le funzionalità della fase di progettazione di Visual Studio](creating-a-wf-control-design-time-features.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-122">[Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md)</span></span>\
<span data-ttu-id="c21cc-123">Illustra come integrare profondamente un controllo composito nell'ambiente di progettazione.</span><span class="sxs-lookup"><span data-stu-id="c21cc-123">Shows how to tightly integrate a composite control into the design environment.</span></span>

<span data-ttu-id="c21cc-124">[Procedura: Controlli autore per Windows Forms](how-to-author-controls-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-124">[How to: Author Controls for Windows Forms](how-to-author-controls-for-windows-forms.md)</span></span>\
<span data-ttu-id="c21cc-125">Offre una serie di considerazioni sull'implementazione di un controllo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c21cc-125">Provides an overview of considerations for implementing a Windows Forms control.</span></span>

<span data-ttu-id="c21cc-126">[Procedura: Crea controlli compositi](how-to-author-composite-controls.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-126">[How to: Author Composite Controls](how-to-author-composite-controls.md)</span></span>\
<span data-ttu-id="c21cc-127">Illustra come creare un controllo ereditando da un controllo composito.</span><span class="sxs-lookup"><span data-stu-id="c21cc-127">Shows how to create a control by inheriting from a composite control.</span></span>

<span data-ttu-id="c21cc-128">[Procedura: Ereditare dalla classe UserControl](how-to-inherit-from-the-usercontrol-class.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-128">[How to: Inherit from the UserControl Class](how-to-inherit-from-the-usercontrol-class.md)</span></span>\
<span data-ttu-id="c21cc-129">Offre una panoramica della procedura di creazione di un controllo composito.</span><span class="sxs-lookup"><span data-stu-id="c21cc-129">Provides an overview of the procedure for creating a composite control.</span></span>

<span data-ttu-id="c21cc-130">[Procedura: Ereditare da controlli Windows Forms esistenti](how-to-inherit-from-existing-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-130">[How to: Inherit from Existing Windows Forms Controls](how-to-inherit-from-existing-windows-forms-controls.md)</span></span>\
<span data-ttu-id="c21cc-131">Viene illustrato come creare un controllo esteso ereditando dalla classe del <xref:System.Windows.Forms.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="c21cc-131">Shows how to create an extended control by inheriting from the <xref:System.Windows.Forms.Button> control class.</span></span>

<span data-ttu-id="c21cc-132">[Procedura: Ereditare dalla classe Control](how-to-inherit-from-the-control-class.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-132">[How to: Inherit from the Control Class](how-to-inherit-from-the-control-class.md)</span></span>\
<span data-ttu-id="c21cc-133">Offre una panoramica della creazione di un controllo esteso.</span><span class="sxs-lookup"><span data-stu-id="c21cc-133">Provides an overview of creating an extended control.</span></span>

<span data-ttu-id="c21cc-134">[Procedura: Allineare un controllo ai bordi dei form in fase di progettazione](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-134">[How to: Align a Control to the Edges of Forms at Design Time](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span></span>\
<span data-ttu-id="c21cc-135">Viene illustrato come utilizzare la <xref:System.Windows.Forms.Control.Dock%2A> proprietà per allineare il controllo al bordo del form che occupa.</span><span class="sxs-lookup"><span data-stu-id="c21cc-135">Shows how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="c21cc-136">[Procedura: Visualizza un controllo nella finestra di dialogo Scegli elementi della casella degli strumenti](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-136">[How to: Display a Control in the Choose Toolbox Items Dialog Box](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span></span>\
<span data-ttu-id="c21cc-137">Illustra la procedura di installazione del controllo in modo che venga visualizzato nella finestra di dialogo **Customize Toolbox** (Personalizza casella degli strumenti).</span><span class="sxs-lookup"><span data-stu-id="c21cc-137">Shows the procedure for installing your control so that it appears in the **Customize Toolbox** dialog box.</span></span>

<span data-ttu-id="c21cc-138">[Procedura: Specificare una bitmap della casella degli strumenti per un controllo](how-to-provide-a-toolbox-bitmap-for-a-control.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-138">[How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md)</span></span>\
<span data-ttu-id="c21cc-139">Viene illustrato come utilizzare <xref:System.Drawing.ToolboxBitmapAttribute> per visualizzare un'icona accanto al controllo personalizzato nella **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="c21cc-139">Shows how to use the <xref:System.Drawing.ToolboxBitmapAttribute> to display an icon next to your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="c21cc-140">[Procedura: Testare il comportamento in fase di esecuzione di un UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-140">[How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span></span>\
<span data-ttu-id="c21cc-141">Illustra come usare **UserControl Test Container** per testare il comportamento di un controllo composito.</span><span class="sxs-lookup"><span data-stu-id="c21cc-141">Shows how to use the **UserControl Test Container** to test the behavior of a composite control.</span></span>

<span data-ttu-id="c21cc-142">[Errori in fase di progettazione in Progettazione Windows Form](design-time-errors-in-the-windows-forms-designer.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-142">[Design-Time Errors in the Windows Forms Designer](design-time-errors-in-the-windows-forms-designer.md)</span></span>\
<span data-ttu-id="c21cc-143">Illustra il significato e l'uso dell'elenco errori della fase di progettazione visualizzato in Microsoft Visual Studio quando il caricamento di Progettazione Windows Form non riesce.</span><span class="sxs-lookup"><span data-stu-id="c21cc-143">Explains the meaning and use of the Design-Time Error List that appears in Microsoft Visual Studio when the Windows Forms designer fails to load.</span></span>

<span data-ttu-id="c21cc-144">[Risoluzione dei problemi relativi alla modifica di controlli e componenti](troubleshooting-control-and-component-authoring.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-144">[Troubleshooting Control and Component Authoring](troubleshooting-control-and-component-authoring.md)</span></span>\
<span data-ttu-id="c21cc-145">Illustra come diagnosticare e correggere gli errori comuni che possono verificarsi quando si crea un componente o un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c21cc-145">Shows how to diagnose and fix common issues that can occur when you author a custom component or control.</span></span>

## <a name="reference"></a><span data-ttu-id="c21cc-146">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="c21cc-146">Reference</span></span>

- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>

- <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>

## <a name="related-sections"></a><span data-ttu-id="c21cc-147">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c21cc-147">Related sections</span></span>

<span data-ttu-id="c21cc-148">[Sviluppo di controlli Windows Forms personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-148">[Developing Custom Windows Forms Controls with the .NET Framework](developing-custom-windows-forms-controls.md)</span></span>\
<span data-ttu-id="c21cc-149">Illustra come creare i controlli personalizzati con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c21cc-149">Discusses how to create your own custom controls with the .NET Framework.</span></span>

<span data-ttu-id="c21cc-150">[Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-150">[Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md)</span></span>\
<span data-ttu-id="c21cc-151">Introduce Common Language Runtime, progettato per semplificare la creazione e l'uso dei componenti.</span><span class="sxs-lookup"><span data-stu-id="c21cc-151">Introduces the common language runtime, which is designed to simplify the creation and use of components.</span></span> <span data-ttu-id="c21cc-152">Un aspetto importante di questa semplificazione è la migliore interoperabilità tra componenti scritti usando linguaggi di programmazione diversi.</span><span class="sxs-lookup"><span data-stu-id="c21cc-152">An important aspect of this simplification is enhanced interoperability between components written using different programming languages.</span></span> <span data-ttu-id="c21cc-153">Common Language Specification (CLS) consente di creare strumenti e componenti che usano più linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="c21cc-153">The Common Language Specification (CLS) makes it possible to create tools and components that work with multiple programming languages.</span></span>

<span data-ttu-id="c21cc-154">[Procedura dettagliata: Popolamento automatico della casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span><span class="sxs-lookup"><span data-stu-id="c21cc-154">[Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span></span>\
<span data-ttu-id="c21cc-155">Descrive come abilitare la visualizzazione dei componenti o dei controlli nella finestra di dialogo **Customize Toolbox** (Personalizza casella degli strumenti).</span><span class="sxs-lookup"><span data-stu-id="c21cc-155">Describes how to enable your component or control to be displayed in the **Customize Toolbox** dialog box.</span></span>
