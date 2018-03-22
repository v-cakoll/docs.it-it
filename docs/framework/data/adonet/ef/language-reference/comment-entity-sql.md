---
title: -- (commento) (Entity SQL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 1ed1c70687b1a4aec542aff5046b237fa4710fa4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="4a775-102">-- (commento) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4a775-102">-- (Comment) (Entity SQL)</span></span>
<span data-ttu-id="4a775-103">Le query[!INCLUDE[esql](../../../../../../includes/esql-md.md)] possono contenere commenti.</span><span class="sxs-lookup"><span data-stu-id="4a775-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries can contain comments.</span></span> <span data-ttu-id="4a775-104">Due trattini (`--`) indicano l'inizio di una riga di commento.</span><span class="sxs-lookup"><span data-stu-id="4a775-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a775-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a775-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="4a775-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4a775-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="4a775-107">Stringa di caratteri contenente il testo del commento.</span><span class="sxs-lookup"><span data-stu-id="4a775-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a775-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a775-108">Example</span></span>  
 <span data-ttu-id="4a775-109">Nella query Entity SQL seguente viene illustrato come usare i commenti.</span><span class="sxs-lookup"><span data-stu-id="4a775-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="4a775-110">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4a775-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4a775-111">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a775-111">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="4a775-112">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="4a775-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="4a775-113">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="4a775-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="4a775-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a775-114">See Also</span></span>  
 [<span data-ttu-id="4a775-115">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="4a775-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="4a775-116">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="4a775-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
