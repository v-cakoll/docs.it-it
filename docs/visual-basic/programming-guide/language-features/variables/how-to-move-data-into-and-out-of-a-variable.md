---
title: 'Procedura: Spostare dati da e verso una variabile (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: 30d1c0ab91724ac556e59b272782513ee8b8067b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818537"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="2a64e-102">Procedura: Spostare dati da e verso una variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a64e-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>
<span data-ttu-id="2a64e-103">Archiviare un valore in una variabile, inserendo il nome della variabile sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="2a64e-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>  
  
## <a name="putting-data-in-a-variable"></a><span data-ttu-id="2a64e-104">Inserire dati in una variabile</span><span class="sxs-lookup"><span data-stu-id="2a64e-104">Putting Data in a Variable</span></span>  
  
#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="2a64e-105">Per archiviare un valore in una variabile</span><span class="sxs-lookup"><span data-stu-id="2a64e-105">To store a value in a variable</span></span>  
  
-   <span data-ttu-id="2a64e-106">Usare il nome della variabile sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="2a64e-106">Use the variable name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="2a64e-107">Nell'esempio seguente imposta il valore della variabile `alpha`.</span><span class="sxs-lookup"><span data-stu-id="2a64e-107">The following example sets the value of the variable `alpha`.</span></span>  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     <span data-ttu-id="2a64e-108">Il valore generato sul lato destro dell'istruzione di assegnazione viene archiviato nella variabile.</span><span class="sxs-lookup"><span data-stu-id="2a64e-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>  
  
## <a name="getting-data-from-a-variable"></a><span data-ttu-id="2a64e-109">Recupero di dati da una variabile</span><span class="sxs-lookup"><span data-stu-id="2a64e-109">Getting Data from a Variable</span></span>  
 <span data-ttu-id="2a64e-110">Per recuperare il valore della variabile, includendo il nome della variabile in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="2a64e-110">You retrieve a variable's value by including the variable name in an expression.</span></span>  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="2a64e-111">Per recuperare un valore da una variabile</span><span class="sxs-lookup"><span data-stu-id="2a64e-111">To retrieve a value from a variable</span></span>  
  
-   <span data-ttu-id="2a64e-112">Usare il nome della variabile in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="2a64e-112">Use the variable name in an expression.</span></span> <span data-ttu-id="2a64e-113">È possibile usare una variabile in un punto qualsiasi è possibile usare una costante o valore letterale, tranne in un'espressione che definisce il valore di una costante.</span><span class="sxs-lookup"><span data-stu-id="2a64e-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>  
  
     <span data-ttu-id="2a64e-114">-oppure-</span><span class="sxs-lookup"><span data-stu-id="2a64e-114">-or-</span></span>  
  
-   <span data-ttu-id="2a64e-115">Usare il nome della variabile seguendo uguali (`=`) Accedi a un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="2a64e-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="2a64e-116">Nell'esempio seguente legge il valore della variabile `startValue` e quindi Usa il valore della variabile `counter` in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="2a64e-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     <span data-ttu-id="2a64e-117">Il valore della variabile fa parte dell'espressione come una costante e quindi viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="2a64e-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a64e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a64e-118">See also</span></span>

- [<span data-ttu-id="2a64e-119">Variabili</span><span class="sxs-lookup"><span data-stu-id="2a64e-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="2a64e-120">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="2a64e-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="2a64e-121">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="2a64e-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
