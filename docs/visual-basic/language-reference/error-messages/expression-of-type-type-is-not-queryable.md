---
title: L'espressione di tipo <type> non può essere sottoposta a query
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 121c0a95a3a6bb695d9c73347c733cba215a0de4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304155"
---
# <a name="expression-of-type-type-is-not-queryable"></a><span data-ttu-id="f28da-102">Espressione di tipo \<tipo > non è disponibile per query</span><span class="sxs-lookup"><span data-stu-id="f28da-102">Expression of type \<type> is not queryable</span></span>
<span data-ttu-id="f28da-103">Espressione di tipo \<tipo > non è disponibile per query.</span><span class="sxs-lookup"><span data-stu-id="f28da-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="f28da-104">Assicurarsi che sia presente un'importazione di riferimento e/o lo spazio dei nomi di assembly per il provider LINQ.</span><span class="sxs-lookup"><span data-stu-id="f28da-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="f28da-105">Tipi queryable sono definiti nel <xref:System.Linq>, <xref:System.Data.Linq>, e <xref:System.Xml.Linq> gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f28da-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="f28da-106">È necessario importare uno o più di questi spazi dei nomi per eseguire query LINQ.</span><span class="sxs-lookup"><span data-stu-id="f28da-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="f28da-107">Il <xref:System.Linq> spazio dei nomi consente agli oggetti di query, ad esempio le raccolte e matrici usando LINQ.</span><span class="sxs-lookup"><span data-stu-id="f28da-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="f28da-108">Il <xref:System.Data.Linq> dello spazio dei nomi consente di eseguire query sui set di dati ADO.NET e i database di SQL Server usando LINQ.</span><span class="sxs-lookup"><span data-stu-id="f28da-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="f28da-109">Il <xref:System.Xml.Linq> dello spazio dei nomi consente di eseguire query XML con LINQ e usare le funzionalità XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f28da-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="f28da-110">**ID errore:** BC36593</span><span class="sxs-lookup"><span data-stu-id="f28da-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f28da-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f28da-111">To correct this error</span></span>  
  
1. <span data-ttu-id="f28da-112">Aggiungere un `Import` istruzione per il <xref:System.Linq>, <xref:System.Data.Linq>, o <xref:System.Xml.Linq> dello spazio dei nomi al file di codice.</span><span class="sxs-lookup"><span data-stu-id="f28da-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="f28da-113">È anche possibile importare gli spazi dei nomi per il progetto utilizzando il **riferimenti** pagina della finestra di Progettazione progetti (**My Project**).</span><span class="sxs-lookup"><span data-stu-id="f28da-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2. <span data-ttu-id="f28da-114">Verificare che il tipo identificato come origine della query è un tipo queryable.</span><span class="sxs-lookup"><span data-stu-id="f28da-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="f28da-115">Vale a dire, un tipo che implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="f28da-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f28da-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f28da-116">See also</span></span>

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [<span data-ttu-id="f28da-117">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f28da-117">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f28da-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="f28da-118">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="f28da-119">XML</span><span class="sxs-lookup"><span data-stu-id="f28da-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="f28da-120">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="f28da-120">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="f28da-121">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="f28da-121">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="f28da-122">Riferimenti (pagina), Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f28da-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
