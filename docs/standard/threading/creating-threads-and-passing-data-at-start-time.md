---
title: Creazione di thread e passaggio di dati all'avvio
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61808dc804cc627ab368a5250414dfcc5f54c87e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="creating-threads-and-passing-data-at-start-time"></a><span data-ttu-id="26f9e-102">Creazione di thread e passaggio di dati all'avvio</span><span class="sxs-lookup"><span data-stu-id="26f9e-102">Creating Threads and Passing Data at Start Time</span></span>
<span data-ttu-id="26f9e-103">Quando viene creato un processo del sistema operativo, il sistema operativo inserisce un thread per eseguire codice in tale processo, inclusi qualsiasi dominio dell'applicazione originale.</span><span class="sxs-lookup"><span data-stu-id="26f9e-103">When an operating-system process is created, the operating system injects a thread to execute code in that process, including any original application domain.</span></span> <span data-ttu-id="26f9e-104">Da quel momento, i domini applicazione possono essere creati e distrutti senza necessariamente creato o eliminato qualsiasi thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="26f9e-104">From that point on, application domains can be created and destroyed without any operating system threads necessarily being created or destroyed.</span></span> <span data-ttu-id="26f9e-105">Se viene gestito il codice eseguito codice, quindi un <xref:System.Threading.Thread> dell'oggetto per il thread in esecuzione nel dominio applicazione corrente può essere ottenuto tramite il recupero statica <xref:System.Threading.Thread.CurrentThread%2A> proprietà di tipo <xref:System.Threading.Thread>.</span><span class="sxs-lookup"><span data-stu-id="26f9e-105">If the code being executed is managed code, then a <xref:System.Threading.Thread> object for the thread executing in the current application domain can be obtained by retrieving the static <xref:System.Threading.Thread.CurrentThread%2A> property of type <xref:System.Threading.Thread>.</span></span> <span data-ttu-id="26f9e-106">In questo argomento viene descritta la creazione di thread e vengono illustrate le alternative per passare dati alla routine del thread.</span><span class="sxs-lookup"><span data-stu-id="26f9e-106">This topic describes thread creation and discusses alternatives for passing data to the thread procedure.</span></span>  
  
