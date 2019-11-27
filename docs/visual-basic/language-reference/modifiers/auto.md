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
ms.openlocfilehash: 7ea46e5f8b882bb986f23e792b240bad0c5be7a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351613"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="d5290-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5290-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="d5290-103">Specifica che Visual Basic deve effettuare il marshalling delle stringhe in base alle regole di .NET Framework in base al nome esterno della procedura esterna dichiarata.</span><span class="sxs-lookup"><span data-stu-id="d5290-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="d5290-104">Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non ha accesso alle informazioni necessarie per chiamare correttamente la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d5290-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="d5290-105">Queste informazioni includono la posizione in cui si trova la stored procedure, la modalità di identificazione, la sequenza chiamante e il tipo restituito e il set di caratteri stringa utilizzato.</span><span class="sxs-lookup"><span data-stu-id="d5290-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="d5290-106">L' [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea un riferimento a una procedura esterna e fornisce le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="d5290-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="d5290-107">La `charsetmodifier` parte nell'istruzione `Declare` fornisce le informazioni sul set di caratteri per il marshalling delle stringhe durante una chiamata alla procedura esterna.</span><span class="sxs-lookup"><span data-stu-id="d5290-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="d5290-108">Influiscono inoltre sul modo in cui Visual Basic Cerca nel file esterno il nome della procedura esterna.</span><span class="sxs-lookup"><span data-stu-id="d5290-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="d5290-109">Il modificatore `Auto` specifica che Visual Basic deve effettuare il marshalling delle stringhe in base alle regole di .NET Framework e che deve determinare il set di caratteri di base della piattaforma di runtime ed eventualmente modificare il nome della procedura esterna se la ricerca iniziale ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d5290-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="d5290-110">Per ulteriori informazioni, vedere "set di caratteri" nell' [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d5290-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="d5290-111">Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="d5290-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5290-112">Note</span><span class="sxs-lookup"><span data-stu-id="d5290-112">Remarks</span></span>  
 <span data-ttu-id="d5290-113">Il modificatore `Auto` può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="d5290-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="d5290-114">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="d5290-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="d5290-115">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="d5290-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="d5290-116">Questa parola chiave non è supportata.</span><span class="sxs-lookup"><span data-stu-id="d5290-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5290-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5290-117">See also</span></span>

- [<span data-ttu-id="d5290-118">Ansi</span><span class="sxs-lookup"><span data-stu-id="d5290-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="d5290-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="d5290-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="d5290-120">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d5290-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
