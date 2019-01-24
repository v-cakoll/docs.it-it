---
title: 'Procedura: Rappresentare colonne come membri di classi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: 7a772de27583f35b18a4fa5854e61768443e5ba5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652559"
---
# <a name="how-to-represent-columns-as-class-members"></a><span data-ttu-id="d821a-102">Procedura: Rappresentare colonne come membri di classi</span><span class="sxs-lookup"><span data-stu-id="d821a-102">How to: Represent Columns as Class Members</span></span>
<span data-ttu-id="d821a-103">Usare la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attributo per associare un campo o proprietà a una colonna del database.</span><span class="sxs-lookup"><span data-stu-id="d821a-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to associate a field or property with a database column.</span></span>  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a><span data-ttu-id="d821a-104">Per eseguire il mapping di un campo o una proprietà a una colonna del database</span><span class="sxs-lookup"><span data-stu-id="d821a-104">To map a field or property to a database column</span></span>  
  
-   <span data-ttu-id="d821a-105">Aggiungere l'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute> alla dichiarazione del campo o della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d821a-105">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to the property or field declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d821a-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d821a-106">Example</span></span>  
 <span data-ttu-id="d821a-107">Nelle mappe del codice riportate di seguito viene eseguito il mapping del campo `CustomerID` nella classe `Customer` alla colonna `CustomerID` nella tabella di database `Customers`.</span><span class="sxs-lookup"><span data-stu-id="d821a-107">The following code maps the `CustomerID` field in the `Customer` class to the `CustomerID` column in the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 <span data-ttu-id="d821a-108">Non è necessario specificare la proprietà <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> se il nome può essere dedotto.</span><span class="sxs-lookup"><span data-stu-id="d821a-108">You do not have to specify the <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="d821a-109">Se non si specifica un nome, verrà usato lo stesso nome della proprietà o del campo.</span><span class="sxs-lookup"><span data-stu-id="d821a-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d821a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d821a-110">See also</span></span>
- [<span data-ttu-id="d821a-111">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d821a-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="d821a-112">Procedura: Personalizzare le classi di entità usando l'Editor di codice</span><span class="sxs-lookup"><span data-stu-id="d821a-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
