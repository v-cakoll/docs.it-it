---
title: "Procedura: Esplorare relazioni con l'operatore NAVIGATE"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
ms.openlocfilehash: c8c23e00112859ffa9949d268c3263f73d3a714f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251426"
---
# <a name="how-to-navigate-relationships-with-the-navigate-operator"></a>Procedura: Esplorare relazioni con l'operatore NAVIGATE
In questo argomento viene illustrato come eseguire un comando su un modello concettuale usando un oggetto <xref:System.Data.EntityClient.EntityCommand> e viene mostrato come recuperare i risultati di <xref:System.Data.Metadata.Edm.RefType> usando un oggetto <xref:System.Data.EntityClient.EntityDataReader>.  
  
### <a name="to-run-the-code-in-this-example"></a>Per eseguire il codice in questo esempio  
  
1. Aggiungere il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al progetto e configurare il progetto per l' [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]utilizzo di. Per altre informazioni, vedere [Procedura: Utilizzare la procedura guidata](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))Entity Data Model.  
  
2. Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come spostarsi tra le [!INCLUDE[esql](../../../../../includes/esql-md.md)] relazioni in utilizzando l'operatore [Navigate](./language-reference/navigate-entity-sql.md) . L' `Navigate` operatore accetta i parametri seguenti: un'istanza di un'entità, il tipo di relazione, l'entità finale della relazione e l'inizio della relazione. Facoltativamente, è possibile passare all' `Navigate` operatore solo un'istanza di un'entità e il tipo di relazione.  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## <a name="see-also"></a>Vedere anche

- [Provider EntityClient per Entity Framework](entityclient-provider-for-the-entity-framework.md)
- [Linguaggio Entity SQL](./language-reference/entity-sql-language.md)
