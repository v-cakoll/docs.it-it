---
title: 'Procedura: Ottenere informazioni sul tipo e sui membri tramite reflection'
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
author: rpetrusha
ms.author: ronpet
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: da71845ea276267220636cfd661465ea02b2b50d
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972921"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="2fb97-102">Procedura: Ottenere informazioni sul tipo e sui membri tramite reflection</span><span class="sxs-lookup"><span data-stu-id="2fb97-102">How to: Get type and member information by using reflection</span></span>
<span data-ttu-id="2fb97-103">Lo <xref:System.Reflection> spazio dei nomi contiene molti metodi per ottenere informazioni sui tipi e sui relativi membri.</span><span class="sxs-lookup"><span data-stu-id="2fb97-103">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="2fb97-104">Questo articolo illustra uno di questi metodi, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2fb97-104">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2fb97-105">Per altre informazioni, vedere [Cenni preliminari sulla reflection](reflection.md).</span><span class="sxs-lookup"><span data-stu-id="2fb97-105">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="2fb97-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="2fb97-106">Example</span></span>

<span data-ttu-id="2fb97-107">Nell'esempio seguente vengono ottenute informazioni sul tipo e sui membri tramite reflection:</span><span class="sxs-lookup"><span data-stu-id="2fb97-107">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="2fb97-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fb97-108">See also</span></span>

- [<span data-ttu-id="2fb97-109">Programma con domini applicazione</span><span class="sxs-lookup"><span data-stu-id="2fb97-109">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="2fb97-110">Reflection</span><span class="sxs-lookup"><span data-stu-id="2fb97-110">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="2fb97-111">Usare i domini applicazione</span><span class="sxs-lookup"><span data-stu-id="2fb97-111">Use application domains</span></span>](../app-domains/use.md)
