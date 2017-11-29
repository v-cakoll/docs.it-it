---
title: Componente BackgroundWorker
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: bef7b0ab-ce57-475a-a2d6-fb8a702a9417
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cbcbc786c19ad1af74114915b0fd0689d466fcbe
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="backgroundworker-component"></a><span data-ttu-id="919e6-102">Componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="919e6-102">BackgroundWorker Component</span></span>
<span data-ttu-id="919e6-103">Il `BackgroundWorker` componente consente a un form o controllo per eseguire un'operazione in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="919e6-103">The `BackgroundWorker` component enables your form or control to run an operation asynchronously.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="919e6-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="919e6-104">In This Section</span></span>  
 [<span data-ttu-id="919e6-105">Panoramica sul componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="919e6-105">BackgroundWorker Component Overview</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <span data-ttu-id="919e6-106">Viene descritto il `BackgroundWorker` componente, che offre la possibilità di eseguire operazioni lunghe ed elaborate in modo asincrono (in background"), su un thread diverso dal thread dell'interfaccia utente principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="919e6-106">Describes the `BackgroundWorker` component, which gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span>  
  
 [<span data-ttu-id="919e6-107">Procedura dettagliata: Esecuzione di un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="919e6-107">Walkthrough: Running an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 <span data-ttu-id="919e6-108">Viene illustrato come utilizzare il `BackgroundWorker` componente nella finestra di progettazione per eseguire un'operazione richiede molto tempo su un thread separato.</span><span class="sxs-lookup"><span data-stu-id="919e6-108">Demonstrates how to use the `BackgroundWorker` component in the designer to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="919e6-109">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="919e6-109">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="919e6-110">Viene illustrato come utilizzare il `BackgroundWorker` componente per l'esecuzione di un'operazione richiede molto tempo su un thread separato.</span><span class="sxs-lookup"><span data-stu-id="919e6-110">Demonstrates how to use the `BackgroundWorker` component to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="919e6-111">Procedura dettagliata: Implementazione di un form che usa un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="919e6-111">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="919e6-112">Crea un'applicazione utilizzando la finestra di progettazione che esegue calcoli matematici in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="919e6-112">Creates an application using the designer that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="919e6-113">Procedura: Implementare un form che esegue un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="919e6-113">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="919e6-114">Crea un'applicazione che esegue calcoli matematici in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="919e6-114">Creates an application that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="919e6-115">Procedura: Scaricare file in background</span><span class="sxs-lookup"><span data-stu-id="919e6-115">How to: Download a File in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 <span data-ttu-id="919e6-116">Viene illustrato come utilizzare il `BackgroundWorker` componente per scaricare un file in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="919e6-116">Demonstrates how to use the `BackgroundWorker` component to download a file on a separate thread.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="919e6-117">Riferimento</span><span class="sxs-lookup"><span data-stu-id="919e6-117">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="919e6-118">Descrive la classe e fornisce i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="919e6-118">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 <span data-ttu-id="919e6-119">Descrive il tipo che contiene i dati per il <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> evento.</span><span class="sxs-lookup"><span data-stu-id="919e6-119">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <span data-ttu-id="919e6-120">Descrive il tipo che contiene i dati per il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="919e6-120">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="919e6-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="919e6-121">Related Sections</span></span>  
 [<span data-ttu-id="919e6-122">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="919e6-122">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="919e6-123">Descrive come il modello asincrono rende disponibili i vantaggi delle applicazioni multithreading nascondendo al contempo gran degli aspetti complessi inerenti la progettazione multithreading.</span><span class="sxs-lookup"><span data-stu-id="919e6-123">Describes how the asynchronous pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>
