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
ms.openlocfilehash: e4beb320b3aa0cadb790dd3ab92255496bc32f05
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802700"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="78b4e-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78b4e-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="78b4e-103">Specifica che Visual Basic deve eseguire il marshalling di stringhe in base alle regole di .NET Framework in base al nome esterno della routine esterna viene dichiarato.</span><span class="sxs-lookup"><span data-stu-id="78b4e-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="78b4e-104">Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic è privo di accesso alle informazioni necessario per chiamare correttamente la routine.</span><span class="sxs-lookup"><span data-stu-id="78b4e-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="78b4e-105">Queste informazioni includono la procedura in cui si trova, come viene identificato, la sequenza di chiamata e tipo restituito e il carattere stringa set utilizzato.</span><span class="sxs-lookup"><span data-stu-id="78b4e-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="78b4e-106">Il [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) crea un riferimento a una routine esterna e fornisce le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="78b4e-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="78b4e-107">Il `charsetmodifier` parte nel `Declare` istruzione fornisce le informazioni sul set di caratteri per il marshalling di stringhe durante una chiamata alla routine esterna.</span><span class="sxs-lookup"><span data-stu-id="78b4e-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="78b4e-108">Influisce anche sulla modalità di ricerca di file esterno per il nome della routine esterna.</span><span class="sxs-lookup"><span data-stu-id="78b4e-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="78b4e-109">Il `Auto` modificatore specifica che Visual Basic deve effettuare il marshalling delle stringhe in base alle regole di .NET Framework e che è necessario determinare il carattere di base impostato della piattaforma in fase di esecuzione ed eventualmente modificare il nome della routine esterna se esegue una ricerca iniziale si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="78b4e-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="78b4e-110">Per altre informazioni, vedere "Set di caratteri" nella [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="78b4e-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="78b4e-111">Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="78b4e-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78b4e-112">Note</span><span class="sxs-lookup"><span data-stu-id="78b4e-112">Remarks</span></span>  
 <span data-ttu-id="78b4e-113">Il `Auto` modificatore può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="78b4e-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="78b4e-114">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="78b4e-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="78b4e-115">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="78b4e-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="78b4e-116">Questa parola chiave non è supportata.</span><span class="sxs-lookup"><span data-stu-id="78b4e-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78b4e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78b4e-117">See also</span></span>

- [<span data-ttu-id="78b4e-118">Ansi</span><span class="sxs-lookup"><span data-stu-id="78b4e-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="78b4e-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="78b4e-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="78b4e-120">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="78b4e-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
