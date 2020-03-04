---
title: Come determinare se un oggetto .NET Standard è serializzabile
description: Viene illustrato come determinare se un tipo di .NET Standard può essere serializzato in fase di esecuzione.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.openlocfilehash: 4037dee36aeb619eb2757016904fd877158e57cf
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159897"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="aa9b5-103">Come determinare se un oggetto .NET Standard è serializzabile</span><span class="sxs-lookup"><span data-stu-id="aa9b5-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="aa9b5-104">Il .NET Standard è una specifica che definisce i tipi e i membri che devono essere presenti in implementazioni .NET specifiche conformi a tale versione dello standard.</span><span class="sxs-lookup"><span data-stu-id="aa9b5-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="aa9b5-105">Tuttavia, il .NET Standard non definisce se un tipo è serializzabile.</span><span class="sxs-lookup"><span data-stu-id="aa9b5-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="aa9b5-106">I tipi definiti nella libreria .NET Standard non sono contrassegnati con l'attributo <xref:System.SerializableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="aa9b5-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="aa9b5-107">Al contrario, le implementazioni di .NET specifiche, ad esempio .NET Framework e .NET Core, sono gratuite per determinare se un determinato tipo è serializzabile.</span><span class="sxs-lookup"><span data-stu-id="aa9b5-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span>

<span data-ttu-id="aa9b5-108">Se è stata sviluppata una libreria destinata al .NET Standard, la libreria può essere utilizzata da qualsiasi implementazione di .NET che supporti l'.NET Standard.</span><span class="sxs-lookup"><span data-stu-id="aa9b5-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="aa9b5-109">Ciò significa che non è possibile sapere in anticipo se un determinato tipo è serializzabile; è possibile determinare solo se è serializzabile in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="aa9b5-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="aa9b5-110">È possibile determinare se un oggetto è serializzabile in fase di esecuzione recuperando il valore della proprietà <xref:System.Type.IsSerializable> di un oggetto <xref:System.Type> che rappresenta il tipo di tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="aa9b5-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="aa9b5-111">Nell'esempio seguente viene fornita un'implementazione di.</span><span class="sxs-lookup"><span data-stu-id="aa9b5-111">The following example provides one implementation.</span></span> <span data-ttu-id="aa9b5-112">Definisce un metodo di estensione `IsSerializable(Object)` che indica se è possibile serializzare un'istanza di <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="aa9b5-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="aa9b5-113">È quindi possibile passare qualsiasi oggetto al metodo per determinare se può essere serializzato e deserializzato nell'implementazione .NET corrente, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="aa9b5-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="aa9b5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa9b5-114">See also</span></span>

- [<span data-ttu-id="aa9b5-115">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="aa9b5-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
