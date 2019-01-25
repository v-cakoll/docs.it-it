---
title: Ansi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: e474bd686cc753a0265df1fc2914a73d1b62f1b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737322"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="baf13-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="baf13-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="baf13-103">Specifica che Visual Basic deve eseguire il marshalling di tutte le stringhe in valori American National Standards Institute (ANSI) indipendentemente dal nome della routine esterna viene dichiarato.</span><span class="sxs-lookup"><span data-stu-id="baf13-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="baf13-104">Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic è privo di accesso per le informazioni necessarie per chiamare la routine in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="baf13-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="baf13-105">Queste informazioni includono la procedura in cui si trova, come viene identificato, la sequenza di chiamata e tipo restituito e il carattere stringa set utilizzato.</span><span class="sxs-lookup"><span data-stu-id="baf13-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="baf13-106">Il [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) crea un riferimento a una routine esterna e fornisce le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="baf13-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="baf13-107">Il `charsetmodifier` parte nel `Declare` istruzione fornisce le informazioni sul set di caratteri per il marshalling di stringhe durante una chiamata alla routine esterna.</span><span class="sxs-lookup"><span data-stu-id="baf13-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="baf13-108">Influisce anche sulla modalità di ricerca di file esterno per il nome della routine esterna.</span><span class="sxs-lookup"><span data-stu-id="baf13-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="baf13-109">Il `Ansi` modificatore specifica che Visual Basic deve eseguire il marshalling di tutte le stringhe in valori ANSI e cercare la routine senza modificarne il nome durante la ricerca.</span><span class="sxs-lookup"><span data-stu-id="baf13-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="baf13-110">Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="baf13-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baf13-111">Note</span><span class="sxs-lookup"><span data-stu-id="baf13-111">Remarks</span></span>  
 <span data-ttu-id="baf13-112">Il `Ansi` modificatore può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="baf13-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="baf13-113">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="baf13-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="baf13-114">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="baf13-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="baf13-115">Questa parola chiave non è supportata.</span><span class="sxs-lookup"><span data-stu-id="baf13-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf13-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baf13-116">See also</span></span>
- [<span data-ttu-id="baf13-117">Auto</span><span class="sxs-lookup"><span data-stu-id="baf13-117">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="baf13-118">Unicode</span><span class="sxs-lookup"><span data-stu-id="baf13-118">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="baf13-119">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="baf13-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
