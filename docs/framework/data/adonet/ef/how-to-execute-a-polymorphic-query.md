---
title: 'Procedura: eseguire una query polimorfica'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: ae491d0eeda7f8703dca174bdf4c5c847f78e675
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519082"
---
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="03635-102">Procedura: eseguire una query polimorfica</span><span class="sxs-lookup"><span data-stu-id="03635-102">How to: Execute a Polymorphic Query</span></span>
<span data-ttu-id="03635-103">In questo argomento viene illustrato come eseguire un polimorfico [!INCLUDE[esql](../../../../../includes/esql-md.md)] eseguire query usando il [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operatore.</span><span class="sxs-lookup"><span data-stu-id="03635-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="03635-104">Per eseguire il codice in questo esempio</span><span class="sxs-lookup"><span data-stu-id="03635-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="03635-105">Aggiungere il [modello School](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) al progetto e configurare il progetto per l'utilizzo di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="03635-105">Add the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="03635-106">Per altre informazioni, vedere [procedura: usare la procedura guidata Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="03635-106">For more information, see [How to: Use the Entity Data Model Wizard](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="03635-107">Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="03635-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="03635-108">Modificare il modello concettuale per creare un'ereditarietà tabella-per-gerarchia seguendo i passaggi descritti in [procedura dettagliata: Mapping di ereditarietà: tabella per gerarchia](https://msdn.microsoft.com/library/49b685cf-9db8-4d6d-b885-8837ed238f55).</span><span class="sxs-lookup"><span data-stu-id="03635-108">Modify the conceptual model to have a table-per-hierrachy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](https://msdn.microsoft.com/library/49b685cf-9db8-4d6d-b885-8837ed238f55).</span></span>  
  
## <a name="example"></a><span data-ttu-id="03635-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="03635-109">Example</span></span>  
 <span data-ttu-id="03635-110">Nell'esempio seguente viene usato un operatore OFTYPE per ottenere e visualizzare una raccolta di soli oggetti `OnsiteCourses` da una raccolta di oggetti `Courses`.</span><span class="sxs-lookup"><span data-stu-id="03635-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## <a name="see-also"></a><span data-ttu-id="03635-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03635-111">See Also</span></span>  
 [<span data-ttu-id="03635-112">Provider EntityClient per Entity Framework</span><span class="sxs-lookup"><span data-stu-id="03635-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
 [<span data-ttu-id="03635-113">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="03635-113">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
