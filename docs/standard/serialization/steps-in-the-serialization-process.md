---
title: Passaggi del processo di serializzazione
description: Il processo di serializzazione inizia quando il metodo Serialize viene chiamato in un formattatore. Questo articolo descrive la sequenza di eventi.
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: 1f749b9102182e78bc3fda436cf386a9f5759d5a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379105"
---
# <a name="steps-in-the-serialization-process"></a><span data-ttu-id="25b95-104">Passaggi del processo di serializzazione</span><span class="sxs-lookup"><span data-stu-id="25b95-104">Steps in the serialization process</span></span>
<span data-ttu-id="25b95-105">Quando viene chiamato il metodo <xref:System.Runtime.Serialization.Formatter.Serialize%2A> su un [formattatore](xref:System.Runtime.Serialization.Formatter), la serializzazione dell'oggetto continua secondo la sequenza di regole riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="25b95-105">When the <xref:System.Runtime.Serialization.Formatter.Serialize%2A> method is called on a [formatter](xref:System.Runtime.Serialization.Formatter), object serialization proceeds according to the following sequence of rules:</span></span>

- <span data-ttu-id="25b95-106">Viene effettuato un controllo per determinare se il formattatore dispone di un selettore di surrogati.</span><span class="sxs-lookup"><span data-stu-id="25b95-106">A check is made to determine whether the formatter has a surrogate selector.</span></span> <span data-ttu-id="25b95-107">In caso affermativo, controllare se il selettore di surrogati gestisce oggetti del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="25b95-107">If the formatter does, check whether the surrogate selector handles objects of the given type.</span></span> <span data-ttu-id="25b95-108">Se il selettore gestisce il tipo di oggetto, viene chiamato <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> sul selettore di surrogati.</span><span class="sxs-lookup"><span data-stu-id="25b95-108">If the selector handles the object type, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> is called on the surrogate selector.</span></span>

- <span data-ttu-id="25b95-109">Se non è presente alcun selettore di surrogati o il tipo di oggetto non viene gestito, viene effettuato un controllo per determinare se l'oggetto è contrassegnato con l'attributo [Serializable](xref:System.SerializableAttribute).</span><span class="sxs-lookup"><span data-stu-id="25b95-109">If there is no surrogate selector or if it does not handle the object type, a check is made to determine whether the object is marked with the [Serializable](xref:System.SerializableAttribute) attribute.</span></span> <span data-ttu-id="25b95-110">Se l'oggetto non è contrassegnato, viene generata una <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="25b95-110">If the object is not, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>

- <span data-ttu-id="25b95-111">Se l'oggetto è contrassegnato in modo appropriato, controllare se l'oggetto implementa l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="25b95-111">If the object is marked appropriately, check whether the object implements the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="25b95-112">In caso affermativo, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> viene chiamato sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="25b95-112">If the object does, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> is called on the object.</span></span>
  
- <span data-ttu-id="25b95-113">Se l'oggetto non implementa <xref:System.Runtime.Serialization.ISerializable>, vengono usati i criteri di serializzazione predefiniti, che serializzano tutti i campi non contrassegnati come [NonSerialized](xref:System.NonSerializedAttribute).</span><span class="sxs-lookup"><span data-stu-id="25b95-113">If the object does not implement <xref:System.Runtime.Serialization.ISerializable>, the default serialization policy is used, serializing all fields not marked as [NonSerialized](xref:System.NonSerializedAttribute).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="25b95-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25b95-114">See also</span></span>

- [<span data-ttu-id="25b95-115">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="25b95-115">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="25b95-116">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="25b95-116">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
