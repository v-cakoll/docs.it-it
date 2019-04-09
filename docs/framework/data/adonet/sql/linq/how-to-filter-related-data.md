---
title: 'Procedura: Filtrare dati correlati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: 3dbedfb7065ac4b1a570a3f6cdbcdcc2177f20cf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218225"
---
# <a name="how-to-filter-related-data"></a><span data-ttu-id="f8d49-102">Procedura: Filtrare dati correlati</span><span class="sxs-lookup"><span data-stu-id="f8d49-102">How to: Filter Related Data</span></span>
<span data-ttu-id="f8d49-103">Usare il metodo <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> per specificare sottoquery che consentano di limitare la quantità di dati recuperati.</span><span class="sxs-lookup"><span data-stu-id="f8d49-103">Use the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method to specify sub-queries to limit the amount of retrieved data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8d49-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8d49-104">Example</span></span>  
 <span data-ttu-id="f8d49-105">Nell'esempio seguente il metodo <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> limita il numero di `Orders` recuperati a quelli non spediti in data odierna.</span><span class="sxs-lookup"><span data-stu-id="f8d49-105">In the following example, the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method limits the `Orders` retrieved to those that have not been shipped today.</span></span> <span data-ttu-id="f8d49-106">Senza questo approccio verrebbero recuperati tutti gli elementi in `Orders`, anche se è richiesto solo un subset.</span><span class="sxs-lookup"><span data-stu-id="f8d49-106">Without this approach, all `Orders` would have been retrieved even though only a subset is desired.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f8d49-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8d49-107">See also</span></span>

- [<span data-ttu-id="f8d49-108">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="f8d49-108">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
