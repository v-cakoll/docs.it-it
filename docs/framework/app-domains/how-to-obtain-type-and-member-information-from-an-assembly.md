---
title: 'Procedura: Reperire informazioni su tipo e membro da un assembly'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- obtaining assembly information
- assemblies [.NET Framework], obtaining information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef3fbb7af3097a67cb39f0c3b2ee294b86f0600e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701599"
---
# <a name="how-to-obtain-type-and-member-information-from-an-assembly"></a>Procedura: Reperire informazioni su tipo e membro da un assembly
Lo spazio dei nomi <xref:System.Reflection> contiene numerosi metodi per il recupero di informazioni da un assembly. Questa sezione illustra uno di questi metodi. Per altre informazioni, vedere [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md).  
  
 L'esempio seguente ottiene informazioni su tipo e membro da un assembly.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)]
 [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)]
 [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## <a name="see-also"></a>Vedere anche
- [Programmazione con i domini dell'applicazione](./application-domains.md#programming-with-application-domains)
- [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md)
- [Uso dei domini dell'applicazione](../../../docs/framework/app-domains/use.md)
