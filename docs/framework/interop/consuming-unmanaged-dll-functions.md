---
title: Utilizzo di funzioni di DLL non gestite
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- platform invoke, about platform invoke
- DLL functions, consuming unmanaged
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke
- DLL functions
ms.assetid: eca7606e-ebfb-4f47-b8d9-289903fdc045
ms.openlocfilehash: 7ec1f129dcc19300dd5a4e7c5e627d9e0edf29a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399973"
---
# <a name="consuming-unmanaged-dll-functions"></a><span data-ttu-id="61920-102">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="61920-102">Consuming Unmanaged DLL Functions</span></span>
<span data-ttu-id="61920-103">Platform invoke è un servizio che consente al codice gestito di chiamare funzioni non gestite implementate in librerie di collegamento dinamico (DLL), ad esempio quelle disponibili nell'API Windows.</span><span class="sxs-lookup"><span data-stu-id="61920-103">Platform invoke is a service that enables managed code to call unmanaged functions implemented in dynamic link libraries (DLLs), such as those in the Windows API.</span></span> <span data-ttu-id="61920-104">Individua e richiama una funzione esportata ed esegue il marshalling degli argomenti (Integer, stringhe, matrici, strutture e così via) nel limite dell'interazione, in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="61920-104">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="61920-105">In questa sezione vengono presentate le attività associate all'utilizzo di funzioni DLL non gestite e sono disponibili altre informazioni su platform invoke.</span><span class="sxs-lookup"><span data-stu-id="61920-105">This section introduces tasks associated with consuming unmanaged DLL functions and provides more information about platform invoke.</span></span> <span data-ttu-id="61920-106">Oltre alle seguenti attività, vengono illustrate alcune considerazioni generali e viene fornito un collegamento a informazioni ed esempi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="61920-106">In addition to the following tasks, there are general considerations and a link providing additional information and examples.</span></span>  
  
#### <a name="to-consume-exported-dll-functions"></a><span data-ttu-id="61920-107">Per usare le funzioni DLL esportate</span><span class="sxs-lookup"><span data-stu-id="61920-107">To consume exported DLL functions</span></span>  
  
1. <span data-ttu-id="61920-108">[Identificare le funzioni nelle DLL](identifying-functions-in-dlls.md).</span><span class="sxs-lookup"><span data-stu-id="61920-108">[Identify functions in DLLs](identifying-functions-in-dlls.md).</span></span>  
  
     <span data-ttu-id="61920-109">È necessario specificare almeno il nome della funzione e il nome della DLL che la contiene.</span><span class="sxs-lookup"><span data-stu-id="61920-109">Minimally, you must specify the name of the function and name of the DLL that contains it.</span></span>  
  
2. <span data-ttu-id="61920-110">[Creare una classe che contenga le funzioni DLL](creating-a-class-to-hold-dll-functions.md).</span><span class="sxs-lookup"><span data-stu-id="61920-110">[Create a class to hold DLL functions](creating-a-class-to-hold-dll-functions.md).</span></span>  
  
     <span data-ttu-id="61920-111">È possibile usare una classe esistente, creare una classe per ogni funzione non gestita o creare una classe contenente un set di funzioni non gestite correlate.</span><span class="sxs-lookup"><span data-stu-id="61920-111">You can use an existing class, create an individual class for each unmanaged function, or create one class that contains a set of related unmanaged functions.</span></span>  
  
