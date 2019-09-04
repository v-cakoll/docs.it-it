---
title: Aggiunta di logica di business mediante metodi parziali
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: 251d7a05971ff7940f85ec9d555d26f2e57067c3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248128"
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="fcea8-102">Aggiunta di logica di business mediante metodi parziali</span><span class="sxs-lookup"><span data-stu-id="fcea8-102">Adding Business Logic By Using Partial Methods</span></span>
<span data-ttu-id="fcea8-103">È possibile personalizzare Visual Basic e C# il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] codice generato nei progetti usando *metodi parziali*.</span><span class="sxs-lookup"><span data-stu-id="fcea8-103">You can customize Visual Basic and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="fcea8-104">Il codice generato da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] definisce le firme come una parte di un metodo parziale.</span><span class="sxs-lookup"><span data-stu-id="fcea8-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="fcea8-105">Se si desidera implementare il metodo, è possibile aggiungere un metodo parziale personalizzato.</span><span class="sxs-lookup"><span data-stu-id="fcea8-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="fcea8-106">Se non si aggiunge un'implementazione personalizzata, il compilatore ignora la firma dei metodi parziali e chiama i metodi predefiniti in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcea8-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fcea8-107">Se si usa Visual Studio, è possibile usare la Object Relational Designer per aggiungere la convalida e altre personalizzazioni alle classi di entità.</span><span class="sxs-lookup"><span data-stu-id="fcea8-107">If you are using Visual Studio, you can use the Object Relational Designer to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="fcea8-108">Ad esempio, il mapping predefinito per la classe `Customer` nel database di esempio Northwind include il seguente metodo parziale:</span><span class="sxs-lookup"><span data-stu-id="fcea8-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="fcea8-109">È possibile implementare un metodo personalizzato aggiungendo codice analogo al seguente alla classe parziale personalizzata `Customer`:</span><span class="sxs-lookup"><span data-stu-id="fcea8-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="fcea8-110">Questo approccio viene in genere usato [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in per eseguire l'override `Insert`dei metodi `Delete`predefiniti per, `Update`, e per convalidare le proprietà durante gli eventi del ciclo di vita dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="fcea8-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="fcea8-111">Per ulteriori informazioni, vedere [metodi parziali](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) o [partial (MethodC# ) (Reference)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#).</span><span class="sxs-lookup"><span data-stu-id="fcea8-111">For more information, see [Partial Methods](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) or [partial (Method) (C# Reference)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcea8-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcea8-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="fcea8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcea8-113">Description</span></span>  
 <span data-ttu-id="fcea8-114">Nell'esempio riportato di seguito viene illustrato innanzitutto come definire `ExampleClass` usando uno strumento per la generazione di codice quale SQLMetal, quindi come è possibile implementare solo uno dei due metodi.</span><span class="sxs-lookup"><span data-stu-id="fcea8-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="fcea8-115">Codice</span><span class="sxs-lookup"><span data-stu-id="fcea8-115">Code</span></span>  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="fcea8-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcea8-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="fcea8-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="fcea8-117">Description</span></span>  
 <span data-ttu-id="fcea8-118">Nell'esempio riportato di seguito viene usata la relazione tra le entità `Shipper` e `Order`.</span><span class="sxs-lookup"><span data-stu-id="fcea8-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="fcea8-119">Notare fra i metodi i metodi parziali `InsertShipper` e `DeleteShipper`.</span><span class="sxs-lookup"><span data-stu-id="fcea8-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="fcea8-120">Questi metodi eseguono l'override dei metodi parziali [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] predefiniti forniti dal mapping.</span><span class="sxs-lookup"><span data-stu-id="fcea8-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="fcea8-121">Codice</span><span class="sxs-lookup"><span data-stu-id="fcea8-121">Code</span></span>  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fcea8-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcea8-122">See also</span></span>

- [<span data-ttu-id="fcea8-123">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="fcea8-123">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="fcea8-124">Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione</span><span class="sxs-lookup"><span data-stu-id="fcea8-124">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)
