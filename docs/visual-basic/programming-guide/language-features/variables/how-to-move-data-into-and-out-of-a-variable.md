---
title: "Procedura: spostare i dati all'interno e all'esterno di una variabile"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: fe19a6160623aa9ea867becdf7a15b51319abf45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410438"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="e4332-102">Procedura: spostare i dati all'interno e all'esterno di una variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4332-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>

<span data-ttu-id="e4332-103">Per archiviare un valore in una variabile, inserire il nome della variabile sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e4332-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>

## <a name="putting-data-in-a-variable"></a><span data-ttu-id="e4332-104">Inserimento di dati in una variabile</span><span class="sxs-lookup"><span data-stu-id="e4332-104">Putting Data in a Variable</span></span>

#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="e4332-105">Per archiviare un valore in una variabile</span><span class="sxs-lookup"><span data-stu-id="e4332-105">To store a value in a variable</span></span>

- <span data-ttu-id="e4332-106">Usare il nome della variabile sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e4332-106">Use the variable name on the left side of an assignment statement.</span></span>

    <span data-ttu-id="e4332-107">Nell'esempio seguente viene impostato il valore della variabile `alpha` .</span><span class="sxs-lookup"><span data-stu-id="e4332-107">The following example sets the value of the variable `alpha`.</span></span>

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    <span data-ttu-id="e4332-108">Il valore generato sul lato destro dell'istruzione di assegnazione viene archiviato nella variabile.</span><span class="sxs-lookup"><span data-stu-id="e4332-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>

## <a name="getting-data-from-a-variable"></a><span data-ttu-id="e4332-109">Recupero di dati da una variabile</span><span class="sxs-lookup"><span data-stu-id="e4332-109">Getting Data from a Variable</span></span>

<span data-ttu-id="e4332-110">Per recuperare il valore di una variabile, è necessario includere il nome della variabile in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="e4332-110">You retrieve a variable's value by including the variable name in an expression.</span></span>

#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="e4332-111">Per recuperare un valore da una variabile</span><span class="sxs-lookup"><span data-stu-id="e4332-111">To retrieve a value from a variable</span></span>

- <span data-ttu-id="e4332-112">Usare il nome della variabile in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="e4332-112">Use the variable name in an expression.</span></span> <span data-ttu-id="e4332-113">È possibile usare una variabile ovunque sia possibile usare una costante o un valore letterale, tranne che in un'espressione che definisce il valore di una costante.</span><span class="sxs-lookup"><span data-stu-id="e4332-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>

  <span data-ttu-id="e4332-114">\-oppure-</span><span class="sxs-lookup"><span data-stu-id="e4332-114">\-or-</span></span>

- <span data-ttu-id="e4332-115">Usare il nome della variabile che segue il `=` segno di uguale () in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e4332-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>

  <span data-ttu-id="e4332-116">Nell'esempio seguente viene letto il valore della variabile `startValue` , quindi viene utilizzato il valore della variabile `counter` in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="e4332-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  <span data-ttu-id="e4332-117">Il valore della variabile partecipa all'espressione come una costante e quindi viene archiviato nella variabile o nella proprietà sul lato sinistro dell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e4332-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4332-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4332-118">See also</span></span>

- [<span data-ttu-id="e4332-119">Variabili</span><span class="sxs-lookup"><span data-stu-id="e4332-119">Variables</span></span>](index.md)
- [<span data-ttu-id="e4332-120">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="e4332-120">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="e4332-121">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="e4332-121">Object Variables</span></span>](object-variables.md)
