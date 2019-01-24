---
title: 'Procedura: Recuperare informazioni sui conflitti di concorrenza'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: 478781e6c8ee31ebf6f5edd0e243a81d9e0524f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669562"
---
# <a name="how-to-retrieve-member-conflict-information"></a>Procedura: Recuperare informazioni sui conflitti di concorrenza
È possibile usare la classe <xref:System.Data.Linq.MemberChangeConflict> per recuperare informazioni sui singoli membri in conflitto. In questo stesso contesto è possibile provvedere alla gestione personalizzata del conflitto per qualsiasi membro. Per altre informazioni, vedere [la concorrenza ottimistica: Panoramica](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
## <a name="example"></a>Esempio  
 Il codice riportato di seguito consente di scorrere gli oggetti <xref:System.Data.Linq.ObjectChangeConflict> quindi, per ogni oggetto, di scorrere gli oggetti <xref:System.Data.Linq.MemberChangeConflict>.  
  
> [!NOTE]
>  Includere <xref:System.Reflection> in modo da fornire informazioni su <xref:System.Data.Linq.MemberChangeConflict.Member%2A>.  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Gestire i conflitti di modifiche](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
