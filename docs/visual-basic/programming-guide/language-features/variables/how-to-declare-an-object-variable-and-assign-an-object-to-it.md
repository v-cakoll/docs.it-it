---
title: 'Procedura: dichiarare una variabile oggetto e assegnarle un oggetto'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: d9a8c1fb30bfa5988d48202e41202e7ede0f5f27
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410503"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="053ea-102">Procedura: dichiarare una variabile oggetto e assegnarle un oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="053ea-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="053ea-103">Per dichiarare una variabile del [tipo di dati Object](../../../language-reference/data-types/object-data-type.md) , è necessario specificare `As Object` in un' [istruzione Dim](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="053ea-103">You declare a variable of the [Object Data Type](../../../language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="053ea-104">Per assegnare un oggetto a una variabile di questo tipo, inserire l'oggetto dopo il segno di uguale ( `=` ) in un'istruzione di assegnazione o in una clausola di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="053ea-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="053ea-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="053ea-105">Example</span></span>

<span data-ttu-id="053ea-106">Nell'esempio seguente viene dichiarata una `Object` variabile a cui viene assegnata l'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="053ea-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="053ea-107">È possibile combinare la dichiarazione e l'assegnazione inizializzando la variabile come parte della relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="053ea-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="053ea-108">L'esempio seguente è equivalente all'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="053ea-108">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compile-the-code"></a><span data-ttu-id="053ea-109">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="053ea-109">Compile the code</span></span>

<span data-ttu-id="053ea-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="053ea-110">This example requires:</span></span>

- <span data-ttu-id="053ea-111">Un riferimento allo spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="053ea-111">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="053ea-112">Classe, struttura o modulo in cui inserire l' `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="053ea-112">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="053ea-113">Routine in cui inserire l'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="053ea-113">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="053ea-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="053ea-114">See also</span></span>

- [<span data-ttu-id="053ea-115">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="053ea-115">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="053ea-116">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="053ea-116">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="053ea-117">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="053ea-117">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="053ea-118">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="053ea-118">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="053ea-119">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="053ea-119">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
- [<span data-ttu-id="053ea-120">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="053ea-120">Local Type Inference</span></span>](local-type-inference.md)
- [<span data-ttu-id="053ea-121">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="053ea-121">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
