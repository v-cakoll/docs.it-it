---
title: 'Procedura: Eseguire una Query polimorfica'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 01619e556750a93910afefed4b5647818f6a9d92
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826239"
---
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="c7e53-102">Procedura: Eseguire una Query polimorfica</span><span class="sxs-lookup"><span data-stu-id="c7e53-102">How to: Execute a Polymorphic Query</span></span>
<span data-ttu-id="c7e53-103">In questo argomento viene illustrato come eseguire un polimorfico [!INCLUDE[esql](../../../../../includes/esql-md.md)] eseguire query usando il [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operatore.</span><span class="sxs-lookup"><span data-stu-id="c7e53-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="c7e53-104">Per eseguire il codice in questo esempio</span><span class="sxs-lookup"><span data-stu-id="c7e53-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="c7e53-105">Aggiungere il [modello School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) al progetto e configurare il progetto per l'utilizzo di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="c7e53-105">Add the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="c7e53-106">Per altre informazioni, vedere [Procedura: Usare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c7e53-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="c7e53-107">Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="c7e53-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="c7e53-108">Modificare il modello concettuale per creare un'ereditarietà tabella-per-gerarchia seguendo i passaggi descritti in [procedura dettagliata: Il mapping dell'ereditarietà: tabella per gerarchia](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c7e53-108">Modify the conceptual model to have a table-per-hierrachy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7e53-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="c7e53-109">Example</span></span>  
 <span data-ttu-id="c7e53-110">Nell'esempio seguente viene usato un operatore OFTYPE per ottenere e visualizzare una raccolta di soli oggetti `OnsiteCourses` da una raccolta di oggetti `Courses`.</span><span class="sxs-lookup"><span data-stu-id="c7e53-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## <a name="see-also"></a><span data-ttu-id="c7e53-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7e53-111">See also</span></span>
- [<span data-ttu-id="c7e53-112">Provider EntityClient per Entity Framework</span><span class="sxs-lookup"><span data-stu-id="c7e53-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="c7e53-113">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c7e53-113">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
