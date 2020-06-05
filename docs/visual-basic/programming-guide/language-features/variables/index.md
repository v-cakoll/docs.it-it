---
title: variables
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
ms.openlocfilehash: ff617774d7e93ab4238ebc06617cc03fb6bc675a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410387"
---
# <a name="variables-in-visual-basic"></a><span data-ttu-id="7e545-102">Variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7e545-102">Variables in Visual Basic</span></span>
<span data-ttu-id="7e545-103">Spesso è necessario archiviare i valori quando si eseguono calcoli con Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7e545-103">You often have to store values when you perform calculations with Visual Basic.</span></span> <span data-ttu-id="7e545-104">È possibile ad esempio che si vogliano calcolare valori diversi, confrontarli ed eseguire operazioni su di essi a seconda del risultato del confronto.</span><span class="sxs-lookup"><span data-stu-id="7e545-104">For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison.</span></span> <span data-ttu-id="7e545-105">Per poter confrontare i valori è necessario archiviarli.</span><span class="sxs-lookup"><span data-stu-id="7e545-105">You have to retain the values if you want to compare them.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="7e545-106">Uso</span><span class="sxs-lookup"><span data-stu-id="7e545-106">Usage</span></span>  
 <span data-ttu-id="7e545-107">Visual Basic, analogamente alla maggior parte dei linguaggi di programmazione, USA le variabili per archiviare i valori.</span><span class="sxs-lookup"><span data-stu-id="7e545-107">Visual Basic, just like most programming languages, uses variables for storing values.</span></span> <span data-ttu-id="7e545-108">Ogni *variabile* ha un nome, ovvero la parola usata per fare riferimento al valore contenuto nella variabile.</span><span class="sxs-lookup"><span data-stu-id="7e545-108">A *variable* has a name (the word that you use to refer to the value that the variable contains).</span></span> <span data-ttu-id="7e545-109">Ogni variabile ha anche un tipo di dati che determina il genere di dati che la variabile può archiviare.</span><span class="sxs-lookup"><span data-stu-id="7e545-109">A variable also has a data type (which determines the kind of data that the variable can store).</span></span> <span data-ttu-id="7e545-110">Una variabile può rappresentare una matrice se deve archiviare un insieme indicizzato di elementi di dati strettamente correlati.</span><span class="sxs-lookup"><span data-stu-id="7e545-110">A variable can represent an array if it has to store an indexed set of closely related data items.</span></span>  
  
 <span data-ttu-id="7e545-111">L'inferenza del tipo di variabile locale consente di dichiarare le variabili senza specificare esplicitamente un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="7e545-111">Local type inference enables you to declare variables without explicitly stating a data type.</span></span> <span data-ttu-id="7e545-112">In questo caso, il compilatore deduce il tipo della variabile in base al tipo dell'espressione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="7e545-112">Instead, the compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="7e545-113">Per altre informazioni, vedere [Local Type Inference](local-type-inference.md) (Inferenza del tipo di variabile locale) e [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md) (Istruzione Option Infer).</span><span class="sxs-lookup"><span data-stu-id="7e545-113">For more information, see [Local Type Inference](local-type-inference.md) and [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="assigning-values"></a><span data-ttu-id="7e545-114">Assegnazione di valori</span><span class="sxs-lookup"><span data-stu-id="7e545-114">Assigning Values</span></span>  
 <span data-ttu-id="7e545-115">Le istruzioni di assegnazione consentono di eseguire i calcoli e assegnare il risultato a una variabile, come illustra l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7e545-115">You use assignment statements to perform calculations and assign the result to a variable, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrVariables#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#1)]  
  
> [!NOTE]
> <span data-ttu-id="7e545-116">Il segno di uguale (`=`) in questo esempio è un operatore di assegnazione, non un operatore di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="7e545-116">The equal sign (`=`) in this example is an assignment operator, not an equality operator.</span></span> <span data-ttu-id="7e545-117">Il valore viene assegnato alla variabile `applesSold`.</span><span class="sxs-lookup"><span data-stu-id="7e545-117">The value is being assigned to the variable `applesSold`.</span></span>  
  
 <span data-ttu-id="7e545-118">Per altre informazioni, vedere [Procedura: Spostare i dati all'interno e all'esterno di una variabile](how-to-move-data-into-and-out-of-a-variable.md).</span><span class="sxs-lookup"><span data-stu-id="7e545-118">For more information, see [How to: Move Data Into and Out of a Variable](how-to-move-data-into-and-out-of-a-variable.md).</span></span>  
  
## <a name="variables-and-properties"></a><span data-ttu-id="7e545-119">Variabili e proprietà</span><span class="sxs-lookup"><span data-stu-id="7e545-119">Variables and Properties</span></span>  
 <span data-ttu-id="7e545-120">Analogamente a una variabile, una *proprietà* rappresenta un valore al quale è possibile accedere.</span><span class="sxs-lookup"><span data-stu-id="7e545-120">Like a variable, a *property* represents a value that you can access.</span></span> <span data-ttu-id="7e545-121">Le proprietà sono tuttavia più complesse delle variabili.</span><span class="sxs-lookup"><span data-stu-id="7e545-121">However, it is more complex than a variable.</span></span> <span data-ttu-id="7e545-122">Le proprietà usano blocchi di codice che controllano come impostare e recuperare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="7e545-122">A property uses code blocks that control how to set and retrieve its value.</span></span> <span data-ttu-id="7e545-123">Per altre informazioni, vedere [Differenze tra proprietà e variabili in Visual Basic](../procedures/differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="7e545-123">For more information, see [Differences Between Properties and Variables in Visual Basic](../procedures/differences-between-properties-and-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e545-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e545-124">See also</span></span>

- [<span data-ttu-id="7e545-125">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="7e545-125">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="7e545-126">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="7e545-126">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="7e545-127">Risoluzione dei problemi relativi alle variabili</span><span class="sxs-lookup"><span data-stu-id="7e545-127">Troubleshooting Variables</span></span>](troubleshooting-variables.md)
- [<span data-ttu-id="7e545-128">Procedura: spostare i dati all'interno e all'esterno di una variabile</span><span class="sxs-lookup"><span data-stu-id="7e545-128">How to: Move Data Into and Out of a Variable</span></span>](how-to-move-data-into-and-out-of-a-variable.md)
- [<span data-ttu-id="7e545-129">Differenze tra proprietà e variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7e545-129">Differences Between Properties and Variables in Visual Basic</span></span>](../procedures/differences-between-properties-and-variables.md)
- [<span data-ttu-id="7e545-130">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="7e545-130">Local Type Inference</span></span>](local-type-inference.md)
