---
title: 'Procedura: Recuperare informazioni sui conflitti di entità'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
ms.openlocfilehash: 825ba2a32e7c75e922ca08386b9f6efede7b2693
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154752"
---
# <a name="how-to-retrieve-entity-conflict-information"></a>Procedura: Recuperare informazioni sui conflitti di entità
È possibile usare oggetti della classe <xref:System.Data.Linq.ObjectChangeConflict> per fornire informazioni sui conflitti rivelati dalle eccezioni <xref:System.Data.Linq.ChangeConflictException>. Per altre informazioni, vedere [la concorrenza ottimistica: Panoramica](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
## <a name="example"></a>Esempio  
 L'esempio riportato di seguito consente di scorrere un elenco di conflitti accumulati.  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Gestire i conflitti di modifiche](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
