---
title: Ordinale non valido
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d31d0fba19cc16004c0b56786af30603d0c509ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="02766-102">Ordinale non valido</span><span class="sxs-lookup"><span data-stu-id="02766-102">Ordinal is not valid</span></span>
<span data-ttu-id="02766-103">La chiamata a una libreria di collegamento dinamico (DLL) indica di usare un numero anziché un nome di stored procedure, tramite il `#num` sintassi.</span><span class="sxs-lookup"><span data-stu-id="02766-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="02766-104">Questo errore sono le seguenti cause possibili:</span><span class="sxs-lookup"><span data-stu-id="02766-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="02766-105">Un tentativo di convertire il `#num` espressione in un ordinale non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="02766-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="02766-106">Il `#num` specificato non specifica alcuna funzione nella DLL.</span><span class="sxs-lookup"><span data-stu-id="02766-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="02766-107">Una libreria dei tipi è una dichiarazione non valida risultante utilizzo interno di un numero ordinale non valido.</span><span class="sxs-lookup"><span data-stu-id="02766-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="02766-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="02766-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="02766-109">Verificare che l'espressione rappresenta un numero valido o chiamare la routine in base al nome.</span><span class="sxs-lookup"><span data-stu-id="02766-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2.  <span data-ttu-id="02766-110">Assicurarsi che `#num` identifica una funzione nella DLL valida.</span><span class="sxs-lookup"><span data-stu-id="02766-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3.  <span data-ttu-id="02766-111">Isolare la chiamata di routine che provoca il problema Commentando il codice.</span><span class="sxs-lookup"><span data-stu-id="02766-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="02766-112">Scrivere un `Declare` istruzione per la procedura e il problema al fornitore della libreria dei tipi di report.</span><span class="sxs-lookup"><span data-stu-id="02766-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02766-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02766-113">See Also</span></span>  
 [<span data-ttu-id="02766-114">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="02766-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
