---
title: 'Procedura: utilizzare una classe generica (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- type parameters, defining
- data type arguments, defining
- arguments [Visual Basic], data types
- Of keyword, using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters, type
- types [Visual Basic], generic
- parameters, generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters, data type
- data type parameters, defining
- type arguments, defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d6f5f941887dfc1f93221be1c184f0dcc2789352
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-use-a-generic-class-visual-basic"></a><span data-ttu-id="deb99-102">Procedura: utilizzare una classe generica (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="deb99-102">How to: Use a Generic Class (Visual Basic)</span></span>
<span data-ttu-id="deb99-103">Una classe che accetta *parametri di tipo* è chiamato *classe generica*.</span><span class="sxs-lookup"><span data-stu-id="deb99-103">A class that takes *type parameters* is called a *generic class*.</span></span> <span data-ttu-id="deb99-104">Se si usa una classe generica, è possibile generare una *classe costruita* da essa fornendo un *argomento di tipo* per ciascuno di questi parametri.</span><span class="sxs-lookup"><span data-stu-id="deb99-104">If you are using a generic class, you can generate a *constructed class* from it by supplying a *type argument* for each of these parameters.</span></span> <span data-ttu-id="deb99-105">È possibile quindi dichiarare una variabile del tipo di classe costruita, creare un'istanza della classe costruita e assegnarla alla variabile.</span><span class="sxs-lookup"><span data-stu-id="deb99-105">You can then declare a variable of the constructed class type, and you can create an instance of the constructed class and assign it to that variable.</span></span>  
  
 <span data-ttu-id="deb99-106">Oltre alle classi, è possibile definire e usare anche strutture, interfacce, routine e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="deb99-106">In addition to classes, you can also define and use generic structures, interfaces, procedures, and delegates.</span></span>  
  
 <span data-ttu-id="deb99-107">La procedura seguente accetta una classe generica definita in [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] e crea un'istanza da essa.</span><span class="sxs-lookup"><span data-stu-id="deb99-107">The following procedure takes a generic class defined in the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] and creates an instance from it.</span></span>  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a><span data-ttu-id="deb99-108">Per usare una classe che accetta un parametro di tipo</span><span class="sxs-lookup"><span data-stu-id="deb99-108">To use a class that takes a type parameter</span></span>  
  
1.  <span data-ttu-id="deb99-109">All'inizio del file di origine, includere un [istruzione Imports (tipo e Namespace .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per importare il <xref:System.Collections.Generic?displayProperty=fullName>dello spazio dei nomi.</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="deb99-109">At the beginning of your source file, include an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import the <xref:System.Collections.Generic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="deb99-110">In questo modo è possibile fare riferimento alla <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>classe senza qualificare completamente per differenziarla da altre classi queue, ad esempio <xref:System.Collections.Queue?displayProperty=fullName>.</xref:System.Collections.Queue?displayProperty=fullName> </xref:System.Collections.Generic.Queue%601?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="deb99-110">This allows you to refer to the <xref:System.Collections.Generic.Queue%601?displayProperty=fullName> class without having to fully qualify it to differentiate it from other queue classes such as <xref:System.Collections.Queue?displayProperty=fullName>.</span></span>  
  
2.  <span data-ttu-id="deb99-111">Creare l'oggetto in modo normale, ma aggiungere `(Of` `type``)` immediatamente dopo il nome della classe.</span><span class="sxs-lookup"><span data-stu-id="deb99-111">Create the object in the normal way, but add `(Of` `type``)` immediately after the class name.</span></span>  
  
     <span data-ttu-id="deb99-112">Nell'esempio seguente viene utilizzata la stessa classe (<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>) per creare due oggetti coda che contengono elementi di diversi tipi di dati.</xref:System.Collections.Generic.Queue%601?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="deb99-112">The following example uses the same class (<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>) to create two queue objects that hold items of different data types.</span></span> <span data-ttu-id="deb99-113">Aggiunge gli elementi alla fine di ogni coda e quindi rimuove e visualizza gli elementi dall'inizio di ogni coda.</span><span class="sxs-lookup"><span data-stu-id="deb99-113">It adds items to the end of each queue and then removes and displays items from the front of each queue.</span></span>  
  
     <span data-ttu-id="deb99-114">[!code-vb[9 VbVbalrDataTypes](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="deb99-114">[!code-vb[VbVbalrDataTypes#9](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb99-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="deb99-115">See Also</span></span>  
 <span data-ttu-id="deb99-116">[Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="deb99-116">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="deb99-117"> [Tipi generici in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="deb99-117"> [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="deb99-118"> [Indipendenza del linguaggio e componenti indipendenti dal linguaggio](https://msdn.microsoft.com/library/12a7a7h3) </span><span class="sxs-lookup"><span data-stu-id="deb99-118"> [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) </span></span>  
<span data-ttu-id="deb99-119"> [Of](../../../../visual-basic/language-reference/statements/of-clause.md) </span><span class="sxs-lookup"><span data-stu-id="deb99-119"> [Of](../../../../visual-basic/language-reference/statements/of-clause.md) </span></span>  
<span data-ttu-id="deb99-120"> [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="deb99-120"> [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="deb99-121"> [Procedura: Definire una classe in grado di fornire funzionalità identiche con tipi di dati diversi](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="deb99-121"> [How to: Define a Class That Can Provide Identical Functionality on Different Data Types](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md) </span></span>  
<span data-ttu-id="deb99-122"> [Iteratori](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)</span><span class="sxs-lookup"><span data-stu-id="deb99-122"> [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)</span></span>
