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
ms.workload: dotnet
ms.openlocfilehash: f6d9269261c6c0ce7573e0a8e298111971ae591c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a>Marshalling di un delegato come metodo di callback
Questo esempio dimostra come passare delegati a una funzione non gestita che prevede puntatori a funzione. Un delegato è una classe che può contenere un riferimento a un metodo ed è equivalente a un puntatore a una funzione indipendente dai tipi o a una funzione di callback.  
  
> [!NOTE]
>  Quando si usa un delegato all'interno di una chiamata, Common Language Runtime protegge il delegato per evitare che venga sottoposto a Garbage Collection per la durata della chiamata. Tuttavia, se la funzione non gestita archivia il delegato da usare dopo il completamento della chiamata, è necessario evitare manualmente operazioni di Garbage Collection fino a quando la funzione non gestita non ha terminato di usare il delegato. Per altre informazioni, vedere [Esempio di HandleRef](http://msdn.microsoft.com/en-us/ab23b04e-1d53-4ec7-b27a-e892d9298959) ed [Esempio di GCHandle](http://msdn.microsoft.com/en-us/6acce798-0385-4ded-a790-77da842c113f).  
  
 Nell'esempio di callback vengono usate le seguenti funzioni non gestite, illustrate con le dichiarazioni di funzione originali:  
  
-   **TestCallBack** esportata da PinvokeLib.dll.  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   **TestCallBack2** esportata da PinvokeLib.dll.  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 [PinvokeLib.dll](http://msdn.microsoft.com/en-us/5d1438d7-9946-489d-8ede-6c694a08f614) è una libreria non gestita personalizzata contenente un'implementazione per le funzioni elencate in precedenza.  
  
 In questo esempio, la classe `LibWrap` contiene prototipi gestiti per i metodi `TestCallBack` e `TestCallBack2`. Entrambi i metodi di passano un delegato a una funzione di callback come parametro. La firma del delegato deve corrispondere alla firma del metodo a cui fa riferimento. Ad esempio, i delegati `FPtr` e `FPtr2` hanno firme identiche ai metodi `DoSomething` e `DoSomething2`.  
  
## <a name="declaring-prototypes"></a>Dichiarazione dei prototipi  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a>Chiamata delle funzioni  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi vari di marshalling](http://msdn.microsoft.com/en-us/a915c948-54e9-4d0f-a525-95a77fd8ed70)  
 [Tipi di dati di Platform Invoke](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)  
 [Creazione di prototipi nel codice gestito](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
