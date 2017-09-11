---
title: "Espressione di tipo &lt;tipo&gt; non è sottoposta a query | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36593
- vbc36593
dev_langs:
- VB
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 84563c7339ffe7415017280d74a13d6501236da5
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a><span data-ttu-id="8d104-102">Espressione di tipo &lt;tipo&gt; non è sottoposta a query</span><span class="sxs-lookup"><span data-stu-id="8d104-102">Expression of type &lt;type&gt; is not queryable</span></span>
<span data-ttu-id="8d104-103">Espressione di tipo \<tipo > non è sottoposta a query.</span><span class="sxs-lookup"><span data-stu-id="8d104-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="8d104-104">Assicurarsi che non manchi un'importazione di riferimento e/o dello spazio dei nomi di assembly per il provider LINQ.</span><span class="sxs-lookup"><span data-stu-id="8d104-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="8d104-105">Tipi queryable sono definiti nel <xref:System.Linq>, <xref:System.Data.Linq>, e <xref:System.Xml.Linq>gli spazi dei nomi.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="8d104-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="8d104-106">È necessario importare uno o più di questi spazi dei nomi per eseguire query LINQ.</span><span class="sxs-lookup"><span data-stu-id="8d104-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="8d104-107">Il <xref:System.Linq>dello spazio dei nomi consente agli oggetti di query, ad esempio raccolte e matrici utilizzando LINQ.</xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="8d104-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="8d104-108">Il <xref:System.Data.Linq>dello spazio dei nomi consente di eseguire query su DataSet ADO.NET e SQL Server database utilizzando LINQ.</xref:System.Data.Linq></span><span class="sxs-lookup"><span data-stu-id="8d104-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="8d104-109">Il <xref:System.Xml.Linq>dello spazio dei nomi consente di eseguire query XML utilizzando LINQ e utilizzare le funzionalità XML in Visual Basic.</xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="8d104-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="8d104-110">**ID errore:** BC36593</span><span class="sxs-lookup"><span data-stu-id="8d104-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8d104-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="8d104-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="8d104-112">Aggiungere un `Import` istruzione per il <xref:System.Linq>, <xref:System.Data.Linq>, o <xref:System.Xml.Linq>dello spazio dei nomi al file di codice.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="8d104-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="8d104-113">È inoltre possibile importare gli spazi dei nomi per il progetto utilizzando il **riferimenti** pagina di Progettazione progetti (**progetto**).</span><span class="sxs-lookup"><span data-stu-id="8d104-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2.  <span data-ttu-id="8d104-114">Assicurarsi che il tipo identificato come origine della query è un tipo queryable.</span><span class="sxs-lookup"><span data-stu-id="8d104-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="8d104-115">Ovvero, un tipo che implementa <xref:System.Collections.Generic.IEnumerable%601>o <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="8d104-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d104-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d104-116">See Also</span></span>  
 <span data-ttu-id="8d104-117"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="8d104-117"><xref:System.Linq></span></span>   
 <span data-ttu-id="8d104-118"><xref:System.Data.Linq></xref:System.Data.Linq></span><span class="sxs-lookup"><span data-stu-id="8d104-118"><xref:System.Data.Linq></span></span>   
 <span data-ttu-id="8d104-119"><xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="8d104-119"><xref:System.Xml.Linq></span></span>   
<span data-ttu-id="8d104-120"> [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="8d104-120"> [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="8d104-121"> [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="8d104-121"> [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="8d104-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="8d104-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="8d104-123"> [I riferimenti e istruzione Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8d104-123"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="8d104-124"> [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="8d104-124"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="8d104-125"> [Pagina Riferimenti, Creazione progetti (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="8d104-125"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span></span>