## <a name="creating-a-thread"></a><span data-ttu-id="26f9e-107">Creazione di un Thread</span><span class="sxs-lookup"><span data-stu-id="26f9e-107">Creating a Thread</span></span>  
 <span data-ttu-id="26f9e-108">Creazione di un nuovo <xref:System.Threading.Thread> oggetto crea un nuovo thread gestito.</span><span class="sxs-lookup"><span data-stu-id="26f9e-108">Creating a new <xref:System.Threading.Thread> object creates a new managed thread.</span></span> <span data-ttu-id="26f9e-109">Il <xref:System.Threading.Thread> classe dispone di costruttori che accettano un <xref:System.Threading.ThreadStart> delegato o un <xref:System.Threading.ParameterizedThreadStart> delegare; il delegato il wrapping del metodo che viene richiamato dal nuovo thread quando si chiama il <xref:System.Threading.Thread.Start%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="26f9e-109">The <xref:System.Threading.Thread> class has constructors that take a <xref:System.Threading.ThreadStart> delegate or a <xref:System.Threading.ParameterizedThreadStart> delegate; the delegate wraps the method that is invoked by the new thread when you call the <xref:System.Threading.Thread.Start%2A> method.</span></span> <span data-ttu-id="26f9e-110">La chiamata <xref:System.Threading.Thread.Start%2A> più volte un <xref:System.Threading.ThreadStateException> generata.</span><span class="sxs-lookup"><span data-stu-id="26f9e-110">Calling <xref:System.Threading.Thread.Start%2A> more than once causes a <xref:System.Threading.ThreadStateException> to be thrown.</span></span>  
  
 <span data-ttu-id="26f9e-111">Il <xref:System.Threading.Thread.Start%2A> restituisce immediatamente, spesso prima dell'avvio effettivo il nuovo thread.</span><span class="sxs-lookup"><span data-stu-id="26f9e-111">The <xref:System.Threading.Thread.Start%2A> method returns immediately, often before the new thread has actually started.</span></span> <span data-ttu-id="26f9e-112">È possibile utilizzare il <xref:System.Threading.Thread.ThreadState%2A> e <xref:System.Threading.Thread.IsAlive%2A> le proprietà per determinare lo stato del thread in qualsiasi momento, ma queste proprietà mai da utilizzare per la sincronizzazione delle attività di thread.</span><span class="sxs-lookup"><span data-stu-id="26f9e-112">You can use the <xref:System.Threading.Thread.ThreadState%2A> and <xref:System.Threading.Thread.IsAlive%2A> properties to determine the state of the thread at any one moment, but these properties should never be used for synchronizing the activities of threads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26f9e-113">Una volta avviato un thread, non è necessario mantenere un riferimento al <xref:System.Threading.Thread> oggetto.</span><span class="sxs-lookup"><span data-stu-id="26f9e-113">Once a thread is started, it is not necessary to retain a reference to the <xref:System.Threading.Thread> object.</span></span> <span data-ttu-id="26f9e-114">Il thread continua l'esecuzione fino al termine della procedura di thread.</span><span class="sxs-lookup"><span data-stu-id="26f9e-114">The thread continues to execute until the thread procedure ends.</span></span>  
  
 <span data-ttu-id="26f9e-115">Esempio di codice seguente crea due nuovi thread per chiamare i metodi statici e istanza su un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="26f9e-115">The following code example creates two new threads to call instance and static methods on another object.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads-and-retrieving-data-from-threads"></a><span data-ttu-id="26f9e-116">Passaggio di dati ai thread e il recupero dei dati da thread</span><span class="sxs-lookup"><span data-stu-id="26f9e-116">Passing Data to Threads and Retrieving Data from Threads</span></span>  
 <span data-ttu-id="26f9e-117">In .NET Framework versione 2.0, il <xref:System.Threading.ParameterizedThreadStart> delegato fornisce un modo semplice per passare un oggetto contenente i dati da un thread quando si chiama il <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> overload del metodo.</span><span class="sxs-lookup"><span data-stu-id="26f9e-117">In the .NET Framework version 2.0, the <xref:System.Threading.ParameterizedThreadStart> delegate provides an easy way to pass an object containing data to a thread when you call the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload.</span></span> <span data-ttu-id="26f9e-118">Per un esempio di codice, vedere <xref:System.Threading.ParameterizedThreadStart>.</span><span class="sxs-lookup"><span data-stu-id="26f9e-118">See <xref:System.Threading.ParameterizedThreadStart> for a code example.</span></span>  
  
 <span data-ttu-id="26f9e-119">Utilizzo di <xref:System.Threading.ParameterizedThreadStart> delegato non è un modo indipendente dai tipi per passare i dati, perché il <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> overload del metodo accetta qualsiasi oggetto.</span><span class="sxs-lookup"><span data-stu-id="26f9e-119">Using the <xref:System.Threading.ParameterizedThreadStart> delegate is not a type-safe way to pass data, because the <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> method overload accepts any object.</span></span> <span data-ttu-id="26f9e-120">In alternativa è possibile incapsulare la procedura del thread e i dati in una classe helper e utilizzare il <xref:System.Threading.ThreadStart> delegato per eseguire la procedura del thread.</span><span class="sxs-lookup"><span data-stu-id="26f9e-120">An alternative is to encapsulate the thread procedure and the data in a helper class and use the <xref:System.Threading.ThreadStart> delegate to execute the thread procedure.</span></span> <span data-ttu-id="26f9e-121">Questa tecnica è illustrata negli esempi di due codice che seguono.</span><span class="sxs-lookup"><span data-stu-id="26f9e-121">This technique is shown in the two code examples that follow.</span></span>  
  
 <span data-ttu-id="26f9e-122">Nessuno di questi delegati è un valore restituito, perché non è possibile restituire i dati da una chiamata asincrona.</span><span class="sxs-lookup"><span data-stu-id="26f9e-122">Neither of these delegates has a return value, because there is no place to return the data from an asynchronous call.</span></span> <span data-ttu-id="26f9e-123">Per recuperare i risultati di un metodo di thread, è possibile utilizzare un metodo di callback, come illustrato nel secondo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="26f9e-123">To retrieve the results of a thread method, you can use a callback method, as demonstrated in the second code example.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### <a name="retrieving-data-with-callback-methods"></a><span data-ttu-id="26f9e-124">Recupero dei dati con i metodi di Callback</span><span class="sxs-lookup"><span data-stu-id="26f9e-124">Retrieving Data with Callback Methods</span></span>  
 <span data-ttu-id="26f9e-125">Nell'esempio seguente viene illustrato un metodo di callback che recupera dati da un thread.</span><span class="sxs-lookup"><span data-stu-id="26f9e-125">The following example demonstrates a callback method that retrieves data from a thread.</span></span> <span data-ttu-id="26f9e-126">Il costruttore per la classe che contiene i dati e il metodo di thread accetta inoltre un delegato che rappresenta il metodo di callback. prima che il metodo di thread termina, viene richiamato il delegato di callback.</span><span class="sxs-lookup"><span data-stu-id="26f9e-126">The constructor for the class that contains the data and the thread method also accepts a delegate representing the callback method; before the thread method ends, it invokes the callback delegate.</span></span>  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="26f9e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26f9e-127">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadStart>  
 <xref:System.Threading.ParameterizedThreadStart>  
 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="26f9e-128">Threading</span><span class="sxs-lookup"><span data-stu-id="26f9e-128">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="26f9e-129">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="26f9e-129">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
