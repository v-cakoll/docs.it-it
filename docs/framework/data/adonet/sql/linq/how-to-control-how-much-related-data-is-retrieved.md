---
title: 'Procedura: Controllare la quantità di dati correlati recuperata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
ms.openlocfilehash: 2112600dfcef65b1c85445b03806ce8e9cab6a27
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782062"
---
# <a name="how-to-control-how-much-related-data-is-retrieved"></a><span data-ttu-id="d7add-102">Procedura: Controllare la quantità di dati correlati recuperata</span><span class="sxs-lookup"><span data-stu-id="d7add-102">How to: Control How Much Related Data Is Retrieved</span></span>
<span data-ttu-id="d7add-103">Usare il metodo <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> per specificare quali dati correlati alla destinazione principale devono essere recuperati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d7add-103">Use the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to specify which data related to your main target should be retrieved at the same time.</span></span> <span data-ttu-id="d7add-104">Ad esempio, se le informazioni necessarie sono relative agli ordini dei clienti, è possibile usare <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> per assicurarsi che le informazioni sugli ordini vengano recuperate contestualmente alle informazioni sui clienti.</span><span class="sxs-lookup"><span data-stu-id="d7add-104">For example, if you know you will need information about customers' orders, you can use <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> to make sure that the order information is retrieved at the same time as the customer information.</span></span> <span data-ttu-id="d7add-105">Questo approccio comporta un solo accesso al database per entrambi i set di informazioni.</span><span class="sxs-lookup"><span data-stu-id="d7add-105">This approach results in only one trip to the database for both sets of information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7add-106">È possibile recuperare dati riferiti alla destinazione principale della query recuperando un prodotto incrociato come una proiezione estesa, ad esempio gli ordini quando la destinazione della query sono i clienti.</span><span class="sxs-lookup"><span data-stu-id="d7add-106">You can retrieve data related to the main target of your query by retrieving a cross-product as one large projection, such as retrieving orders when you target customers.</span></span> <span data-ttu-id="d7add-107">Questo approccio, tuttavia, presenta spesso svantaggi.</span><span class="sxs-lookup"><span data-stu-id="d7add-107">But this approach often has disadvantages.</span></span> <span data-ttu-id="d7add-108">Ad esempio, i risultati sono solo proiezioni e non entità che possono essere modificate ed essere salvate in modo permanente da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7add-108">For example, the results are just projections and not entities that can be changed and persisted by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="d7add-109">Inoltre è possibile che vengano recuperate grandi quantità di dati non necessari.</span><span class="sxs-lookup"><span data-stu-id="d7add-109">And you can be retrieving lots of data that you do not need.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7add-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7add-110">Example</span></span>  
 <span data-ttu-id="d7add-111">Nell'esempio seguente tutti gli oggetti `Orders` di tutti gli oggetti `Customers` residenti nell'area londinese vengono recuperati quando viene eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="d7add-111">In the following example, all the `Orders` for all the `Customers` who are located in London are retrieved when the query is executed.</span></span> <span data-ttu-id="d7add-112">Di conseguenza, l'accesso successivo alla proprietà `Orders` su un oggetto `Customer` non avvia una nuova query di database.</span><span class="sxs-lookup"><span data-stu-id="d7add-112">As a result, successive access to the `Orders` property on a `Customer` object does not trigger a new database query.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d7add-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7add-113">See also</span></span>

- [<span data-ttu-id="d7add-114">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="d7add-114">Querying the Database</span></span>](querying-the-database.md)
