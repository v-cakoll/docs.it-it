---
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 67792e52c21555bef46548e9ab0a6ebd32061071
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373200"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="d9e79-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9e79-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="d9e79-103">Specifica che Visual Basic deve effettuare il marshalling di tutte le stringhe in valori di American National Standards Institute (ANSI) indipendentemente dal nome della procedura esterna dichiarata.</span><span class="sxs-lookup"><span data-stu-id="d9e79-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="d9e79-104">Quando si chiama una routine definita all'esterno del progetto, il compilatore Visual Basic non ha accesso alle informazioni necessarie per chiamare correttamente la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d9e79-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="d9e79-105">Queste informazioni includono la posizione in cui si trova la stored procedure, la modalità di identificazione, la sequenza chiamante e il tipo restituito e il set di caratteri stringa utilizzato.</span><span class="sxs-lookup"><span data-stu-id="d9e79-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="d9e79-106">L' [istruzione Declare](../statements/declare-statement.md) crea un riferimento a una procedura esterna e fornisce le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="d9e79-106">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="d9e79-107">La `charsetmodifier` parte nell' `Declare` istruzione fornisce le informazioni sul set di caratteri per il marshalling delle stringhe durante una chiamata alla procedura esterna.</span><span class="sxs-lookup"><span data-stu-id="d9e79-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="d9e79-108">Influiscono inoltre sul modo in cui Visual Basic Cerca nel file esterno il nome della procedura esterna.</span><span class="sxs-lookup"><span data-stu-id="d9e79-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="d9e79-109">Il `Ansi` modificatore specifica che Visual Basic deve effettuare il marshalling di tutte le stringhe in valori ANSI ed esaminare la procedura senza modificarne il nome durante la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d9e79-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="d9e79-110">Se non viene specificato alcun modificatore del set di caratteri, `Ansi` è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="d9e79-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9e79-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="d9e79-111">Remarks</span></span>  
 <span data-ttu-id="d9e79-112">Il `Ansi` modificatore può essere usato in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="d9e79-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="d9e79-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="d9e79-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="d9e79-114">Note per gli sviluppatori di Smart Device</span><span class="sxs-lookup"><span data-stu-id="d9e79-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="d9e79-115">Questa parola chiave non è supportata.</span><span class="sxs-lookup"><span data-stu-id="d9e79-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e79-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9e79-116">See also</span></span>

- [<span data-ttu-id="d9e79-117">Auto</span><span class="sxs-lookup"><span data-stu-id="d9e79-117">Auto</span></span>](auto.md)
- [<span data-ttu-id="d9e79-118">Unicode</span><span class="sxs-lookup"><span data-stu-id="d9e79-118">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="d9e79-119">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d9e79-119">Keywords</span></span>](../keywords/index.md)
