---
title: Unicode (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: a61fd8e10c39569d92dd84180f678a1ff05a9310
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595722"
---
# <a name="unicode-visual-basic"></a><span data-ttu-id="00a3f-102">Unicode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00a3f-102">Unicode (Visual Basic)</span></span>
<span data-ttu-id="00a3f-103">Specifica che Visual Basic deve eseguire il marshalling di tutte le stringhe in valori Unicode indipendentemente dal nome della routine esterna che viene dichiarato.</span><span class="sxs-lookup"><span data-stu-id="00a3f-103">Specifies that Visual Basic should marshal all strings to Unicode values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="00a3f-104">Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non hanno accesso alle informazioni è necessario per chiamare correttamente la routine.</span><span class="sxs-lookup"><span data-stu-id="00a3f-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have in order to call the procedure correctly.</span></span> <span data-ttu-id="00a3f-105">Queste informazioni includono la procedura in cui si trova, come viene identificato, la sequenza di chiamata e tipo restituito e il set di caratteri stringa viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="00a3f-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="00a3f-106">Il [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea un riferimento a una routine esterna e fornisce le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="00a3f-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="00a3f-107">Il `charsetmodifier` parte il `Declare` istruzione fornisce le informazioni sul set di caratteri per il marshalling di stringhe durante una chiamata alla routine esterna.</span><span class="sxs-lookup"><span data-stu-id="00a3f-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information to marshal strings during a call to the external procedure.</span></span> <span data-ttu-id="00a3f-108">Influisce anche sulle modalità di ricerca di file esterno per il nome della routine esterna.</span><span class="sxs-lookup"><span data-stu-id="00a3f-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="00a3f-109">Il `Unicode` modificatore specifica che Visual Basic deve eseguire il marshalling di tutte le stringhe in valori Unicode e cercare la routine senza modificarne il nome durante la ricerca.</span><span class="sxs-lookup"><span data-stu-id="00a3f-109">The `Unicode` modifier specifies that Visual Basic should marshal all strings to Unicode values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="00a3f-110">Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="00a3f-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00a3f-111">Note</span><span class="sxs-lookup"><span data-stu-id="00a3f-111">Remarks</span></span>  
 <span data-ttu-id="00a3f-112">Il `Unicode` modificatore può essere utilizzato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="00a3f-112">The `Unicode` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="00a3f-113">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="00a3f-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="00a3f-114">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="00a3f-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="00a3f-115">Questa parola chiave non è supportata.</span><span class="sxs-lookup"><span data-stu-id="00a3f-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a3f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00a3f-116">See Also</span></span>  
 [<span data-ttu-id="00a3f-117">Ansi</span><span class="sxs-lookup"><span data-stu-id="00a3f-117">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [<span data-ttu-id="00a3f-118">Auto</span><span class="sxs-lookup"><span data-stu-id="00a3f-118">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)  
 [<span data-ttu-id="00a3f-119">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="00a3f-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
