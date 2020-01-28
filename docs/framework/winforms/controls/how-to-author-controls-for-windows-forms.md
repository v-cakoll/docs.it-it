---
title: 'Procedura: creare controlli'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 169104f51898f9bda08efa08685207e50406a7ff
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746711"
---
# <a name="how-to-author-controls-for-windows-forms"></a><span data-ttu-id="aa3e4-102">Procedura: creare controlli per Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aa3e4-102">How to: Author controls for Windows Forms</span></span>

<span data-ttu-id="aa3e4-103">Un controllo rappresenta un collegamento grafico tra l'utente e il programma.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-103">A control represents a graphical link between the user and the program.</span></span> <span data-ttu-id="aa3e4-104">Un controllo può fornire o elaborare dati, accettare input dall'utente, rispondere a eventi o eseguire qualsiasi numero di altre funzioni che connettono l'utente e l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-104">A control can provide or process data, accept user input, respond to events, or perform any number of other functions that connect the user and the application.</span></span> <span data-ttu-id="aa3e4-105">Poiché un controllo è essenzialmente un componente con un'interfaccia grafica, può essere utilizzato per le stesse funzioni di un componente oltre che per consentire l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-105">Because a control is essentially a component with a graphical interface, it can serve any function that a component does, as well as provide user interaction.</span></span> <span data-ttu-id="aa3e4-106">I controlli vengono creati per scopi specifici e la creazione di controlli è semplicemente un'altra attività di programmazione.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-106">Controls are created to serve specific purposes, and authoring controls is just another programming task.</span></span> <span data-ttu-id="aa3e4-107">Tenendo conto di questo, i passaggi seguenti rappresentano una panoramica del processo di creazione di un controllo.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-107">With that in mind, the following steps represent an overview of the control authoring process.</span></span> <span data-ttu-id="aa3e4-108">I collegamenti forniscono altre informazioni sui singoli passaggi.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-108">Links provide additional information on the individual steps.</span></span>

## <a name="to-author-a-control"></a><span data-ttu-id="aa3e4-109">Per creare un controllo</span><span class="sxs-lookup"><span data-stu-id="aa3e4-109">To author a control</span></span>

1. <span data-ttu-id="aa3e4-110">Determinare ciò il controllo dovrà fare o quale ruolo svolgerà nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-110">Determine what you want your control to accomplish, or what part it will play in your application.</span></span> <span data-ttu-id="aa3e4-111">I fattori da considerare sono:</span><span class="sxs-lookup"><span data-stu-id="aa3e4-111">Factors to consider are:</span></span>

    - <span data-ttu-id="aa3e4-112">Quale tipo di interfaccia grafica è necessario?</span><span class="sxs-lookup"><span data-stu-id="aa3e4-112">What kind of graphical interface do you need?</span></span>

    - <span data-ttu-id="aa3e4-113">Quali specifiche interazioni dell'utente saranno gestite da questo controllo?</span><span class="sxs-lookup"><span data-stu-id="aa3e4-113">What specific user interactions will this control handle?</span></span>

    - <span data-ttu-id="aa3e4-114">Le funzionalità necessarie sono fornite da ogni controllo esistente?</span><span class="sxs-lookup"><span data-stu-id="aa3e4-114">Is the functionality you need provided by any existing controls?</span></span>

    - <span data-ttu-id="aa3e4-115">È possibile ottenere le funzionalità richieste combinando diversi controlli Windows Form?</span><span class="sxs-lookup"><span data-stu-id="aa3e4-115">Can you get the functionality you need by combining several Windows Forms controls?</span></span>

2. <span data-ttu-id="aa3e4-116">Se è necessario un modello di oggetti per il controllo, stabilire come le funzionalità verranno distribuite nel modello di oggetti e suddividere le funzionalità tra il controllo e gli eventuali oggetti secondari.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-116">If you need an object model for your control, determine how functionality will be distributed throughout the object model, and divide up functionality between the control and any subobjects.</span></span> <span data-ttu-id="aa3e4-117">Un modello di oggetti può essere utile se si intende creare un controllo complesso o si desidera incorporare varie funzionalità.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-117">An object model may be useful if you are planning a complex control, or want to incorporate several functionalities.</span></span>

