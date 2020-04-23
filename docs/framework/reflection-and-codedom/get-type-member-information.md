---
title: 'Procedura: ottenere informazioni sul tipo e sui membri tramite reflection'
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: 9ffc173bbd0ed12eedea0c191f6d39baf181793a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130209"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="4a995-102">Procedura: ottenere informazioni sul tipo e sui membri tramite reflection</span><span class="sxs-lookup"><span data-stu-id="4a995-102">How to: Get type and member information by using reflection</span></span>
<span data-ttu-id="4a995-103">Lo <xref:System.Reflection> spazio dei nomi contiene molti metodi per ottenere informazioni sui tipi e sui relativi membri.</span><span class="sxs-lookup"><span data-stu-id="4a995-103">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="4a995-104">Questo articolo illustra uno di questi metodi, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4a995-104">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4a995-105">Per altre informazioni, vedere [Cenni preliminari sulla reflection](reflection.md).</span><span class="sxs-lookup"><span data-stu-id="4a995-105">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="4a995-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a995-106">Example</span></span>

<span data-ttu-id="4a995-107">Nell'esempio seguente vengono ottenute informazioni sul tipo e sui membri tramite reflection:</span><span class="sxs-lookup"><span data-stu-id="4a995-107">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="4a995-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a995-108">See also</span></span>

- [<span data-ttu-id="4a995-109">Programma con domini applicazione</span><span class="sxs-lookup"><span data-stu-id="4a995-109">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="4a995-110">Reflection</span><span class="sxs-lookup"><span data-stu-id="4a995-110">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="4a995-111">Usare i domini applicazione</span><span class="sxs-lookup"><span data-stu-id="4a995-111">Use application domains</span></span>](../app-domains/use.md)
