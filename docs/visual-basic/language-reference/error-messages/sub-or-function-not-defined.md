---
title: Sub o Function non definita (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID35
dev_langs:
- VB
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 837beec039e1fb8f8a796b2781d93de6d4cfb33a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="d573e-102">Sub o Function non definita (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d573e-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="d573e-103">Oggetto `Sub` o `Function` deve essere definito per essere chiamati.</span><span class="sxs-lookup"><span data-stu-id="d573e-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="d573e-104">Alcune cause possibili di questo errore sono:</span><span class="sxs-lookup"><span data-stu-id="d573e-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="d573e-105">Errore di ortografia il nome della routine.</span><span class="sxs-lookup"><span data-stu-id="d573e-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="d573e-106">Tentativo di chiamare una routine da un altro progetto senza aggiungere in modo esplicito un riferimento a tale progetto nel **riferimenti** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d573e-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="d573e-107">Specifica una routine che non è visibile alla routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="d573e-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="d573e-108">Dichiarazione di una routine di libreria a collegamento dinamico (DLL) di Windows o di una routine di risorsa di codice Macintosh che non si trova la risorsa di libreria o di codice specificata.</span><span class="sxs-lookup"><span data-stu-id="d573e-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d573e-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d573e-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="d573e-110">Assicurarsi che il nome della routine sia digitato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d573e-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2.  <span data-ttu-id="d573e-111">Individuare il nome del progetto contenente la routine da chiamare **riferimenti** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d573e-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="d573e-112">Se non viene visualizzato, fare clic su di **Sfoglia** pulsante per eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d573e-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="d573e-113">Selezionare la casella di controllo a sinistra del nome del progetto e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d573e-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d573e-114">Controllare il nome della routine.</span><span class="sxs-lookup"><span data-stu-id="d573e-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d573e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d573e-115">See Also</span></span>  
 <span data-ttu-id="d573e-116">[Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md) </span><span class="sxs-lookup"><span data-stu-id="d573e-116">[Error Types](../../../visual-basic/programming-guide/language-features/error-types.md) </span></span>  
<span data-ttu-id="d573e-117"> [Gestione dei riferimenti in un progetto](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="d573e-117"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="d573e-118"> [Sub (istruzione)](../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d573e-118"> [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="d573e-119"> [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)</span><span class="sxs-lookup"><span data-stu-id="d573e-119"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)</span></span>
