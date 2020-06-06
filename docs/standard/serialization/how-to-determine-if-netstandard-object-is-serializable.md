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
ms.openlocfilehash: b6791ae0666aeb0ac02d8a38ca419d7de2b263cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289603"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="8e6bd-103">Come determinare se un oggetto .NET Standard è serializzabile</span><span class="sxs-lookup"><span data-stu-id="8e6bd-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="8e6bd-104">Il .NET Standard è una specifica che definisce i tipi e i membri che devono essere presenti in implementazioni .NET specifiche conformi a tale versione dello standard.</span><span class="sxs-lookup"><span data-stu-id="8e6bd-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="8e6bd-105">Tuttavia, il .NET Standard non definisce se un tipo è serializzabile.</span><span class="sxs-lookup"><span data-stu-id="8e6bd-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="8e6bd-106">I tipi definiti nella libreria .NET Standard non sono contrassegnati con l' <xref:System.SerializableAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="8e6bd-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="8e6bd-107">Al contrario, le implementazioni di .NET specifiche, ad esempio .NET Framework e .NET Core, sono gratuite per determinare se un determinato tipo è serializzabile.</span><span class="sxs-lookup"><span data-stu-id="8e6bd-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span>

<span data-ttu-id="8e6bd-108">Se è stata sviluppata una libreria destinata al .NET Standard, la libreria può essere utilizzata da qualsiasi implementazione di .NET che supporti l'.NET Standard.</span><span class="sxs-lookup"><span data-stu-id="8e6bd-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="8e6bd-109">Ciò significa che non è possibile sapere in anticipo se un determinato tipo è serializzabile; è possibile determinare solo se è serializzabile in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8e6bd-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="8e6bd-110">È possibile determinare se un oggetto è serializzabile in fase di esecuzione recuperando il valore della <xref:System.Type.IsSerializable> proprietà di un <xref:System.Type> oggetto che rappresenta il tipo di tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="8e6bd-110">You can determine whether an object is serializable at run time by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="8e6bd-111">Nell'esempio seguente viene fornita un'implementazione di.</span><span class="sxs-lookup"><span data-stu-id="8e6bd-111">The following example provides one implementation.</span></span> <span data-ttu-id="8e6bd-112">Definisce un `IsSerializable(Object)` metodo di estensione che indica se <xref:System.Object> è possibile serializzare qualsiasi istanza.</span><span class="sxs-lookup"><span data-stu-id="8e6bd-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="8e6bd-113">È quindi possibile passare qualsiasi oggetto al metodo per determinare se può essere serializzato e deserializzato nell'implementazione .NET corrente, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8e6bd-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="8e6bd-114">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="8e6bd-114">See also</span></span>

- [<span data-ttu-id="8e6bd-115">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="8e6bd-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
