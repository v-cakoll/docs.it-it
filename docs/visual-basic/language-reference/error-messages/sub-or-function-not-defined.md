---
title: Sub o Function non definita (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6237ca26b06bdffa06499607e634b3222725c189
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="79250-102">Sub o Function non definita (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79250-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="79250-103">Oggetto `Sub` o `Function` deve essere definito per essere chiamati.</span><span class="sxs-lookup"><span data-stu-id="79250-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="79250-104">Alcune cause possibili di questo errore sono:</span><span class="sxs-lookup"><span data-stu-id="79250-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="79250-105">Errore di ortografia il nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="79250-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="79250-106">Tentativo di chiamare una routine da un altro progetto senza aggiungere in modo esplicito un riferimento a progetto nel **riferimenti** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="79250-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="79250-107">Specifica una routine che non è visibile alla routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="79250-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="79250-108">Dichiarazione di una routine di libreria a collegamento dinamico (DLL) di Windows o di una routine di risorsa codice Macintosh che non si trova la risorsa di libreria o di codice specificata.</span><span class="sxs-lookup"><span data-stu-id="79250-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="79250-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="79250-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="79250-110">Assicurarsi che il nome della routine sia digitato correttamente.</span><span class="sxs-lookup"><span data-stu-id="79250-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2.  <span data-ttu-id="79250-111">Trovare il nome del progetto contenente la routine da chiamare **riferimenti** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="79250-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="79250-112">Se non è visualizzato, fare clic su di **Sfoglia** pulsante per eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="79250-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="79250-113">Selezionare la casella di controllo a sinistra del nome del progetto e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="79250-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="79250-114">Controllare il nome della routine.</span><span class="sxs-lookup"><span data-stu-id="79250-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79250-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79250-115">See Also</span></span>  
 [<span data-ttu-id="79250-116">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="79250-116">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="79250-117">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="79250-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="79250-118">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="79250-118">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="79250-119">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="79250-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
