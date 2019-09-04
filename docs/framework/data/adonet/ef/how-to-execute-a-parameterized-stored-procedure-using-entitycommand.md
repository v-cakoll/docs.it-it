---
title: 'Procedura: Eseguire una stored procedure con parametri tramite EntityCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: a2196be1a5fb6b9c676542ab5bcc74b1824df9cc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251517"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a>Procedura: Eseguire una stored procedure con parametri tramite EntityCommand
In questo argomento viene mostrato come eseguire una stored procedure con parametri usando la classe <xref:System.Data.EntityClient.EntityCommand>.  
  
### <a name="to-run-the-code-in-this-example"></a>Per eseguire il codice in questo esempio  
  
1. Aggiungere il [modello School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) al progetto e configurare il progetto per l' [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]uso di. Per altre informazioni, vedere [Procedura: Utilizzare la procedura guidata](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))Entity Data Model.  
  
2. Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. Importare la stored procedure `GetStudentGrades` e specificare entità `CourseGrade` come tipo restituito. Per informazioni su come importare una stored procedure, vedere [procedura: Importare una stored procedure](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100)).  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene eseguita la stored procedure `GetStudentGrades`, dove `StudentId` è un parametro obbligatorio. I risultati vengono quindi letti da <xref:System.Data.EntityClient.EntityDataReader>.  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a>Vedere anche

- [Provider EntityClient per Entity Framework](entityclient-provider-for-the-entity-framework.md)
