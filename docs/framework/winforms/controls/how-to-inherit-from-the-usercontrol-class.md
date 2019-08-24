---
title: 'Procedura: Ereditare dalla classe UserControl'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7f4055c2374103b7df941d9a9bef24ed5e6cb27c
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015834"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a><span data-ttu-id="15d64-102">Procedura: Ereditare dalla classe UserControl</span><span class="sxs-lookup"><span data-stu-id="15d64-102">How to: Inherit from the UserControl Class</span></span>

<span data-ttu-id="15d64-103">Per combinare le funzionalità di uno o più controlli Windows Form con il codice personalizzato, è possibile creare un *controllo utente*.</span><span class="sxs-lookup"><span data-stu-id="15d64-103">To combine the functionality of one or more Windows Forms controls with custom code, you can create a *user control*.</span></span> <span data-ttu-id="15d64-104">I controlli utente combinano lo sviluppo rapido del controllo, la funzionalità del controllo standard di Windows Forms e la versatilità di proprietà e metodi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="15d64-104">User controls combine rapid control development, standard Windows Forms control functionality, and the versatility of custom properties and methods.</span></span> <span data-ttu-id="15d64-105">Quando si inizia con la creazione di un controllo utente, viene visualizzata una finestra di progettazione in cui è possibile inserire controlli Windows Forms standard.</span><span class="sxs-lookup"><span data-stu-id="15d64-105">When you begin creating a user control, you are presented with a visible designer, upon which you can place standard Windows Forms controls.</span></span> <span data-ttu-id="15d64-106">Questi controlli mantengono tutte le funzionalità intrinseche, nonché l'aspetto e il comportamento dei controlli standard.</span><span class="sxs-lookup"><span data-stu-id="15d64-106">These controls retain all of their inherent functionality, as well as the appearance and behavior (look and feel) of standard controls.</span></span> <span data-ttu-id="15d64-107">Una volta che questi controlli sono incorporati nel controllo utente, tuttavia, non sono più disponibili tramite codice.</span><span class="sxs-lookup"><span data-stu-id="15d64-107">Once these controls are built into the user control, however, they are no longer available to you through code.</span></span> <span data-ttu-id="15d64-108">Il controllo utente esegue il proprio disegno e gestisce anche tutte le funzionalità di base associate ai controlli.</span><span class="sxs-lookup"><span data-stu-id="15d64-108">The user control does its own painting and also handles all of the basic functionality associated with controls.</span></span>

## <a name="to-create-a-user-control"></a><span data-ttu-id="15d64-109">Per creare un controllo utente</span><span class="sxs-lookup"><span data-stu-id="15d64-109">To create a user control</span></span>

1. <span data-ttu-id="15d64-110">Creare un nuovo progetto di **libreria di controlli Windows** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="15d64-110">Create a new **Windows Control Library** project in Visual Studio.</span></span>

   <span data-ttu-id="15d64-111">Viene creato un nuovo progetto con un controllo utente vuoto.</span><span class="sxs-lookup"><span data-stu-id="15d64-111">A new project is created with a blank user control.</span></span>

2. <span data-ttu-id="15d64-112">Trascinare i controlli dalla scheda **Windows Forms** della **Casella degli strumenti** nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="15d64-112">Drag controls from the **Windows Forms** tab of the **Toolbox** onto your designer.</span></span>

3. <span data-ttu-id="15d64-113">Questi controlli devono essere posizionati e progettati come si desidera che vengano visualizzati nel controllo utente finale.</span><span class="sxs-lookup"><span data-stu-id="15d64-113">These controls should be positioned and designed as you want them to appear in the final user control.</span></span> <span data-ttu-id="15d64-114">Se si desidera consentire agli sviluppatori di accedere ai controlli costitutivi, è necessario dichiararli come public o esporre in modo selettivo le proprietà del controllo che li costituiscono.</span><span class="sxs-lookup"><span data-stu-id="15d64-114">If you want to allow developers to access the constituent controls, you must declare them as public, or selectively expose properties of the constituent control.</span></span> <span data-ttu-id="15d64-115">Per informazioni dettagliate, vedere [Procedura: Esporre le proprietà dei controlli](how-to-expose-properties-of-constituent-controls.md)costitutivi.</span><span class="sxs-lookup"><span data-stu-id="15d64-115">For details, see [How to: Expose Properties of Constituent Controls](how-to-expose-properties-of-constituent-controls.md).</span></span>

4. <span data-ttu-id="15d64-116">Implementare eventuali metodi o proprietà personalizzati da incorporare nel controllo.</span><span class="sxs-lookup"><span data-stu-id="15d64-116">Implement any custom methods or properties that your control will incorporate.</span></span>

5. <span data-ttu-id="15d64-117">Premere **F5** per compilare il progetto ed eseguire il controllo in **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="15d64-117">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="15d64-118">Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)UserControl.</span><span class="sxs-lookup"><span data-stu-id="15d64-118">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="15d64-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15d64-119">See also</span></span>

- [<span data-ttu-id="15d64-120">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="15d64-120">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="15d64-121">Procedura: Ereditare dalla classe Control</span><span class="sxs-lookup"><span data-stu-id="15d64-121">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="15d64-122">Procedura: Ereditare da controlli Windows Forms esistenti</span><span class="sxs-lookup"><span data-stu-id="15d64-122">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="15d64-123">Procedura: Controlli autore per Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15d64-123">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="15d64-124">Risolvere i problemi relativi ai gestori eventi ereditati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15d64-124">Troubleshoot Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="15d64-125">Procedura: Testare il comportamento in fase di esecuzione di un UserControl</span><span class="sxs-lookup"><span data-stu-id="15d64-125">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
