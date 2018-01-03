---
title: 'Procedura: archiviare e riutilizzare query'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a012bd79-1809-45e3-adea-0229532396cc
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8170b1219bf66c1f90fb5db3143916f7a41aab94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-store-and-reuse-queries"></a>Procedura: archiviare e riutilizzare query
Quando si usa un'applicazione che esegue molte volte query strutturalmente simili, è spesso possibile migliorare le prestazioni compilando la query una volta ed eseguendola più volte con parametri diversi. Un'applicazione potrebbe ad esempio essere usata per recuperare tutti i clienti di una determinata città, specificata in fase di runtime dall'utente in un modulo. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]supporta l'utilizzo di *le query compilate* a questo scopo.  
  
> [!NOTE]
>  Questo modello di utilizzo rappresenta il metodo più comune di uso delle query compilate. Sono tuttavia possibili altri approcci. Ad esempio, le query compilate possono essere archiviate come membri statici in una classe parziale che estende il codice generato dalla finestra di progettazione.  
  
## <a name="example"></a>Esempio  
 In molti scenari è possibile riutilizzare le query oltre i limiti dei thread. In questi casi l'archiviazione delle query compilate in variabili statiche è particolarmente efficace. Nell'esempio di codice riportato di seguito si presuppone una classe `Queries` progettata per archiviare le query compilate e una classe Northwind che rappresenta un oggetto <xref:System.Data.Linq.DataContext> fortemente tipizzato.  
  
 [!code-csharp[DLinqQuerying#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#6)]
 [!code-vb[DLinqQuerying#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#6)]  
  
 [!code-csharp[DLinqQuerying#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#7)]
 [!code-vb[DLinqQuerying#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#7)]  
  
## <a name="example"></a>Esempio  
 Attualmente non è possibile archiviare (in variabili statiche) le query che restituiscono un *tipo anonimo*, perché il tipo non dispone di alcun nome da fornire come argomento generico. Nell'esempio riportato di seguito viene descritto come risolvere questo problema creando un tipo in grado di rappresentare il risultato, quindi utilizzandolo come argomento generico.  
  
 [!code-csharp[DLinqQuerying#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#8)]
 [!code-vb[DLinqQuerying#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#8)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Data.Linq.CompiledQuery>  
 [Concetti relativi alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [Esecuzione di query sul database](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
