---
title: Marshalling di un delegato come metodo di callback
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 579bc56a538707fd19d6d089c7f3c0c0561ea9eb
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2018
ms.locfileid: "49454421"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a><span data-ttu-id="424ff-102">Marshalling di un delegato come metodo di callback</span><span class="sxs-lookup"><span data-stu-id="424ff-102">Marshaling a Delegate as a Callback Method</span></span>
<span data-ttu-id="424ff-103">Questo esempio dimostra come passare delegati a una funzione non gestita che prevede puntatori a funzione.</span><span class="sxs-lookup"><span data-stu-id="424ff-103">This sample demonstrates how to pass delegates to an unmanaged function expecting function pointers.</span></span> <span data-ttu-id="424ff-104">Un delegato è una classe che può contenere un riferimento a un metodo ed è equivalente a un puntatore a una funzione indipendente dai tipi o a una funzione di callback.</span><span class="sxs-lookup"><span data-stu-id="424ff-104">A delegate is a class that can hold a reference to a method and is equivalent to a type-safe function pointer or a callback function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="424ff-105">Quando si usa un delegato all'interno di una chiamata, Common Language Runtime protegge il delegato per evitare che venga sottoposto a Garbage Collection per la durata della chiamata.</span><span class="sxs-lookup"><span data-stu-id="424ff-105">When you use a delegate inside a call, the common language runtime protects the delegate from being garbage collected for the duration of that call.</span></span> <span data-ttu-id="424ff-106">Tuttavia, se la funzione non gestita archivia il delegato da usare dopo il completamento della chiamata, è necessario evitare manualmente operazioni di Garbage Collection fino a quando la funzione non gestita non ha terminato di usare il delegato.</span><span class="sxs-lookup"><span data-stu-id="424ff-106">However, if the unmanaged function stores the delegate to use after the call completes, you must manually prevent garbage collection until the unmanaged function finishes with the delegate.</span></span> <span data-ttu-id="424ff-107">Per altre informazioni, vedere [Esempio di HandleRef](https://msdn.microsoft.com/library/ab23b04e-1d53-4ec7-b27a-e892d9298959(v=vs.100)) ed [Esempio di GCHandle](https://msdn.microsoft.com/library/6acce798-0385-4ded-a790-77da842c113f(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="424ff-107">For more information, see the [HandleRef Sample](https://msdn.microsoft.com/library/ab23b04e-1d53-4ec7-b27a-e892d9298959(v=vs.100)) and [GCHandle Sample](https://msdn.microsoft.com/library/6acce798-0385-4ded-a790-77da842c113f(v=vs.100)).</span></span>  
  
 <span data-ttu-id="424ff-108">Nell'esempio di callback vengono usate le seguenti funzioni non gestite, illustrate con le dichiarazioni di funzione originali:</span><span class="sxs-lookup"><span data-stu-id="424ff-108">The Callback sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="424ff-109">**TestCallBack** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="424ff-109">**TestCallBack** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   <span data-ttu-id="424ff-110">**TestCallBack2** esportata da PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="424ff-110">**TestCallBack2** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 <span data-ttu-id="424ff-111">[PinvokeLib.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as6wyhwt(v=vs.100)) è una libreria non gestita personalizzata contenente un'implementazione per le funzioni elencate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="424ff-111">[PinvokeLib.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as6wyhwt(v=vs.100)) is a custom unmanaged library that contains an implementation for the previously listed functions.</span></span>  
  
 <span data-ttu-id="424ff-112">In questo esempio, la classe `LibWrap` contiene prototipi gestiti per i metodi `TestCallBack` e `TestCallBack2`.</span><span class="sxs-lookup"><span data-stu-id="424ff-112">In this sample, the `LibWrap` class contains managed prototypes for the `TestCallBack` and `TestCallBack2` methods.</span></span> <span data-ttu-id="424ff-113">Entrambi i metodi di passano un delegato a una funzione di callback come parametro.</span><span class="sxs-lookup"><span data-stu-id="424ff-113">Both methods pass a delegate to a callback function as a parameter.</span></span> <span data-ttu-id="424ff-114">La firma del delegato deve corrispondere alla firma del metodo a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="424ff-114">The signature of the delegate must match the signature of the method it references.</span></span> <span data-ttu-id="424ff-115">Ad esempio, i delegati `FPtr` e `FPtr2` hanno firme identiche ai metodi `DoSomething` e `DoSomething2`.</span><span class="sxs-lookup"><span data-stu-id="424ff-115">For example, the `FPtr` and `FPtr2` delegates have signatures that are identical to the `DoSomething` and `DoSomething2` methods.</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="424ff-116">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="424ff-116">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a><span data-ttu-id="424ff-117">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="424ff-117">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="424ff-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="424ff-118">See Also</span></span>  
 <span data-ttu-id="424ff-119">[Esempi vari di marshalling](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="424ff-119">[Miscellaneous Marshaling Samples](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))</span></span>  
 <span data-ttu-id="424ff-120">[Tipi di dati platform invoke](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="424ff-120">[Platform Invoke Data Types](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span></span>  
 [<span data-ttu-id="424ff-121">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="424ff-121">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
