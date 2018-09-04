---
title: Cenni preliminari sul componente BackgroundWorker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- BackgroundWorker
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
ms.openlocfilehash: 1f7da963db34434ee2631e9e2c0367abbd628656
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43539236"
---
# <a name="backgroundworker-component-overview"></a><span data-ttu-id="ceec9-102">Cenni preliminari sul componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="ceec9-102">BackgroundWorker Component Overview</span></span>
<span data-ttu-id="ceec9-103">Molte operazioni comuni hanno tempi di esecuzione particolarmente lunghi,</span><span class="sxs-lookup"><span data-stu-id="ceec9-103">There are many commonly performed operations that can take a long time to execute.</span></span> <span data-ttu-id="ceec9-104">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ceec9-104">For example:</span></span>  
  
-   <span data-ttu-id="ceec9-105">Download di immagini</span><span class="sxs-lookup"><span data-stu-id="ceec9-105">Image downloads</span></span>  
  
-   <span data-ttu-id="ceec9-106">Chiamate di servizi Web</span><span class="sxs-lookup"><span data-stu-id="ceec9-106">Web service invocations</span></span>  
  
-   <span data-ttu-id="ceec9-107">Download e caricamento di file (anche per applicazioni peer-to-peer)</span><span class="sxs-lookup"><span data-stu-id="ceec9-107">File downloads and uploads (including for peer-to-peer applications)</span></span>  
  
-   <span data-ttu-id="ceec9-108">Calcoli locali complessi</span><span class="sxs-lookup"><span data-stu-id="ceec9-108">Complex local computations</span></span>  
  
-   <span data-ttu-id="ceec9-109">Transazioni di database</span><span class="sxs-lookup"><span data-stu-id="ceec9-109">Database transactions</span></span>  
  
