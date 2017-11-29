---
title: Marshalling di un delegato come metodo di callback
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c8c4eca35c406b38da603dc10358920ee887b137
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a><span data-ttu-id="b0434-102">Marshalling di un delegato come metodo di callback</span><span class="sxs-lookup"><span data-stu-id="b0434-102">Marshaling a Delegate as a Callback Method</span></span>
<span data-ttu-id="b0434-103">Questo esempio dimostra come passare delegati a una funzione non gestita che prevede puntatori a funzione.</span><span class="sxs-lookup"><span data-stu-id="b0434-103">This sample demonstrates how to pass delegates to an unmanaged function expecting function pointers.</span></span> <span data-ttu-id="b0434-104">Un delegato è una classe che può contenere un riferimento a un metodo ed è equivalente a un puntatore a una funzione indipendente dai tipi o a una funzione di callback.</span><span class="sxs-lookup"><span data-stu-id="b0434-104">A delegate is a class that can hold a reference to a method and is equivalent to a type-safe function pointer or a callback function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0434-105">Quando si usa un delegato all'interno di una chiamata, Common Language Runtime protegge il delegato per evitare che venga sottoposto a Garbage Collection per la durata della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b0434-105">When you use a delegate inside a call, the common language runtime protects the delegate from being garbage collected for the duration of that call.</span></span> <span data-ttu-id="b0434-106">Tuttavia, se la funzione non gestita archivia il delegato da usare dopo il completamento della chiamata, è necessario evitare manualmente operazioni di Garbage Collection fino a quando la funzione non gestita non ha terminato di usare il delegato.</span><span class="sxs-lookup"><span data-stu-id="b0434-106">However, if the unmanaged function stores the delegate to use after the call completes, you must manually prevent garbage collection until the unmanaged function finishes with the delegate.</span></span> <span data-ttu-id="b0434-107">Per altre informazioni, vedere [Esempio di HandleRef](http://msdn.microsoft.com/en-us/ab23b04e-1d53-4ec7-b27a-e892d9298959) ed [Esempio di GCHandle](http://msdn.microsoft.com/en-us/6acce798-0385-4ded-a790-77da842c113f).</span><span class="sxs-lookup"><span data-stu-id="b0434-107">For more information, see the [HandleRef Sample](http://msdn.microsoft.com/en-us/ab23b04e-1d53-4ec7-b27a-e892d9298959) and [GCHandle Sample](http://msdn.microsoft.com/en-us/6acce798-0385-4ded-a790-77da842c113f).</span></span>  
  
 <span data-ttu-id="b0434-108">Nell'esempio di callback vengono usate le seguenti funzioni non gestite, illustrate con le dichiarazioni di funzione originali:</span><span class="sxs-lookup"><span data-stu-id="b0434-108">The Callback sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="b0434-109">**TestCallBack** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="b0434-109">**TestCallBack** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   <span data-ttu-id="b0434-110">**TestCallBack2** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="b0434-110">**TestCallBack2** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 <span data-ttu-id="b0434-111">[PinvokeLib.dll](http://msdn.microsoft.com/en-us/5d1438d7-9946-489d-8ede-6c694a08f614) è una libreria non gestita personalizzata contenente un'implementazione per le funzioni elencate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b0434-111">[PinvokeLib.dll](http://msdn.microsoft.com/en-us/5d1438d7-9946-489d-8ede-6c694a08f614) is a custom unmanaged library that contains an implementation for the previously listed functions.</span></span>  
  
 <span data-ttu-id="b0434-112">In questo esempio, la classe `LibWrap` contiene prototipi gestiti per i metodi `TestCallBack` e `TestCallBack2`.</span><span class="sxs-lookup"><span data-stu-id="b0434-112">In this sample, the `LibWrap` class contains managed prototypes for the `TestCallBack` and `TestCallBack2` methods.</span></span> <span data-ttu-id="b0434-113">Entrambi i metodi di passano un delegato a una funzione di callback come parametro.</span><span class="sxs-lookup"><span data-stu-id="b0434-113">Both methods pass a delegate to a callback function as a parameter.</span></span> <span data-ttu-id="b0434-114">La firma del delegato deve corrispondere alla firma del metodo a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="b0434-114">The signature of the delegate must match the signature of the method it references.</span></span> <span data-ttu-id="b0434-115">Ad esempio, i delegati `FPtr` e `FPtr2` hanno firme identiche ai metodi `DoSomething` e `DoSomething2`.</span><span class="sxs-lookup"><span data-stu-id="b0434-115">For example, the `FPtr` and `FPtr2` delegates have signatures that are identical to the `DoSomething` and `DoSomething2` methods.</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="b0434-116">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="b0434-116">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a><span data-ttu-id="b0434-117">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="b0434-117">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="b0434-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0434-118">See Also</span></span>  
 [<span data-ttu-id="b0434-119">Esempi vari di marshalling</span><span class="sxs-lookup"><span data-stu-id="b0434-119">Miscellaneous Marshaling Samples</span></span>](http://msdn.microsoft.com/en-us/a915c948-54e9-4d0f-a525-95a77fd8ed70)  
 [<span data-ttu-id="b0434-120">Tipi di dati di Platform Invoke</span><span class="sxs-lookup"><span data-stu-id="b0434-120">Platform Invoke Data Types</span></span>](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)  
 [<span data-ttu-id="b0434-121">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="b0434-121">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
