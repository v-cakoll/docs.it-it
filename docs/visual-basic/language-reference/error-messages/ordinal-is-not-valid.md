---
title: Ordinale non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 12d73b33e3c025b40c98d84e3507af7be1e1e91a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593603"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="74661-102">Ordinale non valido</span><span class="sxs-lookup"><span data-stu-id="74661-102">Ordinal is not valid</span></span>
<span data-ttu-id="74661-103">La chiamata a una libreria di collegamento dinamico (DLL) indica di usare un numero anziché un nome di stored procedure, tramite il `#num` sintassi.</span><span class="sxs-lookup"><span data-stu-id="74661-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="74661-104">Questo errore sono le seguenti cause possibili:</span><span class="sxs-lookup"><span data-stu-id="74661-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="74661-105">Un tentativo di convertire il `#num` espressione in un ordinale non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="74661-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="74661-106">Il `#num` specificato non specifica alcuna funzione nella DLL.</span><span class="sxs-lookup"><span data-stu-id="74661-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="74661-107">Una libreria dei tipi è una dichiarazione non valida risultante utilizzo interno di un numero ordinale non valido.</span><span class="sxs-lookup"><span data-stu-id="74661-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="74661-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="74661-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="74661-109">Verificare che l'espressione rappresenta un numero valido o chiamare la routine in base al nome.</span><span class="sxs-lookup"><span data-stu-id="74661-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2.  <span data-ttu-id="74661-110">Assicurarsi che `#num` identifica una funzione nella DLL valida.</span><span class="sxs-lookup"><span data-stu-id="74661-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3.  <span data-ttu-id="74661-111">Isolare la chiamata di routine che provoca il problema Commentando il codice.</span><span class="sxs-lookup"><span data-stu-id="74661-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="74661-112">Scrivere un `Declare` istruzione per la procedura e il problema al fornitore della libreria dei tipi di report.</span><span class="sxs-lookup"><span data-stu-id="74661-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74661-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74661-113">See Also</span></span>  
 [<span data-ttu-id="74661-114">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="74661-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
