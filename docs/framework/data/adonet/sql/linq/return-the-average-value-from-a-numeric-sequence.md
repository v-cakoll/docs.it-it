---
title: Restituire il valore medio da una sequenza numerica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee3b8673-a2e7-4b2d-9b5c-4972ff9e665d
ms.openlocfilehash: eea1439337b29fee51c422238425491fc2345211
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095087"
---
# <a name="return-the-average-value-from-a-numeric-sequence"></a><span data-ttu-id="4b6db-102">Restituire il valore medio da una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="4b6db-102">Return the Average Value From a Numeric Sequence</span></span>
<span data-ttu-id="4b6db-103">L'operatore <xref:System.Linq.Enumerable.Average%2A> calcola la media di una sequenza di valori numerici.</span><span class="sxs-lookup"><span data-stu-id="4b6db-103">The <xref:System.Linq.Enumerable.Average%2A> operator computes the average of a sequence of numeric values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b6db-104">La conversione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] di `Average` di valori integer viene calcolata come un valore integer, non come un valore double.</span><span class="sxs-lookup"><span data-stu-id="4b6db-104">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of `Average` of integer values is computed as an integer, not as a double.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b6db-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b6db-105">Example</span></span>  
 <span data-ttu-id="4b6db-106">Nell'esempio seguente viene restituita la media dei valori `Freight` nella tabella `Orders`.</span><span class="sxs-lookup"><span data-stu-id="4b6db-106">The following example returns the average of `Freight` values in the `Orders` table.</span></span>  
  
 <span data-ttu-id="4b6db-107">Il risultato restituito dal database Northwind di esempio sarà `78.2442`.</span><span class="sxs-lookup"><span data-stu-id="4b6db-107">Results from the sample Northwind database would be `78.2442`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#1)]
 [!code-vb[DLinqQueryExamples#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="4b6db-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b6db-108">Example</span></span>  
 <span data-ttu-id="4b6db-109">Nell'esempio seguente viene restituito il prezzo unitario medio di tutti i valori `Products` nella tabella `Products`.</span><span class="sxs-lookup"><span data-stu-id="4b6db-109">The following example returns the average of the unit price of all `Products` in the `Products` table.</span></span>  
  
 <span data-ttu-id="4b6db-110">Il risultato restituito dal database Northwind di esempio sarà `28.8663`.</span><span class="sxs-lookup"><span data-stu-id="4b6db-110">Results from the sample Northwind database would be `28.8663`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#2)]
 [!code-vb[DLinqQueryExamples#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="4b6db-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b6db-111">Example</span></span>  
 <span data-ttu-id="4b6db-112">Nell'esempio seguente viene usato l'operatore `Average` per trovare i valori `Products` il cui prezzo unitario è maggiore del prezzo unitario medio della categoria a cui appartengono tali prodotti.</span><span class="sxs-lookup"><span data-stu-id="4b6db-112">The following example uses the `Average` operator to find those `Products` whose unit price is higher than the average unit price of the category it belongs to.</span></span> <span data-ttu-id="4b6db-113">Nell'esempio i risultati vengono visualizzati in gruppi.</span><span class="sxs-lookup"><span data-stu-id="4b6db-113">The example then displays the results in groups.</span></span>  
  
 <span data-ttu-id="4b6db-114">Notare che in questo esempio è richiesto l'uso della parola chiave `var` in C#, perché il tipo restituito è anonimo.</span><span class="sxs-lookup"><span data-stu-id="4b6db-114">Note that this example requires the use of the `var` keyword in C#, because the return type is anonymous.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#3)]
 [!code-vb[DLinqQueryExamples#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#3)]  
  
 <span data-ttu-id="4b6db-115">Se si esegue questa query sul database di esempio Northwind, i risultati saranno simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b6db-115">If you run this query against the Northwind sample database, the results should resemble of the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `Ipoh Coffee`  
  
 `2`  
  
 `Grandma's Boysenberry Spread`  
  
 `Northwoods Cranberry Sauce`  
  
 `Sirop d'érable`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `Gumbär Gummibärchen`  
  
 `Schoggi Schokolade`  
  
 `Tarte au sucre`  
  
 `4`  
  
 `Queso Manchego La Pastora`  
  
 `Mascarpone Fabioli`  
  
 `Raclette Courdavault`  
  
 `Camembert Pierrot`  
  
 `Gudbrandsdalsost`  
  
 `Mozzarella di Giovanni`  
  
 `5`  
  
 `Gustaf's Knäckebröd`  
  
 `Gnocchi di nonna Alice`  
  
 `Wimmers gute Semmelknödel`  
  
 `6`  
  
 `Mishi Kobe Niku`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Rössle Sauerkraut`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Ikura`  
  
 `Carnarvon Tigers`  
  
 `Nord-Ost Matjeshering`  
  
 `Gravad lax`  
  
## <a name="see-also"></a><span data-ttu-id="4b6db-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b6db-116">See also</span></span>

- [<span data-ttu-id="4b6db-117">Query di aggregazione</span><span class="sxs-lookup"><span data-stu-id="4b6db-117">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)