3. <span data-ttu-id="aa3e4-118">Determinare il tipo di controllo necessario (ad esempio controllo utente, controllo personalizzato, controllo Windows Form ereditato).</span><span class="sxs-lookup"><span data-stu-id="aa3e4-118">Determine the type of control (for example, user control, custom control, inherited Windows Forms control) you need.</span></span> <span data-ttu-id="aa3e4-119">Per informazioni dettagliate, vedere [Consigli sui tipi di controlli](control-type-recommendations.md) e [Tipi di controlli personalizzati](varieties-of-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="aa3e4-119">For details, see [Control Type Recommendations](control-type-recommendations.md) and [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>

4. <span data-ttu-id="aa3e4-120">Definire le funzionalità come proprietà, metodi ed eventi del controllo e i relativi oggetti secondari o strutture secondarie e assegnare i livelli di accesso appropriati (ad esempio pubblico, protetto e così via).</span><span class="sxs-lookup"><span data-stu-id="aa3e4-120">Express functionality as properties, methods, and events of the control and its subobjects or subsidiary structures, and assign appropriate access levels (for example, public, protected, and so on).</span></span>

5. <span data-ttu-id="aa3e4-121">Se è necessario un disegno personalizzato per il controllo, aggiungere codice per esso.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-121">If you need custom painting for your control, add code for it.</span></span> <span data-ttu-id="aa3e4-122">Per informazioni dettagliate, vedere [Disegno e rendering di controlli personalizzati](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="aa3e4-122">For details, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

6. <span data-ttu-id="aa3e4-123">Se il controllo eredita da <xref:System.Windows.Forms.UserControl>, è possibile verificarne il comportamento in fase di esecuzione compilando il progetto di controllo ed eseguendolo nel **contenitore di test UserControl**.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-123">If your control inherits from <xref:System.Windows.Forms.UserControl>, you can test its runtime behavior by building the control project and running it in the **UserControl Test Container**.</span></span> <span data-ttu-id="aa3e4-124">Per altre informazioni, vedere [Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="aa3e4-124">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

7. <span data-ttu-id="aa3e4-125">È possibile testare ed eseguire il debug del controllo anche creando un nuovo progetto, ad esempio un'applicazione Windows, e inserendolo in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-125">You can also test and debug your control by creating a new project, such as a Windows Application, and placing it into a container.</span></span> <span data-ttu-id="aa3e4-126">Questo processo viene illustrato come parte della [procedura dettagliata: creazione di un controllo composito](walkthrough-authoring-a-composite-control-with-visual-csharp.md).</span><span class="sxs-lookup"><span data-stu-id="aa3e4-126">This process is demonstrated as part of [Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md).</span></span>

8. <span data-ttu-id="aa3e4-127">Quando si aggiunge ogni funzionalità, aggiungere le funzionalità al progetto di test per verificarne il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-127">As you add each feature, add features to your test project to exercise the new functionality.</span></span>

9. <span data-ttu-id="aa3e4-128">Ripetere l'operazione, ottimizzando la struttura.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-128">Repeat, refining the design.</span></span>

10. <span data-ttu-id="aa3e4-129">Creare il pacchetto e distribuire il controllo.</span><span class="sxs-lookup"><span data-stu-id="aa3e4-129">Package and deploy your control.</span></span> <span data-ttu-id="aa3e4-130">Per informazioni dettagliate, vedere la pagina relativa [alla prima occhiata alla distribuzione in Visual Studio](/visualstudio/deployment/deploying-applications-services-and-components).</span><span class="sxs-lookup"><span data-stu-id="aa3e4-130">For details, see [First look at deployment in Visual Studio](/visualstudio/deployment/deploying-applications-services-and-components).</span></span>

## <a name="see-also"></a><span data-ttu-id="aa3e4-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa3e4-131">See also</span></span>

- [<span data-ttu-id="aa3e4-132">Procedura: Ereditare dalla classe UserControl</span><span class="sxs-lookup"><span data-stu-id="aa3e4-132">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="aa3e4-133">Procedura: Ereditare dalla classe Control</span><span class="sxs-lookup"><span data-stu-id="aa3e4-133">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="aa3e4-134">Procedura: Ereditare da controlli Windows Form esistenti</span><span class="sxs-lookup"><span data-stu-id="aa3e4-134">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="aa3e4-135">Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl</span><span class="sxs-lookup"><span data-stu-id="aa3e4-135">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [<span data-ttu-id="aa3e4-136">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="aa3e4-136">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
