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
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a>Procedura: Ottenere informazioni sul tipo e sui membri tramite reflection
Lo <xref:System.Reflection> spazio dei nomi contiene molti metodi per ottenere informazioni sui tipi e sui relativi membri. Questo articolo illustra uno di questi metodi, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>. Per altre informazioni, vedere [Cenni preliminari sulla reflection](reflection.md).
  
## <a name="example"></a>Esempio

Nell'esempio seguente vengono ottenute informazioni sul tipo e sui membri tramite reflection:

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a>Vedere anche

- [Programma con domini applicazione](../app-domains/application-domains.md#programming-with-application-domains)
- [Reflection](reflection.md)
- [Usare i domini applicazione](../app-domains/use.md)
