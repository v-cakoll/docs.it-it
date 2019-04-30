---
title: Chiamate a metodo locali
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
ms.openlocfilehash: c8a4c29b1faa3c05f2cf32e9a60104b43a9b1c40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033514"
---
# <a name="local-method-calls"></a><span data-ttu-id="502ce-102">Chiamate a metodo locali</span><span class="sxs-lookup"><span data-stu-id="502ce-102">Local Method Calls</span></span>
<span data-ttu-id="502ce-103">Una chiamata al metodo locale viene eseguita all'interno del modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="502ce-103">A local method call is one that is executed within the object model.</span></span> <span data-ttu-id="502ce-104">Una chiamata al metodo remota viene convertita da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in SQL e trasmessa al motore di database per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="502ce-104">A remote method call is one that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates to SQL and transmits to the database engine for execution.</span></span> <span data-ttu-id="502ce-105">Chiamate a metodo locali sono necessari quando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non è possibile convertire la chiamata in SQL.</span><span class="sxs-lookup"><span data-stu-id="502ce-105">Local method calls are needed when [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot translate the call into SQL.</span></span> <span data-ttu-id="502ce-106">In caso contrario, verrà generata un'eccezione <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="502ce-106">Otherwise, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="502ce-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="502ce-107">Example 1</span></span>  
 <span data-ttu-id="502ce-108">Nell'esempio seguente viene eseguito il mapping di una classe `Order` alla tabella Orders nel database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="502ce-108">In the following example, an `Order` class is mapped to the Orders table in the Northwind sample database.</span></span> <span data-ttu-id="502ce-109">Alla classe è stato aggiunto un metodo di istanza locale.</span><span class="sxs-lookup"><span data-stu-id="502ce-109">A local instance method has been added to the class.</span></span>  
  
 <span data-ttu-id="502ce-110">Nella Query 1 il costruttore per la classe `Order` viene eseguito localmente.</span><span class="sxs-lookup"><span data-stu-id="502ce-110">In Query 1, the constructor for the `Order` class is executed locally.</span></span> <span data-ttu-id="502ce-111">Nella Query 2 se [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tentasse di convertire `LocalInstanceMethod()`in SQL, il tentativo avrà esito negativo e un <xref:System.InvalidOperationException> verrebbe generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="502ce-111">In Query 2, if [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tried to translate `LocalInstanceMethod()`into SQL, the attempt would fail and an <xref:System.InvalidOperationException> exception would be thrown.</span></span> <span data-ttu-id="502ce-112">Tuttavia, poiché [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fornisce il supporto per chiamate a metodo locali, nella query 2 non viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="502ce-112">But because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides support for local method calls, Query2 will not throw an exception.</span></span>  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="502ce-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="502ce-113">See also</span></span>

- [<span data-ttu-id="502ce-114">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="502ce-114">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
