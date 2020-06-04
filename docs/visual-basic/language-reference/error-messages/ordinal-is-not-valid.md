---
title: Ordinale non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 7b9bd8435b56dd5e33d14eb35d76aacc7d60c8b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413053"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="4c4b8-102">Ordinale non valido</span><span class="sxs-lookup"><span data-stu-id="4c4b8-102">Ordinal is not valid</span></span>
<span data-ttu-id="4c4b8-103">La chiamata a una libreria a collegamento dinamico (DLL) indica di usare un numero anziché un nome di routine, usando la `#num` sintassi.</span><span class="sxs-lookup"><span data-stu-id="4c4b8-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="4c4b8-104">Questo errore presenta le possibili cause seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c4b8-104">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="4c4b8-105">Tentativo di conversione dell' `#num` espressione in un ordinale non riuscito.</span><span class="sxs-lookup"><span data-stu-id="4c4b8-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
- <span data-ttu-id="4c4b8-106">Il `#num` parametro specificato non specifica alcuna funzione nella dll.</span><span class="sxs-lookup"><span data-stu-id="4c4b8-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
- <span data-ttu-id="4c4b8-107">Una libreria dei tipi ha una dichiarazione non valida che comporta l'uso interno di un numero ordinale non valido.</span><span class="sxs-lookup"><span data-stu-id="4c4b8-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4c4b8-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4c4b8-108">To correct this error</span></span>  
  
1. <span data-ttu-id="4c4b8-109">Verificare che l'espressione rappresenti un numero valido o chiamare la procedura in base al nome.</span><span class="sxs-lookup"><span data-stu-id="4c4b8-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="4c4b8-110">Assicurarsi che `#num` identifichi una funzione valida nella dll.</span><span class="sxs-lookup"><span data-stu-id="4c4b8-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="4c4b8-111">Isolare la chiamata di procedura che causa il problema impostando come commento il codice.</span><span class="sxs-lookup"><span data-stu-id="4c4b8-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="4c4b8-112">Scrivere un' `Declare` istruzione per la procedura e segnalare il problema al fornitore della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="4c4b8-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c4b8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c4b8-113">See also</span></span>

- [<span data-ttu-id="4c4b8-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="4c4b8-114">Declare Statement</span></span>](../statements/declare-statement.md)
