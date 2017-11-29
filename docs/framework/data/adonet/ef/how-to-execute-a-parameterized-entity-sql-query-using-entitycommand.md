---
title: 'Procedura: eseguire una query Entity SQL con parametri tramite EntityCommand'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f1531e18a6be3e7ab5c0cec4f19f33692fd04383
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a><span data-ttu-id="f0f09-102">Procedura: eseguire una query Entity SQL con parametri tramite EntityCommand</span><span class="sxs-lookup"><span data-stu-id="f0f09-102">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>
<span data-ttu-id="f0f09-103">In questo argomento viene illustrato come eseguire un [!INCLUDE[esql](../../../../../includes/esql-md.md)] query con parametri usando un <xref:System.Data.EntityClient.EntityCommand> oggetto.</span><span class="sxs-lookup"><span data-stu-id="f0f09-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that has parameters by using an <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="f0f09-104">Per eseguire il codice in questo esempio</span><span class="sxs-lookup"><span data-stu-id="f0f09-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="f0f09-105">Aggiungere il [modello Sales di AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) al progetto e configurare il progetto utilizzerà il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0f09-105">Add the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="f0f09-106">Per ulteriori informazioni, vedere [procedura: utilizzare la procedura guidata Entity Data Model](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="f0f09-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="f0f09-107">Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="f0f09-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="f0f09-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0f09-108">Example</span></span>  
 <span data-ttu-id="f0f09-109">Nell'esempio seguente viene illustrato come costruire una stringa di query con due parametri.</span><span class="sxs-lookup"><span data-stu-id="f0f09-109">The following example shows how to construct a query string with two parameters.</span></span> <span data-ttu-id="f0f09-110">Viene quindi creato un oggetto <xref:System.Data.EntityClient.EntityCommand>, vengono aggiunti due parametri alla raccolta <xref:System.Data.EntityClient.EntityParameter> di <xref:System.Data.EntityClient.EntityCommand> e viene scorsa la raccolta di elementi `Contact`.</span><span class="sxs-lookup"><span data-stu-id="f0f09-110">It then creates an <xref:System.Data.EntityClient.EntityCommand>, adds two parameters to the <xref:System.Data.EntityClient.EntityParameter> collection of that <xref:System.Data.EntityClient.EntityCommand>, and iterates through the collection of `Contact` items.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="f0f09-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0f09-111">See Also</span></span>  
 [<span data-ttu-id="f0f09-112">Procedura: eseguire una Query con parametri</span><span class="sxs-lookup"><span data-stu-id="f0f09-112">How to: Execute a Parameterized Query</span></span>](http://msdn.microsoft.com/en-us/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
 [<span data-ttu-id="f0f09-113">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f0f09-113">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
