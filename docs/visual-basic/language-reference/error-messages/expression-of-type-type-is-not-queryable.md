---
title: L'espressione di tipo <type> non può essere sottoposta a query
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: e61b4dac109f714b5cf25226d1029237ca77032d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409478"
---
# <a name="expression-of-type-type-is-not-queryable"></a><span data-ttu-id="84600-102">L'espressione di tipo \<type> non può essere sottoposta a query</span><span class="sxs-lookup"><span data-stu-id="84600-102">Expression of type \<type> is not queryable</span></span>
<span data-ttu-id="84600-103">L'espressione di tipo \<type> non è Queryable.</span><span class="sxs-lookup"><span data-stu-id="84600-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="84600-104">Verificare che non manchi un riferimento all'assembly e/o l'importazione dello spazio dei nomi per il provider LINQ.</span><span class="sxs-lookup"><span data-stu-id="84600-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="84600-105">I tipi queryable sono definiti negli <xref:System.Linq> <xref:System.Data.Linq> <xref:System.Xml.Linq> spazi dei nomi, e.</span><span class="sxs-lookup"><span data-stu-id="84600-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="84600-106">Per eseguire query LINQ è necessario importare uno o più di questi spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="84600-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="84600-107">Lo <xref:System.Linq> spazio dei nomi consente di eseguire query su oggetti quali raccolte e matrici utilizzando LINQ.</span><span class="sxs-lookup"><span data-stu-id="84600-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="84600-108">Lo <xref:System.Data.Linq> spazio dei nomi consente di eseguire query sui set di dati ADO.NET e SQL Server database usando LINQ.</span><span class="sxs-lookup"><span data-stu-id="84600-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="84600-109">Lo <xref:System.Xml.Linq> spazio dei nomi consente di eseguire query su XML utilizzando LINQ e di utilizzare le funzionalità XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="84600-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="84600-110">**ID errore:** BC36593</span><span class="sxs-lookup"><span data-stu-id="84600-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="84600-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="84600-111">To correct this error</span></span>  
  
1. <span data-ttu-id="84600-112">Aggiungere un' `Import` istruzione per lo <xref:System.Linq> <xref:System.Data.Linq> <xref:System.Xml.Linq> spazio dei nomi, o al file di codice.</span><span class="sxs-lookup"><span data-stu-id="84600-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="84600-113">È anche possibile importare gli spazi dei nomi per il progetto tramite la pagina **riferimenti** di progettazione progetti (**progetto**).</span><span class="sxs-lookup"><span data-stu-id="84600-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2. <span data-ttu-id="84600-114">Verificare che il tipo identificato come origine della query sia un tipo Queryable.</span><span class="sxs-lookup"><span data-stu-id="84600-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="84600-115">Ovvero un tipo che implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="84600-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84600-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84600-116">See also</span></span>

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [<span data-ttu-id="84600-117">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84600-117">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="84600-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="84600-118">LINQ</span></span>](../../programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="84600-119">XML</span><span class="sxs-lookup"><span data-stu-id="84600-119">XML</span></span>](../../programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="84600-120">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="84600-120">References and the Imports Statement</span></span>](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="84600-121">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="84600-121">Imports Statement (.NET Namespace and Type)</span></span>](../statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="84600-122">Riferimenti (pagina), Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84600-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
