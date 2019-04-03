---
title: Ordinale non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: f3207c2cc237ae22c295c2b3ed56f18601625226
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822271"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="e8558-102">Ordinale non valido</span><span class="sxs-lookup"><span data-stu-id="e8558-102">Ordinal is not valid</span></span>
<span data-ttu-id="e8558-103">La chiamata a una libreria di collegamento dinamico (DLL) indica di usare un numero anziché un nome di procedura, utilizzando il `#num` sintassi.</span><span class="sxs-lookup"><span data-stu-id="e8558-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="e8558-104">Questo errore sono le seguenti cause possibili:</span><span class="sxs-lookup"><span data-stu-id="e8558-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="e8558-105">Un tentativo di convertire il `#num` espressione da un numero ordinale non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="e8558-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="e8558-106">Il `#num` specificato non viene specificata alcuna funzione di DLL.</span><span class="sxs-lookup"><span data-stu-id="e8558-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="e8558-107">Una libreria dei tipi dispone di una dichiarazione non valida conseguente uso interno di un numero ordinale non valido.</span><span class="sxs-lookup"><span data-stu-id="e8558-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e8558-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e8558-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="e8558-109">Verificare che l'espressione rappresenta un numero valido oppure chiamare la routine in base al nome.</span><span class="sxs-lookup"><span data-stu-id="e8558-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2.  <span data-ttu-id="e8558-110">Assicurarsi che `#num` identifica una funzione nella DLL valida.</span><span class="sxs-lookup"><span data-stu-id="e8558-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3.  <span data-ttu-id="e8558-111">Isolare la chiamata di procedura provoca il problema Commentando il codice.</span><span class="sxs-lookup"><span data-stu-id="e8558-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="e8558-112">Scrivere un `Declare` istruzione per la routine e di segnalare il problema al fornitore della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="e8558-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8558-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8558-113">See also</span></span>

- [<span data-ttu-id="e8558-114">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="e8558-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
