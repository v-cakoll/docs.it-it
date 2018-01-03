---
title: Aggiunta di logica di business mediante metodi parziali
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
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8c2ff5818aaa22aa51781d09952432fc91a8163c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="51c4e-102">Aggiunta di logica di business mediante metodi parziali</span><span class="sxs-lookup"><span data-stu-id="51c4e-102">Adding Business Logic By Using Partial Methods</span></span>
<span data-ttu-id="51c4e-103">È possibile personalizzare [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] e il codice in c# generato il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetti utilizzando *metodi parziali*.</span><span class="sxs-lookup"><span data-stu-id="51c4e-103">You can customize [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="51c4e-104">Il codice generato da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] definisce le firme come una parte di un metodo parziale.</span><span class="sxs-lookup"><span data-stu-id="51c4e-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="51c4e-105">Se si desidera implementare il metodo, è possibile aggiungere un metodo parziale personalizzato.</span><span class="sxs-lookup"><span data-stu-id="51c4e-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="51c4e-106">Se non si aggiunge un'implementazione personalizzata, il compilatore ignora la firma dei metodi parziali e chiama i metodi predefiniti in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51c4e-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51c4e-107">Se si usa [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], è possibile usare la [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per aggiungere la convalida e altre personalizzazioni alle classi di entità.</span><span class="sxs-lookup"><span data-stu-id="51c4e-107">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="51c4e-108">Ad esempio, il mapping predefinito per la classe `Customer` nel database di esempio Northwind include il seguente metodo parziale:</span><span class="sxs-lookup"><span data-stu-id="51c4e-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="51c4e-109">È possibile implementare un metodo personalizzato aggiungendo codice analogo al seguente alla classe parziale personalizzata `Customer`:</span><span class="sxs-lookup"><span data-stu-id="51c4e-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="51c4e-110">Questo approccio viene utilizzato in genere [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per eseguire l'override di metodi predefiniti per `Insert`, `Update`, `Delete`e per convalidare le proprietà durante gli eventi del ciclo di vita di oggetto.</span><span class="sxs-lookup"><span data-stu-id="51c4e-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="51c4e-111">Per ulteriori informazioni, vedere [metodi parziali](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) o [parziale (metodo) (riferimenti per c#)](~/docs/csharp/language-reference/keywords/partial-method.md) (c#).</span><span class="sxs-lookup"><span data-stu-id="51c4e-111">For more information, see [Partial Methods](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) or [partial (Method) (C# Reference)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="51c4e-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="51c4e-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="51c4e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51c4e-113">Description</span></span>  
 <span data-ttu-id="51c4e-114">Nell'esempio riportato di seguito viene illustrato innanzitutto come definire `ExampleClass` usando uno strumento per la generazione di codice quale SQLMetal, quindi come è possibile implementare solo uno dei due metodi.</span><span class="sxs-lookup"><span data-stu-id="51c4e-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="51c4e-115">Codice</span><span class="sxs-lookup"><span data-stu-id="51c4e-115">Code</span></span>  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="51c4e-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="51c4e-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="51c4e-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51c4e-117">Description</span></span>  
 <span data-ttu-id="51c4e-118">Nell'esempio riportato di seguito viene usata la relazione tra le entità `Shipper` e `Order`.</span><span class="sxs-lookup"><span data-stu-id="51c4e-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="51c4e-119">Notare fra i metodi i metodi parziali `InsertShipper` e `DeleteShipper`.</span><span class="sxs-lookup"><span data-stu-id="51c4e-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="51c4e-120">Questi metodi eseguono l'override dei metodi parziali predefiniti forniti da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span><span class="sxs-lookup"><span data-stu-id="51c4e-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="51c4e-121">Codice</span><span class="sxs-lookup"><span data-stu-id="51c4e-121">Code</span></span>  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="51c4e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51c4e-122">See Also</span></span>  
 [<span data-ttu-id="51c4e-123">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="51c4e-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="51c4e-124">Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione</span><span class="sxs-lookup"><span data-stu-id="51c4e-124">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
