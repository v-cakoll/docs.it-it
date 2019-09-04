---
title: 'Procedura: Eseguire una query Entity SQL con parametri tramite EntityCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
ms.openlocfilehash: addda1a18ab325971b823d0131338a7bb824ad5c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251536"
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a>Procedura: Eseguire una query Entity SQL con parametri tramite EntityCommand
In questo argomento viene illustrato come eseguire [!INCLUDE[esql](../../../../../includes/esql-md.md)] una query con parametri utilizzando un <xref:System.Data.EntityClient.EntityCommand> oggetto.  
  
### <a name="to-run-the-code-in-this-example"></a>Per eseguire il codice in questo esempio  
  
1. Aggiungere il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al progetto e configurare il progetto per l' [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]utilizzo di. Per altre informazioni, vedere [Procedura: Utilizzare la procedura guidata](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))Entity Data Model.  
  
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
