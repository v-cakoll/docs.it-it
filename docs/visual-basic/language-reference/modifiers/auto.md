---
title: Automatico
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: b9bdeed55788252c71b8fb1c995c140cbfdf60eb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373128"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="8458a-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8458a-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="8458a-103">Specifica che Visual Basic deve effettuare il marshalling delle stringhe in base alle regole di .NET Framework in base al nome esterno della procedura esterna dichiarata.</span><span class="sxs-lookup"><span data-stu-id="8458a-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="8458a-104">Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non ha accesso alle informazioni necessarie per chiamare correttamente la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8458a-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="8458a-105">Queste informazioni includono la posizione in cui si trova la stored procedure, la modalità di identificazione, la sequenza chiamante e il tipo restituito e il set di caratteri stringa utilizzato.</span><span class="sxs-lookup"><span data-stu-id="8458a-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="8458a-106">L' [istruzione Declare](../statements/declare-statement.md) crea un riferimento a una procedura esterna e fornisce le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="8458a-106">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="8458a-107">La `charsetmodifier` parte nell' `Declare` istruzione fornisce le informazioni sul set di caratteri per il marshalling delle stringhe durante una chiamata alla procedura esterna.</span><span class="sxs-lookup"><span data-stu-id="8458a-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="8458a-108">Influiscono inoltre sul modo in cui Visual Basic Cerca nel file esterno il nome della procedura esterna.</span><span class="sxs-lookup"><span data-stu-id="8458a-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="8458a-109">Il `Auto` modificatore specifica che Visual Basic deve effettuare il marshalling delle stringhe in base alle regole di .NET Framework e che deve determinare il set di caratteri di base della piattaforma di runtime ed eventualmente modificare il nome della procedura esterna se la ricerca iniziale ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="8458a-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="8458a-110">Per ulteriori informazioni, vedere "set di caratteri" nell' [istruzione Declare](../statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8458a-110">For more information, see "Character Sets" in [Declare Statement](../statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="8458a-111">Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8458a-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8458a-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="8458a-112">Remarks</span></span>  
 <span data-ttu-id="8458a-113">Il `Auto` modificatore può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="8458a-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="8458a-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="8458a-114">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="8458a-115">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="8458a-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="8458a-116">Questa parola chiave non è supportata.</span><span class="sxs-lookup"><span data-stu-id="8458a-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8458a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8458a-117">See also</span></span>

- [<span data-ttu-id="8458a-118">Ansi</span><span class="sxs-lookup"><span data-stu-id="8458a-118">Ansi</span></span>](ansi.md)
- [<span data-ttu-id="8458a-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="8458a-119">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="8458a-120">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8458a-120">Keywords</span></span>](../keywords/index.md)
