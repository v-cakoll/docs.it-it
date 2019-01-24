---
title: -- (commento) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 477a5f9aefeec46766a93c1e6ae9f3ecb3c3677f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705686"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="2c69d-102">-- (commento) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2c69d-102">-- (Comment) (Entity SQL)</span></span>
<span data-ttu-id="2c69d-103">Le query[!INCLUDE[esql](../../../../../../includes/esql-md.md)] possono contenere commenti.</span><span class="sxs-lookup"><span data-stu-id="2c69d-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries can contain comments.</span></span> <span data-ttu-id="2c69d-104">Due trattini (`--`) indicano l'inizio di una riga di commento.</span><span class="sxs-lookup"><span data-stu-id="2c69d-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c69d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c69d-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="2c69d-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2c69d-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="2c69d-107">Stringa di caratteri contenente il testo del commento.</span><span class="sxs-lookup"><span data-stu-id="2c69d-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c69d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c69d-108">Example</span></span>  
 <span data-ttu-id="2c69d-109">Nella query Entity SQL seguente viene illustrato come usare i commenti.</span><span class="sxs-lookup"><span data-stu-id="2c69d-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="2c69d-110">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2c69d-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2c69d-111">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c69d-111">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="2c69d-112">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2c69d-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="2c69d-113">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="2c69d-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="2c69d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c69d-114">See also</span></span>
- [<span data-ttu-id="2c69d-115">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2c69d-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="2c69d-116">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2c69d-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
