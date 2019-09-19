---
title: "Procedura: Creare un dominio dell'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f42f85adf3e9b0874df6c0360bea25b07facc0d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053152"
---
# <a name="how-to-create-an-application-domain"></a>Procedura: Creare un dominio dell'applicazione
I domini dell'applicazione vengono creati automaticamente dall'host Common Language Runtime quando necessario. È tuttavia possibile creare i propri domini dell'applicazione e caricarvi gli assembly che si vuole gestire personalmente. È anche possibile creare domini dell'applicazione da cui eseguire codice.  
  
 Per creare un nuovo dominio dell'applicazione, usare uno dei metodi di overload **CreateDomain** nella classe <xref:System.AppDomain?displayProperty=nameWithType>. È possibile assegnare un nome al dominio dell'applicazione da usare per fare riferimento al dominio.  
  
 L'esempio seguente crea un nuovo dominio dell'applicazione, assegna al dominio il nome `MyDomain` e quindi stampa il nome del dominio host e del dominio dell'applicazione figlio appena creato nella console.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione con i domini dell'applicazione](application-domains.md#programming-with-application-domains)
- [Uso dei domini dell'applicazione](use.md)
