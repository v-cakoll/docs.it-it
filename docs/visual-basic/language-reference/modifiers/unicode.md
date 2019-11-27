---
title: Unicode
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: c4286ed9e9d5fd768ae29b7050b3d1505ccca9dd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344214"
---
# <a name="unicode-visual-basic"></a><span data-ttu-id="63055-102">Unicode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63055-102">Unicode (Visual Basic)</span></span>
<span data-ttu-id="63055-103">Specifica che Visual Basic deve effettuare il marshalling di tutte le stringhe in valori Unicode indipendentemente dal nome della procedura esterna dichiarata.</span><span class="sxs-lookup"><span data-stu-id="63055-103">Specifies that Visual Basic should marshal all strings to Unicode values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="63055-104">Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non ha accesso alle informazioni necessarie per chiamare correttamente la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="63055-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have in order to call the procedure correctly.</span></span> <span data-ttu-id="63055-105">Queste informazioni includono la posizione in cui si trova la stored procedure, la modalità di identificazione, la sequenza chiamante e il tipo restituito e il set di caratteri stringa utilizzato.</span><span class="sxs-lookup"><span data-stu-id="63055-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="63055-106">L' [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea un riferimento a una procedura esterna e fornisce le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="63055-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="63055-107">La `charsetmodifier` parte nell'istruzione `Declare` fornisce le informazioni sul set di caratteri per eseguire il marshalling delle stringhe durante una chiamata alla procedura esterna.</span><span class="sxs-lookup"><span data-stu-id="63055-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information to marshal strings during a call to the external procedure.</span></span> <span data-ttu-id="63055-108">Influiscono inoltre sul modo in cui Visual Basic Cerca nel file esterno il nome della procedura esterna.</span><span class="sxs-lookup"><span data-stu-id="63055-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="63055-109">Il modificatore `Unicode` specifica che Visual Basic deve effettuare il marshalling di tutte le stringhe in valori Unicode e deve cercare la routine senza modificarne il nome durante la ricerca.</span><span class="sxs-lookup"><span data-stu-id="63055-109">The `Unicode` modifier specifies that Visual Basic should marshal all strings to Unicode values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="63055-110">Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="63055-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63055-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="63055-111">Remarks</span></span>  
 <span data-ttu-id="63055-112">Il modificatore `Unicode` può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="63055-112">The `Unicode` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="63055-113">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="63055-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="63055-114">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="63055-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="63055-115">Questa parola chiave non è supportata.</span><span class="sxs-lookup"><span data-stu-id="63055-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63055-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63055-116">See also</span></span>

- [<span data-ttu-id="63055-117">Ansi</span><span class="sxs-lookup"><span data-stu-id="63055-117">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="63055-118">Auto</span><span class="sxs-lookup"><span data-stu-id="63055-118">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="63055-119">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="63055-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
