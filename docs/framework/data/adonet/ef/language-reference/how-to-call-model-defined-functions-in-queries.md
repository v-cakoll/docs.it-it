---
title: 'Procedura: chiamare funzioni definite dal modello in query'
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
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7a713c22b307f10ef529de5c78c002e8d67a38e8
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-call-model-defined-functions-in-queries"></a><span data-ttu-id="17ce2-102">Procedura: chiamare funzioni definite dal modello in query</span><span class="sxs-lookup"><span data-stu-id="17ce2-102">How to: Call Model-Defined Functions in Queries</span></span>
<span data-ttu-id="17ce2-103">In questo argomento viene descritto come chiamare funzioni definite nel modello concettuale dall'interno di query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17ce2-103">This topic describes how to call functions that are defined in the conceptual model from within [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="17ce2-104">La procedura descritta di seguito fornisce una struttura di alto livello per la chiamata di una funzione definita dal modello dall'interno di una query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17ce2-104">The procedure below provides a high-level outline for calling a model-defined function from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="17ce2-105">Nell'esempio che segue vengono forniti dettagli aggiuntivi sui passaggi della procedura.</span><span class="sxs-lookup"><span data-stu-id="17ce2-105">The example that follows provides more detail about the steps in the procedure.</span></span> <span data-ttu-id="17ce2-106">In questa procedura si presuppone che sia stata definita una funzione nel modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="17ce2-106">The procedure assumes that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="17ce2-107">Per ulteriori informazioni, vedere [procedura: definire le funzioni personalizzate nel modello concettuale](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).</span><span class="sxs-lookup"><span data-stu-id="17ce2-107">For more information, see [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).</span></span>  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a><span data-ttu-id="17ce2-108">Per chiamare una funzione definita nel modello concettuale</span><span class="sxs-lookup"><span data-stu-id="17ce2-108">To call a function defined in the conceptual model</span></span>  
  
1.  <span data-ttu-id="17ce2-109">Aggiungere un metodo CLR (Common Language Runtime) all'applicazione che esegue il mapping alla funzione definita nel modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="17ce2-109">Add a common language runtime (CLR) method to your application that maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="17ce2-110">Per eseguire il mapping del metodo, è necessario applicare un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> al metodo.</span><span class="sxs-lookup"><span data-stu-id="17ce2-110">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="17ce2-111">Si noti che i parametri <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> e <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> dell'attributo sono rispettivamente il nome dello spazio dei nomi del modello concettuale e il nome della funzione nel modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="17ce2-111">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="17ce2-112">La risoluzione del nome della funzione per LINQ rileva la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="17ce2-112">Function name resolution for LINQ is case sensitive.</span></span>  
  
2.  <span data-ttu-id="17ce2-113">Chiamare la funzione in una query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17ce2-113">Call the function in a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17ce2-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="17ce2-114">Example</span></span>  
 <span data-ttu-id="17ce2-115">Nell'esempio seguente viene mostrato come chiamare una funzione definita nel modello concettuale dall'interno di una query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17ce2-115">The following example demonstrates how to call a function that is defined in the conceptual model from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="17ce2-116">Nell'esempio viene usato il modello School.</span><span class="sxs-lookup"><span data-stu-id="17ce2-116">The example uses the School model.</span></span> <span data-ttu-id="17ce2-117">Per informazioni sul modello School, vedere [la creazione di Database di esempio School](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) e [la generazione di File con estensione edmx dell'istituto di istruzione](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758).</span><span class="sxs-lookup"><span data-stu-id="17ce2-117">For information about the School model, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) and [Generating the School .edmx File](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758).</span></span>  
  
 <span data-ttu-id="17ce2-118">La funzione del modello concettuale seguente restituisce il numero di anni di servizio di un docente.</span><span class="sxs-lookup"><span data-stu-id="17ce2-118">The following conceptual model function returns the number of years since an instructor was hired.</span></span> <span data-ttu-id="17ce2-119">Per informazioni sull'aggiunta di funzione a un modello concettuale, vedere [procedura: definire le funzioni personalizzate nel modello concettuale](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).)</span><span class="sxs-lookup"><span data-stu-id="17ce2-119">For information about adding the function to a conceptual model, see [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).)</span></span>  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="17ce2-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="17ce2-120">Example</span></span>  
 <span data-ttu-id="17ce2-121">Successivamente aggiungere il metodo seguente all'applicazione e usare un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> per eseguirne il mapping alla funzione del modello concettuale:</span><span class="sxs-lookup"><span data-stu-id="17ce2-121">Next, add the following method to your application and use an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to map it to the conceptual model function:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="17ce2-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="17ce2-122">Example</span></span>  
 <span data-ttu-id="17ce2-123">A questo punto è possibile chiamare la funzione del modello concettuale dall'interno di una query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17ce2-123">Now you can call the conceptual model function from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="17ce2-124">Nel codice seguente viene chiamato il metodo per visualizzare tutti i docenti assunti da più di dieci anni:</span><span class="sxs-lookup"><span data-stu-id="17ce2-124">The following code calls the method to display all instructors that were hired more than ten years ago:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="17ce2-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17ce2-125">See Also</span></span>  
 [<span data-ttu-id="17ce2-126">Cenni preliminari sui file con estensione edmx</span><span class="sxs-lookup"><span data-stu-id="17ce2-126">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="17ce2-127">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="17ce2-127">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [<span data-ttu-id="17ce2-128">Chiamata di funzioni in query di LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="17ce2-128">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [<span data-ttu-id="17ce2-129">Procedura: Chiamare funzioni definite dal modello come metodi di oggetto</span><span class="sxs-lookup"><span data-stu-id="17ce2-129">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)
