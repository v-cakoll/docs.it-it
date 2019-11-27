---
title: Sub o Function non definita
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 8b81460eccb6be8baa2ea7bc68d0f80c9d16398e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349572"
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="04501-102">Sub o Function non definita (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04501-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="04501-103">Per poter essere chiamato, è necessario definire un `Sub` o `Function`.</span><span class="sxs-lookup"><span data-stu-id="04501-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="04501-104">Alcune cause possibili di questo errore sono:</span><span class="sxs-lookup"><span data-stu-id="04501-104">Possible causes of this error include:</span></span>  
  
- <span data-ttu-id="04501-105">Ortografia del nome della procedura.</span><span class="sxs-lookup"><span data-stu-id="04501-105">Misspelling the procedure name.</span></span>  
  
- <span data-ttu-id="04501-106">Tentativo di chiamare una routine da un altro progetto senza aggiungere esplicitamente un riferimento a tale progetto nella finestra di dialogo **riferimenti** .</span><span class="sxs-lookup"><span data-stu-id="04501-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
- <span data-ttu-id="04501-107">Specifica di una routine che non è visibile alla procedura chiamante.</span><span class="sxs-lookup"><span data-stu-id="04501-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
- <span data-ttu-id="04501-108">Dichiarazione di una routine della libreria di collegamento dinamico (DLL) di Windows o di una routine di risorsa di codice Macintosh che non si trova nella libreria o nella risorsa di codice specificata.</span><span class="sxs-lookup"><span data-stu-id="04501-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="04501-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="04501-109">To correct this error</span></span>  
  
1. <span data-ttu-id="04501-110">Verificare che il nome della stored procedure sia stato digitato correttamente.</span><span class="sxs-lookup"><span data-stu-id="04501-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2. <span data-ttu-id="04501-111">Trovare il nome del progetto contenente la procedura che si desidera chiamare nella finestra di dialogo **riferimenti** .</span><span class="sxs-lookup"><span data-stu-id="04501-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="04501-112">Se non viene visualizzato, fare clic sul pulsante **Sfoglia** per cercarlo.</span><span class="sxs-lookup"><span data-stu-id="04501-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="04501-113">Selezionare la casella di controllo a sinistra del nome del progetto, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="04501-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="04501-114">Verificare il nome della routine.</span><span class="sxs-lookup"><span data-stu-id="04501-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04501-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04501-115">See also</span></span>

- [<span data-ttu-id="04501-116">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="04501-116">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="04501-117">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="04501-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="04501-118">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="04501-118">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="04501-119">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="04501-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
