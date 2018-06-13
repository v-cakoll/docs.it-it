---
title: Componente BackgroundWorker
ms.date: 03/30/2017
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
ms.openlocfilehash: 38505876e2f944139622a0d7cf7aaab9c510ef89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525752"
---
# <a name="backgroundworker-component"></a><span data-ttu-id="c7e2c-102">Componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="c7e2c-102">BackgroundWorker Component</span></span>
<span data-ttu-id="c7e2c-103">Il `BackgroundWorker` componente consente a un form o controllo per eseguire un'operazione in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="c7e2c-103">The `BackgroundWorker` component enables your form or control to run an operation asynchronously.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7e2c-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c7e2c-104">In This Section</span></span>  
 [<span data-ttu-id="c7e2c-105">Panoramica sul componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="c7e2c-105">BackgroundWorker Component Overview</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <span data-ttu-id="c7e2c-106">Viene descritto il `BackgroundWorker` componente, che offre la possibilità di eseguire operazioni lunghe ed elaborate in modo asincrono (in background"), su un thread diverso dal thread dell'interfaccia utente principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c7e2c-106">Describes the `BackgroundWorker` component, which gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span>  
  
 [<span data-ttu-id="c7e2c-107">Procedura dettagliata: Esecuzione di un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="c7e2c-107">Walkthrough: Running an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 <span data-ttu-id="c7e2c-108">Viene illustrato come utilizzare il `BackgroundWorker` componente nella finestra di progettazione per eseguire un'operazione richiede molto tempo su un thread separato.</span><span class="sxs-lookup"><span data-stu-id="c7e2c-108">Demonstrates how to use the `BackgroundWorker` component in the designer to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="c7e2c-109">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="c7e2c-109">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="c7e2c-110">Viene illustrato come utilizzare il `BackgroundWorker` componente per l'esecuzione di un'operazione richiede molto tempo su un thread separato.</span><span class="sxs-lookup"><span data-stu-id="c7e2c-110">Demonstrates how to use the `BackgroundWorker` component to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="c7e2c-111">Procedura dettagliata: Implementazione di un form che usa un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="c7e2c-111">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="c7e2c-112">Crea un'applicazione utilizzando la finestra di progettazione che esegue calcoli matematici in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="c7e2c-112">Creates an application using the designer that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="c7e2c-113">Procedura: Implementare un form che esegue un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="c7e2c-113">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="c7e2c-114">Crea un'applicazione che esegue calcoli matematici in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="c7e2c-114">Creates an application that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="c7e2c-115">Procedura: Scaricare file in background</span><span class="sxs-lookup"><span data-stu-id="c7e2c-115">How to: Download a File in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-download-a-file-in-the-background.md)  
 <span data-ttu-id="c7e2c-116">Viene illustrato come utilizzare il `BackgroundWorker` componente per scaricare un file in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="c7e2c-116">Demonstrates how to use the `BackgroundWorker` component to download a file on a separate thread.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c7e2c-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="c7e2c-117">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="c7e2c-118">Descrive la classe e fornisce i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="c7e2c-118">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 <span data-ttu-id="c7e2c-119">Descrive il tipo che contiene i dati per il <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> evento.</span><span class="sxs-lookup"><span data-stu-id="c7e2c-119">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <span data-ttu-id="c7e2c-120">Descrive il tipo che contiene i dati per il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="c7e2c-120">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c7e2c-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c7e2c-121">Related Sections</span></span>  
 [<span data-ttu-id="c7e2c-122">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="c7e2c-122">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="c7e2c-123">Descrive come il modello asincrono rende disponibili i vantaggi delle applicazioni multithreading nascondendo al contempo gran degli aspetti complessi inerenti la progettazione multithreading.</span><span class="sxs-lookup"><span data-stu-id="c7e2c-123">Describes how the asynchronous pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>
