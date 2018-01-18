---
title: "Procedura: controllare la quantità di dati correlati recuperata"
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
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3beb6f6b019535e273df7103e2e22f1be669797a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-control-how-much-related-data-is-retrieved"></a><span data-ttu-id="107e5-102">Procedura: controllare la quantità di dati correlati recuperata</span><span class="sxs-lookup"><span data-stu-id="107e5-102">How to: Control How Much Related Data Is Retrieved</span></span>
<span data-ttu-id="107e5-103">Usare il metodo <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> per specificare quali dati correlati alla destinazione principale devono essere recuperati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="107e5-103">Use the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to specify which data related to your main target should be retrieved at the same time.</span></span> <span data-ttu-id="107e5-104">Ad esempio, se le informazioni necessarie sono relative agli ordini dei clienti, è possibile usare <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> per assicurarsi che le informazioni sugli ordini vengano recuperate contestualmente alle informazioni sui clienti.</span><span class="sxs-lookup"><span data-stu-id="107e5-104">For example, if you know you will need information about customers' orders, you can use <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> to make sure that the order information is retrieved at the same time as the customer information.</span></span> <span data-ttu-id="107e5-105">Questo approccio comporta un solo accesso al database per entrambi i set di informazioni.</span><span class="sxs-lookup"><span data-stu-id="107e5-105">This approach results in only one trip to the database for both sets of information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="107e5-106">È possibile recuperare dati riferiti alla destinazione principale della query recuperando un prodotto incrociato come una proiezione estesa, ad esempio gli ordini quando la destinazione della query sono i clienti.</span><span class="sxs-lookup"><span data-stu-id="107e5-106">You can retrieve data related to the main target of your query by retrieving a cross-product as one large projection, such as retrieving orders when you target customers.</span></span> <span data-ttu-id="107e5-107">Questo approccio, tuttavia, presenta spesso svantaggi.</span><span class="sxs-lookup"><span data-stu-id="107e5-107">But this approach often has disadvantages.</span></span> <span data-ttu-id="107e5-108">Ad esempio, i risultati sono solo proiezioni e non entità che possono essere modificate ed essere salvate in modo permanente da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="107e5-108">For example, the results are just projections and not entities that can be changed and persisted by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="107e5-109">Inoltre è possibile che vengano recuperate grandi quantità di dati non necessari.</span><span class="sxs-lookup"><span data-stu-id="107e5-109">And you can be retrieving lots of data that you do not need.</span></span>  
  
## <a name="example"></a><span data-ttu-id="107e5-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="107e5-110">Example</span></span>  
 <span data-ttu-id="107e5-111">Nell'esempio seguente tutti gli oggetti `Orders` di tutti gli oggetti `Customers` residenti nell'area londinese vengono recuperati quando viene eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="107e5-111">In the following example, all the `Orders` for all the `Customers` who are located in London are retrieved when the query is executed.</span></span> <span data-ttu-id="107e5-112">Di conseguenza, l'accesso successivo alla proprietà `Orders` su un oggetto `Customer` non avvia una nuova query di database.</span><span class="sxs-lookup"><span data-stu-id="107e5-112">As a result, successive access to the `Orders` property on a `Customer` object does not trigger a new database query.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="107e5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="107e5-113">See Also</span></span>  
 [<span data-ttu-id="107e5-114">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="107e5-114">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
