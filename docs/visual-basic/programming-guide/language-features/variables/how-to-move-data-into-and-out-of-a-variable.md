---
title: 'Procedura: spostare i dati all''interno e all''esterno di una variabile (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fefb1979e35cd7b5fa1917f8f1a57af575e51234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="3a930-102">Procedura: spostare i dati all'interno e all'esterno di una variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a930-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>
<span data-ttu-id="3a930-103">Archiviare un valore in una variabile inserendo il nome della variabile sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="3a930-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>  
  
## <a name="putting-data-in-a-variable"></a><span data-ttu-id="3a930-104">Inserimento di dati in una variabile</span><span class="sxs-lookup"><span data-stu-id="3a930-104">Putting Data in a Variable</span></span>  
  
#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="3a930-105">Per archiviare un valore in una variabile</span><span class="sxs-lookup"><span data-stu-id="3a930-105">To store a value in a variable</span></span>  
  
-   <span data-ttu-id="3a930-106">Utilizzare il nome della variabile sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="3a930-106">Use the variable name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="3a930-107">Nell'esempio seguente imposta il valore della variabile `alpha`.</span><span class="sxs-lookup"><span data-stu-id="3a930-107">The following example sets the value of the variable `alpha`.</span></span>  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     <span data-ttu-id="3a930-108">Il valore generato sul lato destro dell'istruzione di assegnazione è archiviato nella variabile.</span><span class="sxs-lookup"><span data-stu-id="3a930-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>  
  
## <a name="getting-data-from-a-variable"></a><span data-ttu-id="3a930-109">Recupero di dati da una variabile</span><span class="sxs-lookup"><span data-stu-id="3a930-109">Getting Data from a Variable</span></span>  
 <span data-ttu-id="3a930-110">Per recuperare il valore di una variabile, includendo il nome della variabile in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="3a930-110">You retrieve a variable's value by including the variable name in an expression.</span></span>  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="3a930-111">Per recuperare un valore da una variabile</span><span class="sxs-lookup"><span data-stu-id="3a930-111">To retrieve a value from a variable</span></span>  
  
-   <span data-ttu-id="3a930-112">Utilizzare il nome della variabile in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="3a930-112">Use the variable name in an expression.</span></span> <span data-ttu-id="3a930-113">È possibile utilizzare una variabile in qualsiasi punto è possibile utilizzare una costante o valore letterale, tranne in un'espressione che definisce il valore di una costante.</span><span class="sxs-lookup"><span data-stu-id="3a930-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>  
  
     <span data-ttu-id="3a930-114">-oppure-</span><span class="sxs-lookup"><span data-stu-id="3a930-114">-or-</span></span>  
  
-   <span data-ttu-id="3a930-115">Utilizzare il nome della variabile seguente uguali (`=`) eseguire l'accesso in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="3a930-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="3a930-116">Nell'esempio seguente legge il valore della variabile `startValue` e quindi utilizza il valore della variabile `counter` in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="3a930-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     <span data-ttu-id="3a930-117">Il valore della variabile fa parte dell'espressione come una costante, e quindi viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="3a930-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a930-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a930-118">See Also</span></span>  
 [<span data-ttu-id="3a930-119">Variabili</span><span class="sxs-lookup"><span data-stu-id="3a930-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="3a930-120">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="3a930-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="3a930-121">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="3a930-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
