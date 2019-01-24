---
title: 'Procedura: Disattivare il caricamento posticipato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: 9878ec468333ba79d0171d0bf96235d48273e03e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669536"
---
# <a name="how-to-turn-off-deferred-loading"></a>Procedura: Disattivare il caricamento posticipato
È possibile disattivare il caricamento posticipato impostando <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> su `false`. Per altre informazioni, vedere [posticipato e immediato caricamento](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
> [!NOTE]
>  Il caricamento posticipato viene disattivato implicitamente quando è disattivato il rilevamento degli oggetti. Per altre informazioni, vedere [Procedura: Recuperare le informazioni in sola lettura](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene descritto come disattivare il caricamento posticipato impostando <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> su `false`.  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche
- [Concetti relativi alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [Esecuzione di query sul database](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
