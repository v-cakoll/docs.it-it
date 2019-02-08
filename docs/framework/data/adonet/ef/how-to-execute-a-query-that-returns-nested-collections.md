---
title: 'Procedura: Eseguire una Query che restituisce raccolte annidate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f7f385f3-ffcf-4f3b-af35-de8818938e5f
ms.openlocfilehash: 466187bf340d8cc2088615ae942131658399d65f
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827097"
---
# <a name="how-to-execute-a-query-that-returns-nested-collections"></a><span data-ttu-id="2be05-102">Procedura: Eseguire una Query che restituisce raccolte annidate</span><span class="sxs-lookup"><span data-stu-id="2be05-102">How to: Execute a Query that Returns Nested Collections</span></span>
<span data-ttu-id="2be05-103">In questo argomento viene illustrato come eseguire un comando su un modello concettuale usando un oggetto <xref:System.Data.EntityClient.EntityCommand> e come recuperare i risultati della raccolta annidata usando un oggetto <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="2be05-103">This shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the nested collection results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="2be05-104">Per eseguire il codice in questo esempio</span><span class="sxs-lookup"><span data-stu-id="2be05-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="2be05-105">Aggiungere il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al progetto e configurare il progetto per usare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2be05-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="2be05-106">Per altre informazioni, vedere [Procedura: Usare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="2be05-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="2be05-107">Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="2be05-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="2be05-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="2be05-108">Example</span></span>  
 <span data-ttu-id="2be05-109">Oggetto *annidate raccolta* è una raccolta che si trova all'interno di un'altra raccolta.</span><span class="sxs-lookup"><span data-stu-id="2be05-109">A *nested collection* is a collection that is inside another collection.</span></span> <span data-ttu-id="2be05-110">Nell'esempio seguente vengono recuperate una raccolta di `Contacts` e le raccolte annidate di `SalesOrderHeaders` che sono associate a ciascun `Contact`.</span><span class="sxs-lookup"><span data-stu-id="2be05-110">The following code retrieves a collection of `Contacts` and the nested collections of `SalesOrderHeaders` that are associated with each `Contact`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#returnnestedcollectionwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#returnnestedcollectionwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="2be05-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2be05-111">See also</span></span>
- [<span data-ttu-id="2be05-112">Provider EntityClient per Entity Framework</span><span class="sxs-lookup"><span data-stu-id="2be05-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
