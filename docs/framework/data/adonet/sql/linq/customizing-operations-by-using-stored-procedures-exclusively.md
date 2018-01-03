---
title: Personalizzazione di operazioni utilizzando esclusivamente stored procedure
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
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: eba9e4462c1a71708173994dfb3efaf4199248c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="5e71c-102">Personalizzazione di operazioni utilizzando esclusivamente stored procedure</span><span class="sxs-lookup"><span data-stu-id="5e71c-102">Customizing Operations by Using Stored Procedures Exclusively</span></span>
<span data-ttu-id="5e71c-103">L'accesso ai dati usando solo stored procedure costituisce uno scenario comune.</span><span class="sxs-lookup"><span data-stu-id="5e71c-103">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e71c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e71c-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="5e71c-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e71c-105">Description</span></span>  
 <span data-ttu-id="5e71c-106">È possibile modificare l'esempio fornito [personalizzazione di operazioni usando Stored procedure](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) sostituendo anche la prima query (che determina l'esecuzione di SQL dinamico) con una chiamata al metodo che esegue il wrapping di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5e71c-106">You can modify the example provided in [Customizing Operations By Using Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="5e71c-107">Si supponga che il metodo sia `CustomersByCity`, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5e71c-107">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5e71c-108">Codice</span><span class="sxs-lookup"><span data-stu-id="5e71c-108">Code</span></span>  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="5e71c-109">Il codice seguente viene eseguito senza SQL dinamico.</span><span class="sxs-lookup"><span data-stu-id="5e71c-109">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="5e71c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e71c-110">See Also</span></span>  
 [<span data-ttu-id="5e71c-111">Responsabilità dello sviluppatore nell'override del comportamento predefinito</span><span class="sxs-lookup"><span data-stu-id="5e71c-111">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
