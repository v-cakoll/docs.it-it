---
title: 'Procedura: utilizzare matrici di raccolte di blocco in una pipeline'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
ms.openlocfilehash: 397c438bacd1cfed1613efef61e9d7266d55ea47
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711259"
---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a>Procedura: utilizzare matrici di raccolte di blocco in una pipeline
L'esempio seguente illustra come usare matrici di oggetti <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> con metodi statici, ad esempio <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> e <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A>, per implementare un trasferimento di dati rapido e flessibile tra componenti.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra un'implementazione della pipeline di base in cui ogni oggetto preleva simultaneamente dati dalla raccolta di input, li trasforma e li passa alla raccolta di output.  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Raccolte thread-safe](../../../../docs/standard/collections/thread-safe/index.md)
