---
title: Ordinale non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 740243c744a7ba5391659894812a00d80555fd80
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665671"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="a9484-102">Ordinale non valido</span><span class="sxs-lookup"><span data-stu-id="a9484-102">Ordinal is not valid</span></span>
<span data-ttu-id="a9484-103">La chiamata a una libreria di collegamento dinamico (DLL) indica di usare un numero anziché un nome di procedura, utilizzando il `#num` sintassi.</span><span class="sxs-lookup"><span data-stu-id="a9484-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="a9484-104">Questo errore sono le seguenti cause possibili:</span><span class="sxs-lookup"><span data-stu-id="a9484-104">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="a9484-105">Un tentativo di convertire il `#num` espressione da un numero ordinale non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="a9484-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
- <span data-ttu-id="a9484-106">Il `#num` specificato non viene specificata alcuna funzione di DLL.</span><span class="sxs-lookup"><span data-stu-id="a9484-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
- <span data-ttu-id="a9484-107">Una libreria dei tipi dispone di una dichiarazione non valida conseguente uso interno di un numero ordinale non valido.</span><span class="sxs-lookup"><span data-stu-id="a9484-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a9484-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a9484-108">To correct this error</span></span>  
  
1. <span data-ttu-id="a9484-109">Verificare che l'espressione rappresenta un numero valido oppure chiamare la routine in base al nome.</span><span class="sxs-lookup"><span data-stu-id="a9484-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="a9484-110">Assicurarsi che `#num` identifica una funzione nella DLL valida.</span><span class="sxs-lookup"><span data-stu-id="a9484-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="a9484-111">Isolare la chiamata di procedura provoca il problema Commentando il codice.</span><span class="sxs-lookup"><span data-stu-id="a9484-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="a9484-112">Scrivere un `Declare` istruzione per la routine e di segnalare il problema al fornitore della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="a9484-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9484-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9484-113">See also</span></span>

- [<span data-ttu-id="a9484-114">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="a9484-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
