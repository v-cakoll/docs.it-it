---
title: Sub o Function non definita (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 6bca368e13a32559bcb7cbb028dcaa1dea0353e3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819788"
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="39816-102">Sub o Function non definita (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39816-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="39816-103">Oggetto `Sub` o `Function` deve essere definito per essere chiamati.</span><span class="sxs-lookup"><span data-stu-id="39816-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="39816-104">Alcune cause possibili di questo errore sono:</span><span class="sxs-lookup"><span data-stu-id="39816-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="39816-105">Errore di ortografia il nome della routine.</span><span class="sxs-lookup"><span data-stu-id="39816-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="39816-106">Tentativo di chiamare una routine da un altro progetto senza aggiungere in modo esplicito un riferimento al progetto nella **riferimenti** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="39816-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="39816-107">Specifica una routine che non è visibile alla routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="39816-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="39816-108">Dichiara una routine di libreria a collegamento dinamico (DLL) Windows o routine Macintosh risorsa codice che non si trova la risorsa di libreria o codice specificata.</span><span class="sxs-lookup"><span data-stu-id="39816-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="39816-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="39816-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="39816-110">Assicurarsi che il nome della routine sia digitato correttamente.</span><span class="sxs-lookup"><span data-stu-id="39816-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2.  <span data-ttu-id="39816-111">Trovare il nome del progetto contenente le procedure da chiamare **riferimenti** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="39816-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="39816-112">Se non viene visualizzato, scegliere il **esplorare** pulsante per eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="39816-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="39816-113">Selezionare la casella di controllo a sinistra del nome del progetto e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="39816-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="39816-114">Controllare il nome della routine.</span><span class="sxs-lookup"><span data-stu-id="39816-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39816-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39816-115">See also</span></span>

- [<span data-ttu-id="39816-116">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="39816-116">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="39816-117">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="39816-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="39816-118">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="39816-118">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="39816-119">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="39816-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
