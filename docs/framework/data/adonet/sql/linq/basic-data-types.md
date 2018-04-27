---
title: Tipi di dati di base
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: e88767bd478b4b59e8c395473cfd8a36aaf68f3b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="basic-data-types"></a><span data-ttu-id="828ae-102">Tipi di dati di base</span><span class="sxs-lookup"><span data-stu-id="828ae-102">Basic Data Types</span></span>
<span data-ttu-id="828ae-103">Poiché le query LINQ to SQL vengono convertite in Transact-SQL prima di essere eseguite in Microsoft SQL Server,</span><span class="sxs-lookup"><span data-stu-id="828ae-103">Because LINQ to SQL queries translate to Transact-SQL before they are executed on the Microsoft SQL Server.</span></span> <span data-ttu-id="828ae-104">in LINQ to SQL è supportata buona parte delle funzionalità predefinite di SQL Server  per i tipi di dati di base.</span><span class="sxs-lookup"><span data-stu-id="828ae-104">LINQ to SQL supports much of the same built-in functionality that SQL Server does for basic data types.</span></span>  
  
## <a name="casting"></a><span data-ttu-id="828ae-105">Cast</span><span class="sxs-lookup"><span data-stu-id="828ae-105">Casting</span></span>  
 <span data-ttu-id="828ae-106">I cast impliciti o espliciti vengono abilitati da un tipo CLR di origine in un tipo CLR di destinazione se è disponibile una conversione valida simile all'interno di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="828ae-106">Implicit or explicit casts are enabled from a source CLR type to a target CLR type if there is a similar valid conversion within SQL Server.</span></span> <span data-ttu-id="828ae-107">Per ulteriori informazioni sui cast CLR, vedere [funzione CType](~/docs/visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) e [come](~/docs/csharp/language-reference/keywords/as.md).</span><span class="sxs-lookup"><span data-stu-id="828ae-107">For more information about CLR casting, see [CType Function](~/docs/visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) and [as](~/docs/csharp/language-reference/keywords/as.md).</span></span> <span data-ttu-id="828ae-108">Dopo la conversione i cast modificano il comportamento delle operazioni eseguite su un'espressione CLR, in modo che corrisponda a quello di altre espressioni CLR di cui viene eseguito naturalmente il mapping al tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="828ae-108">After conversion, casts change the behavior of operations performed on a CLR expression to match the behavior of other CLR expressions that naturally map to the destination type.</span></span> <span data-ttu-id="828ae-109">I cast sono inoltre convertibili nel contesto del mapping di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="828ae-109">Casts are also translatable in the context of inheritance mapping.</span></span> <span data-ttu-id="828ae-110">È possibile eseguire il cast degli oggetti in sottotipi dell'entità più specifici, in modo che sia possibile accedere ai dati specifici del sottotipo.</span><span class="sxs-lookup"><span data-stu-id="828ae-110">Objects can be cast to more specific entity subtypes so that their subtype-specific data can be accessed.</span></span>  
  
## <a name="equality-operators"></a><span data-ttu-id="828ae-111">Operatori di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="828ae-111">Equality Operators</span></span>  
 <span data-ttu-id="828ae-112">LINQ to SQL all'interno di query LINQ to SQL supporta i seguenti operatori di uguaglianza sui tipi di dati di base:</span><span class="sxs-lookup"><span data-stu-id="828ae-112">LINQ to SQL supports the following equality operators on basic data types inside LINQ to SQL queries:</span></span>  
  
-   <span data-ttu-id="828ae-113">Operatore di uguaglianza e disuguaglianza: tali operatori sono supportati per i tipi numerici <xref:System.Boolean>, <xref:System.DateTime> e <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="828ae-113">Equal and Inequality Operator: Equality and inequality operators are supported for numeric <xref:System.Boolean>, <xref:System.DateTime>, and <xref:System.TimeSpan> types.</span></span> <span data-ttu-id="828ae-114">Per ulteriori informazioni sugli operatori di Visual Basic `=` e `<>`, vedere [gli operatori di confronto](~/docs/visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="828ae-114">For more about Visual Basic operators `=` and `<>`, see [Comparison Operators](~/docs/visual-basic/language-reference/operators/comparison-operators.md).</span></span> <span data-ttu-id="828ae-115">Per ulteriori informazioni sugli operatori di confronto c# `==` e `!=`, vedere [Operator = =](~/docs/csharp/language-reference/operators/equality-comparison-operator.md) e [! = (operatore)](~/docs/csharp/language-reference/operators/not-equal-operator.md)rispettivamente</span><span class="sxs-lookup"><span data-stu-id="828ae-115">For more information about C# comparison operators `==` and `!=`, see [== Operator](~/docs/csharp/language-reference/operators/equality-comparison-operator.md) and [!= Operator](~/docs/csharp/language-reference/operators/not-equal-operator.md), respectively</span></span>  
  
-   <span data-ttu-id="828ae-116">Operatore Is: l'operatore `IS` supporta la conversione quando viene usato il mapping di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="828ae-116">Is operator: The `IS` operator has a supported translation when inheritance mapping is being used.</span></span> <span data-ttu-id="828ae-117">È possibile usarlo invece di testare direttamente la colonna del discriminatore per determinare se un oggetto è di un tipo di entità specifico e viene convertito in un controllo nella colonna del discriminatore.</span><span class="sxs-lookup"><span data-stu-id="828ae-117">It can be used instead of directly testing the discriminator column to determine whether an object is of a specific entity type, and is translated to a check on the discriminator column.</span></span> <span data-ttu-id="828ae-118">Per ulteriori informazioni sugli operatori di Visual Basic e C#, vedere [operatore Is](~/docs/visual-basic/language-reference/operators/is-operator.md) e [è](~/docs/csharp/language-reference/keywords/is.md).</span><span class="sxs-lookup"><span data-stu-id="828ae-118">For more information about the Visual Basic and C# Is operators, see [Is Operator](~/docs/visual-basic/language-reference/operators/is-operator.md) and [is](~/docs/csharp/language-reference/keywords/is.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="828ae-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="828ae-119">See Also</span></span>  
 [<span data-ttu-id="828ae-120">Mapping del tipo SQL-CLR</span><span class="sxs-lookup"><span data-stu-id="828ae-120">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [<span data-ttu-id="828ae-121">Tipi di dati e funzioni</span><span class="sxs-lookup"><span data-stu-id="828ae-121">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
