---
title: Disegno e rendering di controlli personalizzati
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: 18a05a739f42d41a650e66723f44aae69c1707c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526051"
---
# <a name="custom-control-painting-and-rendering"></a><span data-ttu-id="0df6d-102">Disegno e rendering di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="0df6d-102">Custom Control Painting and Rendering</span></span>
<span data-ttu-id="0df6d-103">Disegno personalizzato di controlli è una delle molte attività complesse semplificata da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0df6d-103">Custom painting of controls is one of the many complicated tasks made easy by the .NET Framework.</span></span> <span data-ttu-id="0df6d-104">Durante la creazione di un controllo personalizzato, sono disponibili molte opzioni riguardanti l'aspetto grafico.</span><span class="sxs-lookup"><span data-stu-id="0df6d-104">When authoring a custom control, you have many options regarding your control's graphical appearance.</span></span> <span data-ttu-id="0df6d-105">Se si sta creando un controllo da cui eredita il `Control`, è necessario fornire codice che consente la rappresentazione grafica di eseguire il rendering del controllo.</span><span class="sxs-lookup"><span data-stu-id="0df6d-105">If you are authoring a control that inherits from the `Control`, you must provide code that allows your control to render its graphical representation.</span></span> <span data-ttu-id="0df6d-106">Se si sta creando un controllo utente ereditando dalla classe di `UserControl`, o da uno dei controlli Windows Form, è possibile eseguire l'override della rappresentazione grafica standard e fornire il proprio codice di grafica.</span><span class="sxs-lookup"><span data-stu-id="0df6d-106">If you are creating a user control by inheriting from the `UserControl`, or are inheriting from one of the Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span> <span data-ttu-id="0df6d-107">Se si desidera fornire per il rendering personalizzate per i controlli costitutivi di un `UserControl` si esegue la creazione, le opzioni sono più limitate, ma consentono ancora un'ampia gamma di possibilità grafiche per i controlli e le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0df6d-107">If you want to provide custom rendering for the constituent controls of a `UserControl` you are authoring, your options become more limited, but still allow a wide range of graphical possibilities for your controls and applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0df6d-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="0df6d-108">In This Section</span></span>  
 [<span data-ttu-id="0df6d-109">Rendering di un controllo di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0df6d-109">Rendering a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 <span data-ttu-id="0df6d-110">Viene illustrato come programmare la logica che viene visualizzato un controllo.</span><span class="sxs-lookup"><span data-stu-id="0df6d-110">Shows how to program the logic that displays a control.</span></span>  
  
 [<span data-ttu-id="0df6d-111">Controlli creati dall'utente</span><span class="sxs-lookup"><span data-stu-id="0df6d-111">User-Drawn Controls</span></span>](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 <span data-ttu-id="0df6d-112">Fornisce una panoramica dei passaggi necessari per la scrittura e si esegue l'override per il controllo del codice di rendering.</span><span class="sxs-lookup"><span data-stu-id="0df6d-112">Gives an overview of the steps involved in writing and overriding rendering code for your control.</span></span>  
  
 [<span data-ttu-id="0df6d-113">Controlli costitutivi</span><span class="sxs-lookup"><span data-stu-id="0df6d-113">Constituent Controls</span></span>](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 <span data-ttu-id="0df6d-114">Viene descritto come implementare il codice per il rendering personalizzate per i controlli che costituiscono il form e controlli utente.</span><span class="sxs-lookup"><span data-stu-id="0df6d-114">Describes how to implement custom rendering code for constituent controls in your user controls and forms.</span></span>  
  
 [<span data-ttu-id="0df6d-115">Procedura: Rendere invisibile il controllo in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="0df6d-115">How to: Make Your Control Invisible at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 <span data-ttu-id="0df6d-116">Viene illustrato come utilizzare il <xref:System.Windows.Forms.Control.Visible%2A> proprietà per nascondere e mostrare un controllo.</span><span class="sxs-lookup"><span data-stu-id="0df6d-116">Shows how to use the <xref:System.Windows.Forms.Control.Visible%2A> property to hide and show a control.</span></span>  
  
 [<span data-ttu-id="0df6d-117">Procedura: Assegnare uno sfondo trasparente al controllo</span><span class="sxs-lookup"><span data-stu-id="0df6d-117">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 <span data-ttu-id="0df6d-118">Viene illustrato come utilizzare il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo per creare un colore di sfondo opaco, trasparente o semitrasparente.</span><span class="sxs-lookup"><span data-stu-id="0df6d-118">Shows how to use the <xref:System.Windows.Forms.Control.SetStyle%2A> method to create a background color that is opaque, transparent, or partially transparent.</span></span>  
  
 [<span data-ttu-id="0df6d-119">Rendering dei controlli con stili visivi</span><span class="sxs-lookup"><span data-stu-id="0df6d-119">Rendering Controls with Visual Styles</span></span>](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 <span data-ttu-id="0df6d-120">Viene illustrato come eseguire il rendering di controlli con stili visivi nei sistemi operativi che li supportano.</span><span class="sxs-lookup"><span data-stu-id="0df6d-120">Shows how to render controls using visual styles in operating systems that support them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0df6d-121">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="0df6d-121">Reference</span></span>  
 <xref:System.Windows.Forms.Control>  
 <span data-ttu-id="0df6d-122">Descrive la classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="0df6d-122">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="0df6d-123">Descrive la classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="0df6d-123">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <span data-ttu-id="0df6d-124">Viene descritto il metodo.</span><span class="sxs-lookup"><span data-stu-id="0df6d-124">Describes this method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0df6d-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0df6d-125">Related Sections</span></span>  
 [<span data-ttu-id="0df6d-126">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="0df6d-126">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 <span data-ttu-id="0df6d-127">Introduce [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funzionalità grafica da una prospettiva e fornisce i collegamenti di Visual Studio per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="0df6d-127">Introduces [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] graphics functionality from a Visual Studio perspective and gives links to more information.</span></span>  
  
 [<span data-ttu-id="0df6d-128">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="0df6d-128">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 <span data-ttu-id="0df6d-129">Descrive i tipi di controlli personalizzati, che è possibile creare.</span><span class="sxs-lookup"><span data-stu-id="0df6d-129">Describes the kinds of custom controls you can author.</span></span>