3. <span data-ttu-id="61920-112">[Creare prototipi nel codice gestito](creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="61920-112">[Create prototypes in managed code](creating-prototypes-in-managed-code.md).</span></span>  
  
     <span data-ttu-id="61920-113">[Visual Basic] Usare l'istruzione **Declare** con le parole chiave **Function** e **Lib**.</span><span class="sxs-lookup"><span data-stu-id="61920-113">[Visual Basic] Use the **Declare** statement with the **Function** and **Lib** keywords.</span></span> <span data-ttu-id="61920-114">In pochissimi casi, è possibile usare **DllImportAttribute** con le parole chiave **Shared Function**.</span><span class="sxs-lookup"><span data-stu-id="61920-114">In some rare cases, you can use the **DllImportAttribute** with the **Shared Function** keywords.</span></span> <span data-ttu-id="61920-115">Questi casi vengono illustrati più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="61920-115">These cases are explained later in this section.</span></span>  
  
     <span data-ttu-id="61920-116">[Cè] Utilizzare **DllImportAttribute** per identificare la DLL e la funzione.</span><span class="sxs-lookup"><span data-stu-id="61920-116">[C#] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="61920-117">Contrassegnare il metodo con i modificatori **static** ed **extern**.</span><span class="sxs-lookup"><span data-stu-id="61920-117">Mark the method with the **static** and **extern** modifiers.</span></span>  
  
     <span data-ttu-id="61920-118">[C++] Usare **DllImportAttribute** per identificare la DLL e la funzione.</span><span class="sxs-lookup"><span data-stu-id="61920-118">[C++] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="61920-119">Contrassegnare il metodo o la funzione wrapper con **extern "C"**.</span><span class="sxs-lookup"><span data-stu-id="61920-119">Mark the wrapper method or function with **extern "C"**.</span></span>  
  
4. <span data-ttu-id="61920-120">[Chiamare una funzione DLL](calling-a-dll-function.md).</span><span class="sxs-lookup"><span data-stu-id="61920-120">[Call a DLL function](calling-a-dll-function.md).</span></span>  
  
     <span data-ttu-id="61920-121">Chiamare il metodo sulla classe gestita come qualsiasi altro metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="61920-121">Call the method on your managed class as you would any other managed method.</span></span> <span data-ttu-id="61920-122">Il [passaggio di strutture](passing-structures.md) e l'[implementazione di funzioni di callback](callback-functions.md) sono casi particolari.</span><span class="sxs-lookup"><span data-stu-id="61920-122">[Passing structures](passing-structures.md) and [implementing callback functions](callback-functions.md) are special cases.</span></span>  
  
 <span data-ttu-id="61920-123">Per alcuni esempi che mostrano come costruire dichiarazioni basate su .NET da usare con platform invoke, vedere , vedere [Marshalling dei dati con platform invoke](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="61920-123">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="a-closer-look-at-platform-invoke"></a><span data-ttu-id="61920-124">Informazioni dettagliate su platform invoke</span><span class="sxs-lookup"><span data-stu-id="61920-124">A closer look at platform invoke</span></span>  
 <span data-ttu-id="61920-125">Platform invoke si basa sui metadati per individuare le funzioni esportate ed effettuare il marshalling degli argomenti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="61920-125">Platform invoke relies on metadata to locate exported functions and marshal their arguments at run time.</span></span> <span data-ttu-id="61920-126">Questo processo viene illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="61920-126">The following illustration shows this process.</span></span>  
  
 ![Diagramma che illustra una chiamata PInvoke.](./media/consuming-unmanaged-dll-functions/platform-invoke-call.gif)  
  
 <span data-ttu-id="61920-128">Quando platform invoke chiama una funzione non gestita, esegue la sequenza di azioni seguente:</span><span class="sxs-lookup"><span data-stu-id="61920-128">When platform invoke calls an unmanaged function, it performs the following sequence of actions:</span></span>  
  
1. <span data-ttu-id="61920-129">Individua la DLL contenente la funziona.</span><span class="sxs-lookup"><span data-stu-id="61920-129">Locates the DLL containing the function.</span></span>  
  
2. <span data-ttu-id="61920-130">Carica la DLL in memoria.</span><span class="sxs-lookup"><span data-stu-id="61920-130">Loads the DLL into memory.</span></span>  
  
3. <span data-ttu-id="61920-131">Individua l'indirizzo della funzione in memoria ed effettua il push degli argomenti nello stack, effettuando il marshalling dei dati in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="61920-131">Locates the address of the function in memory and pushes its arguments onto the stack, marshaling data as required.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="61920-132">L'individuazione e il caricamento della DLL e l'individuazione dell'indirizzo della funzione in memoria si verificano solo alla prima chiamata alla funzione.</span><span class="sxs-lookup"><span data-stu-id="61920-132">Locating and loading the DLL, and locating the address of the function in memory occur only on the first call to the function.</span></span>  
  
4. <span data-ttu-id="61920-133">Trasferisce il controllo alla funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="61920-133">Transfers control to the unmanaged function.</span></span>  
  
 <span data-ttu-id="61920-134">Platform invoke dà luogo a eccezioni generate dalla funzione non gestita per il chiamante gestito.</span><span class="sxs-lookup"><span data-stu-id="61920-134">Platform invoke throws exceptions generated by the unmanaged function to the managed caller.</span></span>

## <a name="see-also"></a><span data-ttu-id="61920-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61920-135">See also</span></span>

- [<span data-ttu-id="61920-136">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="61920-136">Interoperating with Unmanaged Code</span></span>](index.md)
- [<span data-ttu-id="61920-137">Esempi di platform invoke</span><span class="sxs-lookup"><span data-stu-id="61920-137">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="61920-138">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="61920-138">Interop Marshaling</span></span>](interop-marshaling.md)
