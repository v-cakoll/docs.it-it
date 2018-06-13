---
title: Auto (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 414998b4bef526060e7ba4f584fa071fbd0acaa5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595875"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="8e5c5-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e5c5-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="8e5c5-103">Specifica che Visual Basic deve eseguire il marshalling di stringhe in base alle regole di .NET Framework in base al nome esterno della routine esterna che viene dichiarato.</span><span class="sxs-lookup"><span data-stu-id="8e5c5-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="8e5c5-104">Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non hanno accesso alle informazioni necessari per chiamare correttamente la routine.</span><span class="sxs-lookup"><span data-stu-id="8e5c5-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="8e5c5-105">Queste informazioni includono la procedura in cui si trova, come viene identificato, la sequenza di chiamata e tipo restituito e il set di caratteri stringa viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="8e5c5-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="8e5c5-106">Il [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea un riferimento a una routine esterna e fornisce le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="8e5c5-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="8e5c5-107">Il `charsetmodifier` parte il `Declare` istruzione fornisce le informazioni sul set di caratteri per il marshalling di stringhe durante una chiamata alla routine esterna.</span><span class="sxs-lookup"><span data-stu-id="8e5c5-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="8e5c5-108">Influisce anche sulle modalità di ricerca di file esterno per il nome della routine esterna.</span><span class="sxs-lookup"><span data-stu-id="8e5c5-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="8e5c5-109">Il `Auto` modificatore specifica che Visual Basic deve eseguire il marshalling di stringhe in base alle regole di .NET Framework e che è necessario determinare il carattere di base impostato della piattaforma in fase di esecuzione ed eventualmente modificare il nome della routine esterna se esegue la ricerca iniziale ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="8e5c5-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="8e5c5-110">Per ulteriori informazioni, vedere "Set di caratteri" in [istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8e5c5-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="8e5c5-111">Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8e5c5-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e5c5-112">Note</span><span class="sxs-lookup"><span data-stu-id="8e5c5-112">Remarks</span></span>  
 <span data-ttu-id="8e5c5-113">Il `Auto` modificatore può essere utilizzato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="8e5c5-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="8e5c5-114">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="8e5c5-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="8e5c5-115">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="8e5c5-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="8e5c5-116">Questa parola chiave non è supportata.</span><span class="sxs-lookup"><span data-stu-id="8e5c5-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5c5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e5c5-117">See Also</span></span>  
 [<span data-ttu-id="8e5c5-118">Ansi</span><span class="sxs-lookup"><span data-stu-id="8e5c5-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [<span data-ttu-id="8e5c5-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="8e5c5-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [<span data-ttu-id="8e5c5-120">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8e5c5-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
