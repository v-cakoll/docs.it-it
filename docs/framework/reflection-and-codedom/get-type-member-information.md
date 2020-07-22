---
title: 'Procedura: Ottenere informazioni su tipi e membri tramite reflection'
description: Informazioni su come ottenere informazioni sul tipo e sui membri con la reflection, usando lo spazio dei nomi System. Reflection.
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: fa7af39c0addb328944a03236c26982301caf722
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865320"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="52099-103">Procedura: Ottenere informazioni su tipi e membri tramite reflection</span><span class="sxs-lookup"><span data-stu-id="52099-103">How to: Get type and member information by using reflection</span></span>
<span data-ttu-id="52099-104">Lo <xref:System.Reflection> spazio dei nomi contiene molti metodi per ottenere informazioni sui tipi e sui relativi membri.</span><span class="sxs-lookup"><span data-stu-id="52099-104">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="52099-105">Questo articolo illustra uno di questi metodi, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="52099-105">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="52099-106">Per altre informazioni, vedere [Cenni preliminari sulla reflection](reflection.md).</span><span class="sxs-lookup"><span data-stu-id="52099-106">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="52099-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="52099-107">Example</span></span>

<span data-ttu-id="52099-108">Nell'esempio seguente vengono ottenute informazioni sul tipo e sui membri tramite reflection:</span><span class="sxs-lookup"><span data-stu-id="52099-108">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="52099-109">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="52099-109">See also</span></span>

- [<span data-ttu-id="52099-110">Programma con domini applicazione</span><span class="sxs-lookup"><span data-stu-id="52099-110">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="52099-111">Reflection</span><span class="sxs-lookup"><span data-stu-id="52099-111">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="52099-112">Usare i domini applicazione</span><span class="sxs-lookup"><span data-stu-id="52099-112">Use application domains</span></span>](../app-domains/use.md)
