---
title: 'Procedura: determinare se un oggetto .NET Standard è serializzabile'
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
ms.openlocfilehash: 247eed2e7091930c6bcfaa524296b45350dd6510
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580988"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="f289e-103">Procedura: determinare se un oggetto .NET Standard è serializzabile</span><span class="sxs-lookup"><span data-stu-id="f289e-103">How to: Determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="f289e-104">.NET Standard è una specifica che definisce i tipi e membri che devono essere presenti in implementazioni specifiche di .NET conformi a tale versione dello standard.</span><span class="sxs-lookup"><span data-stu-id="f289e-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="f289e-105">Tuttavia, lo Standard di .NET non definisce se un tipo è serializzabile.</span><span class="sxs-lookup"><span data-stu-id="f289e-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="f289e-106">I tipi definiti nella libreria Standard di .NET non contrassegnati con il <xref:System.SerializableAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="f289e-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="f289e-107">Invece, le implementazioni specifiche di .NET, ad esempio .NET Framework e .NET Core, sono disponibili per determinare se un determinato tipo è serializzabile.</span><span class="sxs-lookup"><span data-stu-id="f289e-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="f289e-108">Se si sono creato una libreria che ha come destinazione .NET Standard, la libreria può essere utilizzata da qualsiasi implementazione di .NET che supporta lo Standard di .NET.</span><span class="sxs-lookup"><span data-stu-id="f289e-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="f289e-109">Ciò significa che è possibile sapere in anticipo se un determinato tipo è serializzabile. è solo possibile determinare se è serializzabile in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f289e-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="f289e-110">È possibile determinare se un oggetto serializzabile in fase di esecuzione eseguendo il recupero del valore del <xref:System.Type.IsSerializable> proprietà di un <xref:System.Type> oggetto che rappresenta il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f289e-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="f289e-111">Nell'esempio seguente fornisce un'implementazione.</span><span class="sxs-lookup"><span data-stu-id="f289e-111">The following example provides one implementation.</span></span> <span data-ttu-id="f289e-112">Definisce un `IsSerializable(Object)` metodo di estensione che indica se qualsiasi <xref:System.Object> istanza può essere serializzata.</span><span class="sxs-lookup"><span data-stu-id="f289e-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="f289e-113">È quindi possibile passare qualsiasi oggetto al metodo per determinare se può essere serializzato e deserializzato nell'implementazione corrente di .NET, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f289e-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

# <a name="see-also"></a><span data-ttu-id="f289e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f289e-114">See also</span></span>

<span data-ttu-id="f289e-115">[Serializzazione binaria](binary-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="f289e-115">[Binary serialization](binary-serialization.md) </span></span>  
<xref:System.SerializableAttribute?displayProperty=nameWithType>    
<xref:System.Type.IsSerializable?displayProperty=nameWithType>   
