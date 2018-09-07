---
title: Passaggi del processo di serializzazione
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: ef81ecc7ca177fa9360f53a6b66015412d282065
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084915"
---
# <a name="steps-in-the-serialization-process"></a><span data-ttu-id="460db-102">Passaggi del processo di serializzazione</span><span class="sxs-lookup"><span data-stu-id="460db-102">Steps in the serialization process</span></span>
<span data-ttu-id="460db-103">Quando viene chiamato il metodo <xref:System.Runtime.Serialization.Formatter.Serialize*> su un [formattatore](xref:System.Runtime.Serialization.Formatter), la serializzazione dell'oggetto continua secondo la sequenza di regole riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="460db-103">When the <xref:System.Runtime.Serialization.Formatter.Serialize*> method is called on a [formatter](xref:System.Runtime.Serialization.Formatter), object serialization proceeds according to the following sequence of rules:</span></span>

- <span data-ttu-id="460db-104">Viene effettuato un controllo per determinare se il formattatore dispone di un selettore di surrogati.</span><span class="sxs-lookup"><span data-stu-id="460db-104">A check is made to determine whether the formatter has a surrogate selector.</span></span> <span data-ttu-id="460db-105">In caso affermativo, controllare se il selettore di surrogati gestisce oggetti del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="460db-105">If the formatter does, check whether the surrogate selector handles objects of the given type.</span></span> <span data-ttu-id="460db-106">Se il selettore gestisce il tipo di oggetto, viene chiamato <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=nameWithType> sul selettore di surrogati.</span><span class="sxs-lookup"><span data-stu-id="460db-106">If the selector handles the object type, <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=nameWithType> is called on the surrogate selector.</span></span>

- <span data-ttu-id="460db-107">Se non è presente alcun selettore di surrogati o il tipo di oggetto non viene gestito, viene effettuato un controllo per determinare se l'oggetto è contrassegnato con l'attributo [Serializable](xref:System.SerializableAttribute).</span><span class="sxs-lookup"><span data-stu-id="460db-107">If there is no surrogate selector or if it does not handle the object type, a check is made to determine whether the object is marked with the [Serializable](xref:System.SerializableAttribute) attribute.</span></span> <span data-ttu-id="460db-108">Se l'oggetto non è contrassegnato, viene generata una <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="460db-108">If the object is not, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>

- <span data-ttu-id="460db-109">Se l'oggetto è contrassegnato in modo appropriato, controllare se l'oggetto implementa l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="460db-109">If the object is marked appropriately, check whether the object implements the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="460db-110">In caso affermativo, <xref:System.Runtime.Serialization.ISerializable.GetObjectData*> viene chiamato sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="460db-110">If the object does, <xref:System.Runtime.Serialization.ISerializable.GetObjectData*> is called on the object.</span></span>
  
- <span data-ttu-id="460db-111">Se l'oggetto non implementa <xref:System.Runtime.Serialization.ISerializable>, vengono usati i criteri di serializzazione predefiniti, che serializzano tutti i campi non contrassegnati come [NonSerialized](xref:System.NonSerializedAttribute).</span><span class="sxs-lookup"><span data-stu-id="460db-111">If the object does not implement <xref:System.Runtime.Serialization.ISerializable>, the default serialization policy is used, serializing all fields not marked as [NonSerialized](xref:System.NonSerializedAttribute).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="460db-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="460db-112">See also</span></span>

- [<span data-ttu-id="460db-113">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="460db-113">Binary Serialization</span></span>](binary-serialization.md)  
- [<span data-ttu-id="460db-114">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="460db-114">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
