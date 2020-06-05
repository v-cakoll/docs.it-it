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
ms.openlocfilehash: 9b1bc40bb52244deefc0486d3a40c4b961ad1ee5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402681"
---
# <a name="unicode-visual-basic"></a><span data-ttu-id="10df0-102">Unicode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10df0-102">Unicode (Visual Basic)</span></span>
<span data-ttu-id="10df0-103">Specifica che Visual Basic deve effettuare il marshalling di tutte le stringhe in valori Unicode indipendentemente dal nome della procedura esterna dichiarata.</span><span class="sxs-lookup"><span data-stu-id="10df0-103">Specifies that Visual Basic should marshal all strings to Unicode values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="10df0-104">Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non ha accesso alle informazioni necessarie per chiamare correttamente la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="10df0-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have in order to call the procedure correctly.</span></span> <span data-ttu-id="10df0-105">Queste informazioni includono la posizione in cui si trova la stored procedure, la modalità di identificazione, la sequenza chiamante e il tipo restituito e il set di caratteri stringa utilizzato.</span><span class="sxs-lookup"><span data-stu-id="10df0-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="10df0-106">L' [istruzione Declare](../statements/declare-statement.md) crea un riferimento a una procedura esterna e fornisce le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="10df0-106">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="10df0-107">La `charsetmodifier` parte nell' `Declare` istruzione fornisce le informazioni sul set di caratteri per il marshalling delle stringhe durante una chiamata alla procedura esterna.</span><span class="sxs-lookup"><span data-stu-id="10df0-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information to marshal strings during a call to the external procedure.</span></span> <span data-ttu-id="10df0-108">Influiscono inoltre sul modo in cui Visual Basic Cerca nel file esterno il nome della procedura esterna.</span><span class="sxs-lookup"><span data-stu-id="10df0-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="10df0-109">Il `Unicode` modificatore specifica che Visual Basic necessario effettuare il marshalling di tutte le stringhe in valori Unicode e cercare la routine senza modificarne il nome durante la ricerca.</span><span class="sxs-lookup"><span data-stu-id="10df0-109">The `Unicode` modifier specifies that Visual Basic should marshal all strings to Unicode values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="10df0-110">Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="10df0-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10df0-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="10df0-111">Remarks</span></span>  
 <span data-ttu-id="10df0-112">Il `Unicode` modificatore può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="10df0-112">The `Unicode` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="10df0-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="10df0-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="10df0-114">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="10df0-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="10df0-115">Questa parola chiave non è supportata.</span><span class="sxs-lookup"><span data-stu-id="10df0-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10df0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10df0-116">See also</span></span>

- [<span data-ttu-id="10df0-117">Ansi</span><span class="sxs-lookup"><span data-stu-id="10df0-117">Ansi</span></span>](ansi.md)
- [<span data-ttu-id="10df0-118">Auto</span><span class="sxs-lookup"><span data-stu-id="10df0-118">Auto</span></span>](auto.md)
- [<span data-ttu-id="10df0-119">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="10df0-119">Keywords</span></span>](../keywords/index.md)
