---
title: "Si è verificato un errore imprevisto perché non è possibile acquisire una risorsa del sistema operativo necessaria per l&quot;avvio singola istanza | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
dev_langs:
- VB
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
caps.latest.revision: 10
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
ms.openlocfilehash: 03ab2d1c746fbc28c0c6f3e59371cc6bbd4050cd
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="23971-102">Errore imprevisto. Impossibile acquisire una risorsa del sistema operativo necessaria per l'avvio di istanze singole</span><span class="sxs-lookup"><span data-stu-id="23971-102">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>
<span data-ttu-id="23971-103">L'applicazione non è riuscita ad acquisire una risorsa del sistema operativo necessaria.</span><span class="sxs-lookup"><span data-stu-id="23971-103">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="23971-104">Alcune possibili cause di questo problema sono:</span><span class="sxs-lookup"><span data-stu-id="23971-104">Some of the possible causes for this problem are:</span></span>  
  
-   <span data-ttu-id="23971-105">L'applicazione non dispone di autorizzazioni per la creazione di oggetti del sistema operativo denominati.</span><span class="sxs-lookup"><span data-stu-id="23971-105">The application does not have permissions to create named operating-system objects.</span></span>  
  
-   <span data-ttu-id="23971-106">Common Language Runtime non dispone di autorizzazioni per la creazione di file mappati alla memoria.</span><span class="sxs-lookup"><span data-stu-id="23971-106">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
-   <span data-ttu-id="23971-107">L'applicazione deve accedere a un oggetto del sistema operativo, ma un altro processo lo sta usando.</span><span class="sxs-lookup"><span data-stu-id="23971-107">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="23971-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="23971-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="23971-109">Verificare che l'applicazione disponga di autorizzazioni sufficienti per la creazione di oggetti del sistema operativo denominati.</span><span class="sxs-lookup"><span data-stu-id="23971-109">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2.  <span data-ttu-id="23971-110">Verificare che Common Language Runtime disponga di autorizzazioni sufficienti per la creazione di file mappati alla memoria.</span><span class="sxs-lookup"><span data-stu-id="23971-110">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3.  <span data-ttu-id="23971-111">Riavviare il computer per cancellare i processi che stanno usando la risorsa necessaria per la connessione all'istanza originale.</span><span class="sxs-lookup"><span data-stu-id="23971-111">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4.  <span data-ttu-id="23971-112">Prendere nota delle circostanze in cui si è verificato l'errore e contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="23971-112">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23971-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23971-113">See Also</span></span>  
 <span data-ttu-id="23971-114">[Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)  (Pagina Applicazione, Creazione progetti (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="23971-114">[Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="23971-115"> [Nozioni di base del debugger](https://docs.microsoft.com/visualstudio/debugger/debugger-basics) </span><span class="sxs-lookup"><span data-stu-id="23971-115"> [Debugger Basics](https://docs.microsoft.com/visualstudio/debugger/debugger-basics) </span></span>  
<span data-ttu-id="23971-116"> [Comunicazioni con Microsoft](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="23971-116"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>
