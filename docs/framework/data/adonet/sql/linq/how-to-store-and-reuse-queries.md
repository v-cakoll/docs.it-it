---
title: 'Procedura: Archiviare e riutilizzare query'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a012bd79-1809-45e3-adea-0229532396cc
ms.openlocfilehash: 1aac20c3f9c421d353938a83b9e321d35abd244e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033644"
---
# <a name="how-to-store-and-reuse-queries"></a>Procedura: Archiviare e riutilizzare query
Quando si usa un'applicazione che esegue molte volte query strutturalmente simili, è spesso possibile migliorare le prestazioni compilando la query una volta ed eseguendola più volte con parametri diversi. Un'applicazione potrebbe ad esempio essere usata per recuperare tutti i clienti di una determinata città, specificata in fase di runtime dall'utente in un modulo. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta l'utilizzo delle *query compilate* per questo scopo.  
  
> [!NOTE]
>  Questo modello di utilizzo rappresenta il metodo più comune di uso delle query compilate. Sono tuttavia possibili altri approcci. Ad esempio, le query compilate possono essere archiviate come membri statici in una classe parziale che estende il codice generato dalla finestra di progettazione.  
  
## <a name="example"></a>Esempio  
 In molti scenari è possibile riutilizzare le query oltre i limiti dei thread. In questi casi l'archiviazione delle query compilate in variabili statiche è particolarmente efficace. Nell'esempio di codice riportato di seguito si presuppone una classe `Queries` progettata per archiviare le query compilate e una classe Northwind che rappresenta un oggetto <xref:System.Data.Linq.DataContext> fortemente tipizzato.  
  
 [!code-csharp[DLinqQuerying#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#6)]
 [!code-vb[DLinqQuerying#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#6)]  
  
 [!code-csharp[DLinqQuerying#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#7)]
 [!code-vb[DLinqQuerying#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#7)]  
  
## <a name="example"></a>Esempio  
 Attualmente non è possibile query store (in variabili statiche) che restituiscono un *tipo anonimo*, perché non hanno nome da fornire come argomento generico. Nell'esempio riportato di seguito viene descritto come risolvere questo problema creando un tipo in grado di rappresentare il risultato, quindi utilizzandolo come argomento generico.  
  
 [!code-csharp[DLinqQuerying#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#8)]
 [!code-vb[DLinqQuerying#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#8)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.Linq.CompiledQuery>
- [Concetti relativi alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [Esecuzione di query sul database](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
