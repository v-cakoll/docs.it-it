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
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a>Procedura: Ottenere informazioni su tipi e membri tramite reflection
Lo <xref:System.Reflection> spazio dei nomi contiene molti metodi per ottenere informazioni sui tipi e sui relativi membri. Questo articolo illustra uno di questi metodi, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> . Per altre informazioni, vedere [Cenni preliminari sulla reflection](reflection.md).
  
## <a name="example"></a>Esempio

Nell'esempio seguente vengono ottenute informazioni sul tipo e sui membri tramite reflection:

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a>Vedi anche

- [Programma con domini applicazione](../app-domains/application-domains.md#programming-with-application-domains)
- [Reflection](reflection.md)
- [Usare i domini applicazione](../app-domains/use.md)
