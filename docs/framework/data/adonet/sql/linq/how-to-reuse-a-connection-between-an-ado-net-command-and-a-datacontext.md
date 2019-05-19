---
title: 'Procedura: Riutilizzare una connessione tra un comando ADO.NET e un oggetto DataContext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 92b0d8cf2c4904fabc17241ef2c31175f0c87baf
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878530"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Procedura: Riutilizzare una connessione tra un comando ADO.NET e un oggetto DataContext
In quanto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fa parte della famiglia di tecnologie ADO.NET e si basa sui servizi forniti da ADO.NET, è possibile riutilizzare una connessione tra un comando ADO.NET e un <xref:System.Data.Linq.DataContext>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come riutilizzare la stessa connessione tra un comando ADO.NET e <xref:System.Data.Linq.DataContext>.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [ADO.NET e LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)
- [Comunicazione con il database](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
