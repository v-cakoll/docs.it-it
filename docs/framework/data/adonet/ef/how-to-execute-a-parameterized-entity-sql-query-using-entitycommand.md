---
title: 'Procedura: Eseguire una query Entity SQL con parametri tramite EntityCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
ms.openlocfilehash: aa750ef088ee045c8d1045b2509d8fc4bde014ce
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854636"
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a>Procedura: Eseguire una query Entity SQL con parametri tramite EntityCommand
In questo argomento viene illustrato come eseguire [!INCLUDE[esql](../../../../../includes/esql-md.md)] una query con parametri utilizzando un <xref:System.Data.EntityClient.EntityCommand> oggetto.  
  
### <a name="to-run-the-code-in-this-example"></a>Per eseguire il codice in questo esempio  
  
1. Aggiungere il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al progetto e configurare il progetto per l'utilizzo del Entity Framework. Per altre informazioni, vedere [Procedura: Utilizzare la procedura guidata](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))Entity Data Model.  
  
2. Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come costruire una stringa di query con due parametri. Viene quindi creato un oggetto <xref:System.Data.EntityClient.EntityCommand>, vengono aggiunti due parametri alla raccolta <xref:System.Data.EntityClient.EntityParameter> di <xref:System.Data.EntityClient.EntityCommand> e viene scorsa la raccolta di elementi `Contact`.  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Eseguire una query con parametri](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))
- [Linguaggio Entity SQL](./language-reference/entity-sql-language.md)
