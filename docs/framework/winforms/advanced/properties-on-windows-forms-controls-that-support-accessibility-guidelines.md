---
title: "Proprietà nei controlli Windows Form che supportano le linee guida per l'accesso facilitato"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ca18b35b90b028054e68a0a14fecc819a6c20b9
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="d9e6d-102">Proprietà nei controlli Windows Form che supportano le linee guida per l'accesso facilitato</span><span class="sxs-lookup"><span data-stu-id="d9e6d-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="d9e6d-103">Controlli della casella degli strumenti standard di Windows Form supportano molte delle linee guida di accessibilità, inclusi l'esposizione dello stato attivo e l'esposizione di elementi dello schermo.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="d9e6d-104">Pianificazione dell'accesso facilitato</span><span class="sxs-lookup"><span data-stu-id="d9e6d-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="d9e6d-105">Proprietà dei controlli è utilizzabile per supportare altre linee guida di accessibilità, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="d9e6d-106">Inoltre, utilizzare i menu per fornire accesso alle funzionalità del programma.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="d9e6d-107">Proprietà del controllo</span><span class="sxs-lookup"><span data-stu-id="d9e6d-107">Control Property</span></span>|<span data-ttu-id="d9e6d-108">Considerazioni per l'accessibilità</span><span class="sxs-lookup"><span data-stu-id="d9e6d-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="d9e6d-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="d9e6d-109">AccessibleDescription</span></span>|<span data-ttu-id="d9e6d-110">La descrizione viene segnalata agli strumenti di accessibilità, ad esempio gli screen reader.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="d9e6d-111">Gli strumenti per l'accessibilità sono dispositivi e programmi specializzati che consentono agli utenti con disabilità di usare i computer in modo più efficace.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="d9e6d-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="d9e6d-112">AccessibleName</span></span>|<span data-ttu-id="d9e6d-113">Il nome che verrà segnalato agli strumenti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="d9e6d-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="d9e6d-114">AccessibleRole</span></span>|<span data-ttu-id="d9e6d-115">Viene descritto l'utilizzo dell'elemento nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="d9e6d-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="d9e6d-116">TabIndex</span></span>|<span data-ttu-id="d9e6d-117">Crea un percorso di navigazione sensibile nel form.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="d9e6d-118">È importante per i controlli senza etichette intrinseche, ad esempio caselle di testo che precede nell'ordine di tabulazione all'etichetta associata.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="d9e6d-119">Testo</span><span class="sxs-lookup"><span data-stu-id="d9e6d-119">Text</span></span>|<span data-ttu-id="d9e6d-120">Usare il carattere "&" per creare le chiavi di accesso.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="d9e6d-121">Utilizzando i tasti di scelta fa parte di accesso da tastiera documentato alle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="d9e6d-122">Dimensione carattere</span><span class="sxs-lookup"><span data-stu-id="d9e6d-122">Font Size</span></span>|<span data-ttu-id="d9e6d-123">Se le dimensioni del carattere non sono regolabile, quindi deve essere impostato su 10 punti o superiori.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="d9e6d-124">Dopo aver impostata la dimensione dello stesso tipo di carattere, tutti i controlli aggiunti in seguito al form avranno le stesse dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="d9e6d-125">Forecolor</span><span class="sxs-lookup"><span data-stu-id="d9e6d-125">Forecolor</span></span>|<span data-ttu-id="d9e6d-126">Se questa proprietà è impostata sul valore predefinito, le preferenze dell'utente colore verranno usate nel form.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="d9e6d-127">Backcolor</span><span class="sxs-lookup"><span data-stu-id="d9e6d-127">Backcolor</span></span>|<span data-ttu-id="d9e6d-128">Se questa proprietà è impostata sul valore predefinito, le preferenze dell'utente colore verranno usate nel form.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="d9e6d-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="d9e6d-129">BackgroundImage</span></span>|<span data-ttu-id="d9e6d-130">Omettere questa proprietà per rendere più leggibile il testo.</span><span class="sxs-lookup"><span data-stu-id="d9e6d-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9e6d-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9e6d-131">See Also</span></span>  
 [<span data-ttu-id="d9e6d-132">Procedura dettagliata: Creazione di un'applicazione Windows ad Accesso facilitato</span><span class="sxs-lookup"><span data-stu-id="d9e6d-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)
