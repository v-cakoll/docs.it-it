---
title: 'Procedura: eseguire una query che restituisce risultati StructuralType'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2314f2a2-b1c3-40c4-95bb-cdf9b21a7b53
ms.openlocfilehash: f0bfa3e673ec6628e5cf84209544e96e72186515
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-execute-a-query-that-returns-structuraltype-results"></a><span data-ttu-id="0d1fc-102">Procedura: eseguire una query che restituisce risultati StructuralType</span><span class="sxs-lookup"><span data-stu-id="0d1fc-102">How to: Execute a Query that Returns StructuralType Results</span></span>
<span data-ttu-id="0d1fc-103">In questo argomento viene illustrato come eseguire un comando su un modello concettuale usando un oggetto <xref:System.Data.EntityClient.EntityCommand> e viene mostrato come recuperare i risultati di <xref:System.Data.Metadata.Edm.StructuralType> usando un oggetto <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="0d1fc-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.StructuralType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="0d1fc-104">Le classi <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.RowType> e <xref:System.Data.Metadata.Edm.ComplexType> derivano dalla classe <xref:System.Data.Metadata.Edm.StructuralType>.</span><span class="sxs-lookup"><span data-stu-id="0d1fc-104">The <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.RowType> and <xref:System.Data.Metadata.Edm.ComplexType> classes derive from the <xref:System.Data.Metadata.Edm.StructuralType> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="0d1fc-105">Per eseguire il codice in questo esempio</span><span class="sxs-lookup"><span data-stu-id="0d1fc-105">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="0d1fc-106">Aggiungere il [modello Sales di AdventureWorks](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) al progetto e configurare il progetto utilizzerà il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d1fc-106">Add the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="0d1fc-107">Per ulteriori informazioni, vedere [procedura: utilizzare la procedura guidata Entity Data Model](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="0d1fc-107">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="0d1fc-108">Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="0d1fc-108">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="0d1fc-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d1fc-109">Example</span></span>  
 <span data-ttu-id="0d1fc-110">In questo esempio viene eseguita una query che restituisce risultati dell'oggetto <xref:System.Data.Metadata.Edm.EntityType>.</span><span class="sxs-lookup"><span data-stu-id="0d1fc-110">This example executes a query that returns <xref:System.Data.Metadata.Edm.EntityType> results.</span></span> <span data-ttu-id="0d1fc-111">Se si passa la query riportata di seguito come argomento alla funzione `ExecuteStructuralTypeQuery`, quest'ultima visualizza i dettagli relativi a `Products`:</span><span class="sxs-lookup"><span data-stu-id="0d1fc-111">If you pass the following query as an argument to the `ExecuteStructuralTypeQuery` function, the function displays details about the `Products`:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SelectProduct](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#selectproduct)]  
  
 <span data-ttu-id="0d1fc-112">Se si passa una query con parametri, come quella riportata di seguito, aggiungere gli oggetti <xref:System.Data.EntityClient.EntityParameter> alla proprietà <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> nell'oggetto <xref:System.Data.EntityClient.EntityCommand>.</span><span class="sxs-lookup"><span data-stu-id="0d1fc-112">If you pass a parameterized query, like the following, add the <xref:System.Data.EntityClient.EntityParameter> objects to the <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> property on the <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLStructuralTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlstructuraltypes)]
 [!code-vb[DP EntityServices Concepts#eSQLStructuralTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlstructuraltypes)]  
  
## <a name="see-also"></a><span data-ttu-id="0d1fc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d1fc-113">See Also</span></span>  
 [<span data-ttu-id="0d1fc-114">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0d1fc-114">Entity SQL Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="0d1fc-115">Provider EntityClient per Entity Framework</span><span class="sxs-lookup"><span data-stu-id="0d1fc-115">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
