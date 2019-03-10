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
ms.openlocfilehash: 0baf54d27cf33eef7e4df7019ee98b42eba40205
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710667"
---
# <a name="backgroundworker-component"></a><span data-ttu-id="73492-102">Componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="73492-102">BackgroundWorker Component</span></span>
<span data-ttu-id="73492-103">Il `BackgroundWorker` componente consente a un form o controllo per eseguire un'operazione in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="73492-103">The `BackgroundWorker` component enables your form or control to run an operation asynchronously.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73492-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="73492-104">In This Section</span></span>  
 [<span data-ttu-id="73492-105">Panoramica sul componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="73492-105">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="73492-106">Viene descritto il `BackgroundWorker` componente, che ti offre la possibilità di eseguire operazioni che richiedono molto tempo in modo asincrono ("in background"), in un thread diverso dal thread principale della UI dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="73492-106">Describes the `BackgroundWorker` component, which gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span>  
  
 [<span data-ttu-id="73492-107">Procedura dettagliata: Esecuzione di un'operazione in Background</span><span class="sxs-lookup"><span data-stu-id="73492-107">Walkthrough: Running an Operation in the Background</span></span>](walkthrough-running-an-operation-in-the-background.md)  
 <span data-ttu-id="73492-108">Viene illustrato come utilizzare il `BackgroundWorker` componente nella finestra di progettazione per eseguire un'operazione impegnativa in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="73492-108">Demonstrates how to use the `BackgroundWorker` component in the designer to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="73492-109">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="73492-109">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="73492-110">Viene illustrato come utilizzare il `BackgroundWorker` componente per l'esecuzione di un'operazione impegnativa in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="73492-110">Demonstrates how to use the `BackgroundWorker` component to run a time-consuming operation on a separate thread.</span></span>  
  
 [<span data-ttu-id="73492-111">Procedura dettagliata: Implementazione di un Form che usa un'operazione in Background</span><span class="sxs-lookup"><span data-stu-id="73492-111">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>](walkthrough-implementing-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="73492-112">Crea un'applicazione usando la finestra di progettazione che esegue calcoli matematici in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="73492-112">Creates an application using the designer that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="73492-113">Procedura: Implementare un modulo che usa un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="73492-113">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)  
 <span data-ttu-id="73492-114">Crea un'applicazione che esegue calcoli matematici in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="73492-114">Creates an application that does mathematical computations asynchronously.</span></span>  
  
 [<span data-ttu-id="73492-115">Procedura: Scaricare un File in Background</span><span class="sxs-lookup"><span data-stu-id="73492-115">How to: Download a File in the Background</span></span>](how-to-download-a-file-in-the-background.md)  
 <span data-ttu-id="73492-116">Viene illustrato come utilizzare il `BackgroundWorker` componente per scaricare un file in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="73492-116">Demonstrates how to use the `BackgroundWorker` component to download a file on a separate thread.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="73492-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="73492-117">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="73492-118">Descrive la classe e fornisce i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="73492-118">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>  
 <span data-ttu-id="73492-119">Descrive il tipo che contiene i dati per il <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> evento.</span><span class="sxs-lookup"><span data-stu-id="73492-119">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span>  
  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <span data-ttu-id="73492-120">Descrive il tipo che contiene i dati per il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="73492-120">Describes the type that holds data for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="73492-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="73492-121">Related Sections</span></span>  
 [<span data-ttu-id="73492-122">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="73492-122">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="73492-123">Viene descritto come il modello asincrono rende disponibili i vantaggi delle applicazioni multithread, nascondendo molti dei problemi complessi correlati alla progettazione multithread.</span><span class="sxs-lookup"><span data-stu-id="73492-123">Describes how the asynchronous pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>
