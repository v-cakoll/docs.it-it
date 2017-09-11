---
title: 'Procedura: creare un elenco di elementi | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- list [LINQ in Visual Basic]
- objects [Visual Basic], list of items
ms.assetid: fe941aba-6340-455c-8b1f-ffd9c3eb1ac5
caps.latest.revision: 29
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
ms.openlocfilehash: ad0d2dfd38e30ddff1a5b030ec1ace884539d134
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-list-of-items"></a><span data-ttu-id="19b5b-102">Procedura: creare un elenco di elementi</span><span class="sxs-lookup"><span data-stu-id="19b5b-102">How to: Create a List of Items</span></span>
<span data-ttu-id="19b5b-103">Il codice in questo argomento definisce una classe `Student` e crea un elenco di istanze nella classe.</span><span class="sxs-lookup"><span data-stu-id="19b5b-103">The code in this topic defines a `Student` class and creates a list of instances of the class.</span></span> <span data-ttu-id="19b5b-104">L'elenco è progettato per supportare l'argomento [procedura dettagliata: scrittura di query in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).</span><span class="sxs-lookup"><span data-stu-id="19b5b-104">The list is designed to support the topic [Walkthrough: Writing Queries in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).</span></span> <span data-ttu-id="19b5b-105">Può inoltre essere usato per qualsiasi applicazione richieda un elenco di oggetti.</span><span class="sxs-lookup"><span data-stu-id="19b5b-105">It also can be used for any application that requires a list of objects.</span></span> <span data-ttu-id="19b5b-106">Il codice definisce gli elementi nell'elenco di studenti usando gli inizializzatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="19b5b-106">The code defines the items in the list of students by using object initializers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19b5b-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="19b5b-107">Example</span></span>  
 <span data-ttu-id="19b5b-108">Se si lavora sulla procedura dettagliata, è possibile usare questo codice per il file Module1.vb del progetto creato.</span><span class="sxs-lookup"><span data-stu-id="19b5b-108">If you are working on the walkthrough, you can use this code for the Module1.vb file of the project that is created there.</span></span> <span data-ttu-id="19b5b-109">Basta sostituire le righe contrassegnate con **** nel metodo `Main` con le query e le esecuzioni delle query fornite nella procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="19b5b-109">Just replace the lines marked with **** in the `Main` method with the queries and query executions that are provided in the walkthrough.</span></span>  
  
 <span data-ttu-id="19b5b-110">[!code-vb[VbLINQHowToCreateList n.&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/how-to-create-a-list-of-items_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="19b5b-110">[!code-vb[VbLINQHowToCreateList#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/how-to-create-a-list-of-items_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19b5b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19b5b-111">See Also</span></span>  
 <span data-ttu-id="19b5b-112">[Procedura dettagliata: Scrittura di query in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md) </span><span class="sxs-lookup"><span data-stu-id="19b5b-112">[Walkthrough: Writing Queries in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md) </span></span>  
<span data-ttu-id="19b5b-113"> [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="19b5b-113"> [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
<span data-ttu-id="19b5b-114"> [Inizializzatori di oggetto: Tipi denominati e anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="19b5b-114"> [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) </span></span>  
<span data-ttu-id="19b5b-115"> [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="19b5b-115"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="19b5b-116"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="19b5b-116"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="19b5b-117"> [Query](../../../../visual-basic/language-reference/queries/queries.md)</span><span class="sxs-lookup"><span data-stu-id="19b5b-117"> [Queries](../../../../visual-basic/language-reference/queries/queries.md)</span></span>
