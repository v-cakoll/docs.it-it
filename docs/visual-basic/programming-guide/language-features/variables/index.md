---
title: Variabili in Visual Basic
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
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: 27
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2fdc670bf4f17000809e75e32c32edb39abf0fed
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="variables-in-visual-basic"></a><span data-ttu-id="75475-102">Variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75475-102">Variables in Visual Basic</span></span>
<span data-ttu-id="75475-103">Quando si eseguono calcoli con [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] è spesso necessario archiviare i valori.</span><span class="sxs-lookup"><span data-stu-id="75475-103">You often have to store values when you perform calculations with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="75475-104">È possibile ad esempio che si vogliano calcolare valori diversi, confrontarli ed eseguire operazioni su di essi a seconda del risultato del confronto.</span><span class="sxs-lookup"><span data-stu-id="75475-104">For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison.</span></span> <span data-ttu-id="75475-105">Per poter confrontare i valori è necessario archiviarli.</span><span class="sxs-lookup"><span data-stu-id="75475-105">You have to retain the values if you want to compare them.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="75475-106">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="75475-106">Usage</span></span>  
 <span data-ttu-id="75475-107">Come la maggior parte dei linguaggi di programmazione, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] usa le variabili per archiviare i valori.</span><span class="sxs-lookup"><span data-stu-id="75475-107">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], just like most programming languages, uses variables for storing values.</span></span> <span data-ttu-id="75475-108">Ogni *variabile* ha un nome, ovvero la parola usata per fare riferimento al valore contenuto nella variabile.</span><span class="sxs-lookup"><span data-stu-id="75475-108">A *variable* has a name (the word that you use to refer to the value that the variable contains).</span></span> <span data-ttu-id="75475-109">Ogni variabile ha anche un tipo di dati che determina il genere di dati che la variabile può archiviare.</span><span class="sxs-lookup"><span data-stu-id="75475-109">A variable also has a data type (which determines the kind of data that the variable can store).</span></span> <span data-ttu-id="75475-110">Una variabile può rappresentare una matrice se deve archiviare un insieme indicizzato di elementi di dati strettamente correlati.</span><span class="sxs-lookup"><span data-stu-id="75475-110">A variable can represent an array if it has to store an indexed set of closely related data items.</span></span>  
  
 <span data-ttu-id="75475-111">L'inferenza del tipo di variabile locale consente di dichiarare le variabili senza specificare esplicitamente un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="75475-111">Local type inference enables you to declare variables without explicitly stating a data type.</span></span> <span data-ttu-id="75475-112">In questo caso, il compilatore deduce il tipo della variabile in base al tipo dell'espressione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="75475-112">Instead, the compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="75475-113">Per altre informazioni, vedere [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) (Inferenza del tipo di variabile locale) e [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) (Istruzione Option Infer).</span><span class="sxs-lookup"><span data-stu-id="75475-113">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="assigning-values"></a><span data-ttu-id="75475-114">Assegnazione di valori</span><span class="sxs-lookup"><span data-stu-id="75475-114">Assigning Values</span></span>  
 <span data-ttu-id="75475-115">Le istruzioni di assegnazione consentono di eseguire i calcoli e assegnare il risultato a una variabile, come illustra l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="75475-115">You use assignment statements to perform calculations and assign the result to a variable, as the following example shows.</span></span>  
  
 <span data-ttu-id="75475-116">[!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="75475-116">[!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75475-117">Il segno di uguale (`=`) in questo esempio è un operatore di assegnazione, non un operatore di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="75475-117">The equal sign (`=`) in this example is an assignment operator, not an equality operator.</span></span> <span data-ttu-id="75475-118">Il valore viene assegnato alla variabile `applesSold`.</span><span class="sxs-lookup"><span data-stu-id="75475-118">The value is being assigned to the variable `applesSold`.</span></span>  
  
 <span data-ttu-id="75475-119">Per altre informazioni, vedere [Procedura: Spostare i dati all'interno e all'esterno di una variabile](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).</span><span class="sxs-lookup"><span data-stu-id="75475-119">For more information, see [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).</span></span>  
  
## <a name="variables-and-properties"></a><span data-ttu-id="75475-120">Variabili e proprietà</span><span class="sxs-lookup"><span data-stu-id="75475-120">Variables and Properties</span></span>  
 <span data-ttu-id="75475-121">Analogamente a una variabile, una *proprietà* rappresenta un valore al quale è possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="75475-121">Like a variable, a *property* represents a value that you can access.</span></span> <span data-ttu-id="75475-122">Le proprietà sono tuttavia più complesse delle variabili.</span><span class="sxs-lookup"><span data-stu-id="75475-122">However, it is more complex than a variable.</span></span> <span data-ttu-id="75475-123">Le proprietà usano blocchi di codice che controllano come impostare e recuperare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="75475-123">A property uses code blocks that control how to set and retrieve its value.</span></span> <span data-ttu-id="75475-124">Per altre informazioni, vedere [Differenze tra proprietà e variabili in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="75475-124">For more information, see [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75475-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75475-125">See Also</span></span>  
 <span data-ttu-id="75475-126">[Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="75475-126">[Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
 <span data-ttu-id="75475-127">[Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="75475-127">[Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
 <span data-ttu-id="75475-128">[Risoluzione dei problemi relativi alle variabili](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md) </span><span class="sxs-lookup"><span data-stu-id="75475-128">[Troubleshooting Variables](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md) </span></span>  
 <span data-ttu-id="75475-129">[Procedura: Spostare i dati all'interno e all'esterno di una variabile](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="75475-129">[How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span></span>  
 <span data-ttu-id="75475-130">[Differenze tra proprietà e variabili in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="75475-130">[Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md) </span></span>  
 [<span data-ttu-id="75475-131">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="75475-131">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

