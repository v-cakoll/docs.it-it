---
title: 'Procedura: Recuperare informazioni sui conflitti tra membri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: 40caa07488cb40ca8e9e3eb3a570c325b92de491
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793300"
---
# <a name="how-to-retrieve-member-conflict-information"></a>Procedura: Recuperare informazioni sui conflitti tra membri
È possibile usare la classe <xref:System.Data.Linq.MemberChangeConflict> per recuperare informazioni sui singoli membri in conflitto. In questo stesso contesto è possibile provvedere alla gestione personalizzata del conflitto per qualsiasi membro. Per ulteriori informazioni, vedere [concorrenza ottimistica: Panoramica](optimistic-concurrency-overview.md).  
  
## <a name="example"></a>Esempio  
 Il codice riportato di seguito consente di scorrere gli oggetti <xref:System.Data.Linq.ObjectChangeConflict> quindi, per ogni oggetto, di scorrere gli oggetti <xref:System.Data.Linq.MemberChangeConflict>.  
  
> [!NOTE]
> Includere <xref:System.Reflection> in modo da fornire informazioni su <xref:System.Data.Linq.MemberChangeConflict.Member%2A>.  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Gestione dei conflitti di modifica](how-to-manage-change-conflicts.md)
