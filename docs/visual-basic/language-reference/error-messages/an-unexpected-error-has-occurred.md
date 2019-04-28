---
title: Errore imprevisto. Impossibile acquisire una risorsa del sistema operativo necessaria per l'avvio di istanze singole
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
ms.openlocfilehash: 9aa7ba0babe0a89942e320a76e07c05162b31700
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61751618"
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="ce1d3-102">Errore imprevisto. Impossibile acquisire una risorsa del sistema operativo necessaria per l'avvio di istanze singole</span><span class="sxs-lookup"><span data-stu-id="ce1d3-102">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>
<span data-ttu-id="ce1d3-103">L'applicazione non è riuscita ad acquisire una risorsa del sistema operativo necessaria.</span><span class="sxs-lookup"><span data-stu-id="ce1d3-103">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="ce1d3-104">Alcune possibili cause di questo problema sono:</span><span class="sxs-lookup"><span data-stu-id="ce1d3-104">Some of the possible causes for this problem are:</span></span>  
  
- <span data-ttu-id="ce1d3-105">L'applicazione non dispone di autorizzazioni per la creazione di oggetti del sistema operativo denominati.</span><span class="sxs-lookup"><span data-stu-id="ce1d3-105">The application does not have permissions to create named operating-system objects.</span></span>  
  
- <span data-ttu-id="ce1d3-106">Common Language Runtime non dispone di autorizzazioni per la creazione di file mappati alla memoria.</span><span class="sxs-lookup"><span data-stu-id="ce1d3-106">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
- <span data-ttu-id="ce1d3-107">L'applicazione deve accedere a un oggetto del sistema operativo, ma un altro processo lo sta usando.</span><span class="sxs-lookup"><span data-stu-id="ce1d3-107">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ce1d3-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ce1d3-108">To correct this error</span></span>  
  
1. <span data-ttu-id="ce1d3-109">Verificare che l'applicazione disponga di autorizzazioni sufficienti per la creazione di oggetti del sistema operativo denominati.</span><span class="sxs-lookup"><span data-stu-id="ce1d3-109">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2. <span data-ttu-id="ce1d3-110">Verificare che Common Language Runtime disponga di autorizzazioni sufficienti per la creazione di file mappati alla memoria.</span><span class="sxs-lookup"><span data-stu-id="ce1d3-110">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3. <span data-ttu-id="ce1d3-111">Riavviare il computer per cancellare i processi che stanno usando la risorsa necessaria per la connessione all'istanza originale.</span><span class="sxs-lookup"><span data-stu-id="ce1d3-111">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4. <span data-ttu-id="ce1d3-112">Prendere nota delle circostanze in cui si è verificato l'errore e contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ce1d3-112">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce1d3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce1d3-113">See also</span></span>

- [<span data-ttu-id="ce1d3-114">Pagina Applicazione, Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce1d3-114">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- <span data-ttu-id="ce1d3-115">[Debugger Basics](/visualstudio/debugger/debugger-basics) (Nozioni di base sul debugger)</span><span class="sxs-lookup"><span data-stu-id="ce1d3-115">[Debugger Basics](/visualstudio/debugger/debugger-basics)</span></span>
- <span data-ttu-id="ce1d3-116">[Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)</span><span class="sxs-lookup"><span data-stu-id="ce1d3-116">[Talk to Us](/visualstudio/ide/talk-to-us)</span></span>
