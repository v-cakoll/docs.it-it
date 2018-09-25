---
title: Come determinare se un oggetto .NET Standard è serializzabile
description: Viene illustrato come determinare se un tipo .NET Standard può essere serializzato in fase di esecuzione.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 196e99ab1f1a0baae53c6a1dc295b135e36fbfe0
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47080273"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="dae9d-103">Come determinare se un oggetto .NET Standard è serializzabile</span><span class="sxs-lookup"><span data-stu-id="dae9d-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="dae9d-104">.NET Standard è una specifica che definisce i tipi e membri che devono essere presenti nelle specifiche implementazioni .NET conformi a tale versione dello standard.</span><span class="sxs-lookup"><span data-stu-id="dae9d-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="dae9d-105">Tuttavia, .NET Standard non definisce se un tipo è serializzabile.</span><span class="sxs-lookup"><span data-stu-id="dae9d-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="dae9d-106">I tipi definiti nella libreria .NET Standard non siano contrassegnati con il <xref:System.SerializableAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="dae9d-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="dae9d-107">Al contrario, le implementazioni di .NET specifiche, ad esempio .NET Framework e .NET Core, sono gratuite determinare se un determinato tipo è serializzabile.</span><span class="sxs-lookup"><span data-stu-id="dae9d-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="dae9d-108">Se è stata sviluppata una libreria destinata a .NET Standard, la libreria può essere utilizzata da qualsiasi implementazione di .NET che supporta .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="dae9d-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="dae9d-109">Ciò significa che è possibile sapere in anticipo se un determinato tipo è serializzabile. è solo possibile determinare se è serializzabile in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dae9d-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="dae9d-110">È possibile determinare se un oggetto serializzabile in fase di esecuzione eseguendo il recupero del valore dei <xref:System.Type.IsSerializable> proprietà di un <xref:System.Type> oggetto che rappresenta il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="dae9d-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="dae9d-111">Nell'esempio seguente fornisce un'implementazione.</span><span class="sxs-lookup"><span data-stu-id="dae9d-111">The following example provides one implementation.</span></span> <span data-ttu-id="dae9d-112">Definisce un `IsSerializable(Object)` metodo di estensione che indica se qualsiasi <xref:System.Object> istanza può essere serializzata.</span><span class="sxs-lookup"><span data-stu-id="dae9d-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="dae9d-113">È quindi possibile passare qualsiasi oggetto al metodo per determinare se può essere serializzato e deserializzato nell'implementazione .NET corrente, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dae9d-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="dae9d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dae9d-114">See also</span></span>

- [<span data-ttu-id="dae9d-115">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="dae9d-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
