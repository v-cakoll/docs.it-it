---
title: Serializzazione selettiva
ms.date: 08/07/2017
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
ms.openlocfilehash: cc5d7964d5f3268f08721593fefc07e3eff853ca
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159598"
---
# <a name="selective-serialization"></a><span data-ttu-id="ecf75-102">Serializzazione selettiva</span><span class="sxs-lookup"><span data-stu-id="ecf75-102">Selective serialization</span></span>
<span data-ttu-id="ecf75-103">Una classe spesso contiene campi che non devono essere serializzati.</span><span class="sxs-lookup"><span data-stu-id="ecf75-103">A class often contains fields that shouldn't be serialized.</span></span> <span data-ttu-id="ecf75-104">Ad esempio, si prenda in considerazione una classe che archivia un ID del thread in una variabile membro.</span><span class="sxs-lookup"><span data-stu-id="ecf75-104">For example, assume a class stores a thread ID in a member variable.</span></span> <span data-ttu-id="ecf75-105">Quando la classe viene deserializzata, il thread archivia l'ID nel caso in cui la classe serializzata non sia più in esecuzione. La serializzazione di questo valore non ha quindi senso.</span><span class="sxs-lookup"><span data-stu-id="ecf75-105">When the class is deserialized, the thread stored the ID for when the class was serialized might no longer be running; so serializing this value doesn't make sense.</span></span> <span data-ttu-id="ecf75-106">È possibile evitare che le variabili membro vengano serializzate contrassegnandole con l'attributo [NonSerialized](xref:System.NonSerializedAttribute) come riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ecf75-106">You can prevent member variables from being serialized by marking them with the [NonSerialized](xref:System.NonSerializedAttribute) attribute as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

<span data-ttu-id="ecf75-107">Se possibile, rendere non serializzabili gli oggetti che possono contenere dati sensibili alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ecf75-107">If possible, make an object that could contain security-sensitive data nonserializable.</span></span> <span data-ttu-id="ecf75-108">Se l'oggetto deve essere serializzato, applicare l'attributo `NonSerialized` ai campi specifici che archiviano dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="ecf75-108">If the object must be serialized, apply the `NonSerialized` attribute to specific fields that store sensitive data.</span></span> <span data-ttu-id="ecf75-109">Se non si escludono questi campi dalla serializzazione, è necessario essere consapevoli che i dati archiviati sono esposti a qualsiasi codice con le autorizzazioni per la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="ecf75-109">If you don't exclude these fields from serialization, be aware that the data they store are exposed to any code that has permission to serialize.</span></span> <span data-ttu-id="ecf75-110">Per altre informazioni sulla scrittura di codice di serializzazione sicuro, vedere [Sicurezza e serializzazione](../../../docs/framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="ecf75-110">For more information about writing secure serialization code, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="ecf75-111">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ecf75-111">See also</span></span>

- [<span data-ttu-id="ecf75-112">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="ecf75-112">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="ecf75-113">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="ecf75-113">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="ecf75-114">Sicurezza e serializzazione</span><span class="sxs-lookup"><span data-stu-id="ecf75-114">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)