-   <span data-ttu-id="ceec9-110">Accesso locale ai dischi, a causa della velocità ridotta rispetto all'accesso alla memoria</span><span class="sxs-lookup"><span data-stu-id="ceec9-110">Local disk access, given its slow speed relative to memory access</span></span>  
  
 <span data-ttu-id="ceec9-111">Durante l'esecuzione di questo tipo di operazioni è possibile che l'interfaccia utente si blocchi.</span><span class="sxs-lookup"><span data-stu-id="ceec9-111">Operations like these can cause your user interface to hang while they are running.</span></span> <span data-ttu-id="ceec9-112">Nel caso sia necessario eseguire operazioni di questo genere ma si vogliano evitare ritardi di risposta dell'interfaccia utente, il componente <xref:System.ComponentModel.BackgroundWorker> costituisce la soluzione ideale.</span><span class="sxs-lookup"><span data-stu-id="ceec9-112">When you want a responsive UI and you are faced with long delays associated with such operations, the <xref:System.ComponentModel.BackgroundWorker> component provides a convenient solution.</span></span>  
  
 <span data-ttu-id="ceec9-113">Il componente <xref:System.ComponentModel.BackgroundWorker> offre la possibilità di eseguire operazioni che richiedono molto tempo in modo asincrono (in background) su un thread diverso da quello usato dall'interfaccia utente principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ceec9-113">The <xref:System.ComponentModel.BackgroundWorker> component gives you the ability to execute time-consuming operations asynchronously ("in the background"), on a thread different from your application's main UI thread.</span></span> <span data-ttu-id="ceec9-114">Per usare un componente <xref:System.ComponentModel.BackgroundWorker>, è sufficiente indicare il metodo di lavoro da eseguire in background e quindi chiamare il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="ceec9-114">To use a <xref:System.ComponentModel.BackgroundWorker>, you simply tell it what time-consuming worker method to execute in the background, and then you call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="ceec9-115">Il thread chiamante continua l'esecuzione normale mentre il metodo di lavoro viene eseguito in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="ceec9-115">Your calling thread continues to run normally while the worker method runs asynchronously.</span></span> <span data-ttu-id="ceec9-116">Al completamento dell'esecuzione del metodo, il componente <xref:System.ComponentModel.BackgroundWorker> avvisa il thread chiamante attivando l'evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>, in cui è possibile includere i risultati dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="ceec9-116">When the method is finished, the <xref:System.ComponentModel.BackgroundWorker> alerts the calling thread by firing the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event, which optionally contains the results of the operation.</span></span>  
  
 <span data-ttu-id="ceec9-117">Il <xref:System.ComponentModel.BackgroundWorker> componente è disponibile presso il **casella degli strumenti**, nella **componenti** scheda. Per aggiungere un componente <xref:System.ComponentModel.BackgroundWorker> al form, trascina il componente <xref:System.ComponentModel.BackgroundWorker> nel form.</span><span class="sxs-lookup"><span data-stu-id="ceec9-117">The <xref:System.ComponentModel.BackgroundWorker> component is available from the **Toolbox**, in the **Components** tab. To add a <xref:System.ComponentModel.BackgroundWorker> to your form, drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span> <span data-ttu-id="ceec9-118">Verrà visualizzato nella barra dei componenti e le proprietà visualizzate nella **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="ceec9-118">It appears in the component tray, and its properties appear in the **Properties** window.</span></span>  
  
 <span data-ttu-id="ceec9-119">Per avviare l'operazione asincrona, usare il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="ceec9-119">To start your asynchronous operation, use the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span> <span data-ttu-id="ceec9-120">Il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> accetta un parametro `object` facoltativo, che può essere usato per passare gli argomenti al metodo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ceec9-120"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> takes an optional `object` parameter, which can be used to pass arguments to your worker method.</span></span> <span data-ttu-id="ceec9-121">La classe <xref:System.ComponentModel.BackgroundWorker> espone l'evento <xref:System.ComponentModel.BackgroundWorker.DoWork> a cui viene collegato il thread di lavoro mediante un gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork>.</span><span class="sxs-lookup"><span data-stu-id="ceec9-121">The <xref:System.ComponentModel.BackgroundWorker> class exposes the <xref:System.ComponentModel.BackgroundWorker.DoWork> event, to which your worker thread is attached through a <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
 <span data-ttu-id="ceec9-122">Il gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork> accetta un parametro <xref:System.ComponentModel.DoWorkEventArgs> che include una proprietà <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>.</span><span class="sxs-lookup"><span data-stu-id="ceec9-122">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler takes a <xref:System.ComponentModel.DoWorkEventArgs> parameter, which has an <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property.</span></span> <span data-ttu-id="ceec9-123">Questa proprietà riceve il parametro da <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> e può essere passata al metodo di lavoro, che verrà chiamato nel gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork>.</span><span class="sxs-lookup"><span data-stu-id="ceec9-123">This property receives the parameter from <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and can be passed to your worker method, which will be called in the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="ceec9-124">L'esempio seguente illustra come assegnare un risultato proveniente da un metodo di lavoro denominato `ComputeFibonacci`.</span><span class="sxs-lookup"><span data-stu-id="ceec9-124">The following example shows how to assign a result from a worker method called `ComputeFibonacci`.</span></span> <span data-ttu-id="ceec9-125">Fa parte di un esempio più esaustivo, che trova in [procedura: implementare un Form che usa un'operazione in Background](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="ceec9-125">It is part of a larger example, which you can find at [How to: Implement a Form That Uses a Background Operation](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 <span data-ttu-id="ceec9-126">Per altre informazioni sull'uso di gestori eventi, vedere [eventi](../../../../docs/standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="ceec9-126">For more information on using event handlers, see [Events](../../../../docs/standard/events/index.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ceec9-127">L'uso di qualsiasi tipo di multithreading determina la potenziale esposizione a bug seri e complessi.</span><span class="sxs-lookup"><span data-stu-id="ceec9-127">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="ceec9-128">Vedere [Procedure consigliate per l'uso del threading gestito](../../../../docs/standard/threading/managed-threading-best-practices.md) prima di implementare soluzioni che usano il multithreading.</span><span class="sxs-lookup"><span data-stu-id="ceec9-128">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
 <span data-ttu-id="ceec9-129">Per altre informazioni sull'uso di <xref:System.ComponentModel.BackgroundWorker> classe, vedere [procedura: eseguire un'operazione in Background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="ceec9-129">For more information on using the <xref:System.ComponentModel.BackgroundWorker> class, see [How to: Run an Operation in the Background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceec9-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ceec9-130">See Also</span></span>  
 [<span data-ttu-id="ceec9-131">NON INCLUSO NELLA COMPILAZIONE: Multithreading in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ceec9-131">NOT IN BUILD: Multithreading in Visual Basic</span></span>](https://msdn.microsoft.com/library/c731a50c-09c1-4468-9646-54c86b75d269)  
 [<span data-ttu-id="ceec9-132">Procedura: Implementare un form che esegue un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="ceec9-132">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
