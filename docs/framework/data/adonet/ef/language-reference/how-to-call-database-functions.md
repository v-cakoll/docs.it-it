---
title: 'Procedura: Chiamare funzioni di database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
ms.openlocfilehash: 5990e9f4c08eafeae6bed18d3d8af0617b84ff54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147927"
---
# <a name="how-to-call-database-functions"></a>Procedura: Chiamare funzioni di database
La classe <xref:System.Data.Objects.SqlClient.SqlFunctions> contiene metodi che espongono funzioni SQL Server da usare nelle query LINQ to Entities. Quando si usano metodi <xref:System.Data.Objects.SqlClient.SqlFunctions> nelle query LINQ to Entities, le funzioni di database corrispondenti vengono eseguite nel database.  
  
> [!NOTE]
>  Le funzioni di database che eseguono un calcolo su un set di valori e restituiscono un valore singolo (anche note come funzioni di database di aggregazione) possono essere richiamate direttamente. Altre funzioni canoniche possono essere chiamate solo come parte di una query LINQ to Entities. Per chiamare direttamente una funzione di aggregazione, è necessario passare un oggetto <xref:System.Data.Objects.ObjectQuery%601> alla funzione. Per altre informazioni, vedere il secondo esempio che segue.  
  
> [!NOTE]
>  Questi metodi nella classe <xref:System.Data.Objects.SqlClient.SqlFunctions> sono specifici delle funzioni SQL Server. Classi simili che espongono funzioni di database possono essere disponibili tramite altri provider.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples). Nell'esempio viene eseguita una query LINQ to Entities che usa il metodo <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> per restituire tutti i contatti il cui cognome inizia con "Si":  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples). Nell'esempio viene chiamato direttamente il metodo di aggregazione <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A>. Si noti che alla funzione viene passato un oggetto <xref:System.Data.Objects.ObjectQuery%601>, che consente alla funzione di essere chiamata senza essere parte di una query LINQ to Entities.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Chiamata di funzioni in query di LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)
- [Query in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
