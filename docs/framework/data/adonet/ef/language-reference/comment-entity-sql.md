---
title: -- (commento) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 43b8cdbf5dbca8822645c27711f6984b8d741ea7
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040281"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="1de9e-102">-- (commento) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1de9e-102">-- (Comment) (Entity SQL)</span></span>
<span data-ttu-id="1de9e-103">Le query[!INCLUDE[esql](../../../../../../includes/esql-md.md)] possono contenere commenti.</span><span class="sxs-lookup"><span data-stu-id="1de9e-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries can contain comments.</span></span> <span data-ttu-id="1de9e-104">Due trattini (`--`) indicano l'inizio di una riga di commento.</span><span class="sxs-lookup"><span data-stu-id="1de9e-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1de9e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1de9e-105">Syntax</span></span>  
  
```csharp  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="1de9e-106">argomenti</span><span class="sxs-lookup"><span data-stu-id="1de9e-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="1de9e-107">Stringa di caratteri contenente il testo del commento.</span><span class="sxs-lookup"><span data-stu-id="1de9e-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1de9e-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="1de9e-108">Example</span></span>  
 <span data-ttu-id="1de9e-109">Nella query Entity SQL seguente viene illustrato come usare i commenti.</span><span class="sxs-lookup"><span data-stu-id="1de9e-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="1de9e-110">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="1de9e-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1de9e-111">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1de9e-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="1de9e-112">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="1de9e-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="1de9e-113">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="1de9e-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="1de9e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1de9e-114">See also</span></span>

- [<span data-ttu-id="1de9e-115">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1de9e-115">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="1de9e-116">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1de9e-116">Entity SQL Reference</span></span>](entity-sql-reference.md)
