---
title: 'Procedura: eseguire una query che restituisce raccolte annidate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f7f385f3-ffcf-4f3b-af35-de8818938e5f
ms.openlocfilehash: 5e282bce5f2519592babad0afcf7f8a326cf936d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530568"
---
# <a name="how-to-execute-a-query-that-returns-nested-collections"></a>Procedura: eseguire una query che restituisce raccolte annidate
In questo argomento viene illustrato come eseguire un comando su un modello concettuale usando un oggetto <xref:System.Data.EntityClient.EntityCommand> e come recuperare i risultati della raccolta annidata usando un oggetto <xref:System.Data.EntityClient.EntityDataReader>.  
  
### <a name="to-run-the-code-in-this-example"></a>Per eseguire il codice in questo esempio  
  
1.  Aggiungere il [modello Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) al progetto e configurare il progetto per usare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Per altre informazioni, vedere [procedura: usare la procedura guidata Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Esempio  
 Oggetto *annidate raccolta* è una raccolta che si trova all'interno di un'altra raccolta. Nell'esempio seguente vengono recuperate una raccolta di `Contacts` e le raccolte annidate di `SalesOrderHeaders` che sono associate a ciascun `Contact`.  
  
 [!code-csharp[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#returnnestedcollectionwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#returnnestedcollectionwithentitycommand)]  
  
## <a name="see-also"></a>Vedere anche  
 [Provider EntityClient per Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
