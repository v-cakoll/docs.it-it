---
title: Impossibile connettere l'applicazione a istanza singola con l'istanza originale
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
ms.openlocfilehash: 04ceec4839d07ba959c39af8c4f582c7abfe7d6b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198135"
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a><span data-ttu-id="2f23b-102">Impossibile connettere l'applicazione a istanza singola con l'istanza originale</span><span class="sxs-lookup"><span data-stu-id="2f23b-102">This single-instance application could not connect to the original instance</span></span>
<span data-ttu-id="2f23b-103">Impossibile connettere l'applicazione a istanza singola con l'istanza originale.</span><span class="sxs-lookup"><span data-stu-id="2f23b-103">This single-instance application could not connect to the original instance.</span></span> <span data-ttu-id="2f23b-104">Alcune possibili cause di questo problema sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f23b-104">Some of the possible causes for this problem are as follows:</span></span>  
  
- <span data-ttu-id="2f23b-105">L'istanza originale attualmente non risponde.</span><span class="sxs-lookup"><span data-stu-id="2f23b-105">The original instance stopped responding.</span></span>  
  
- <span data-ttu-id="2f23b-106">L'applicazione non dispone di autorizzazioni per la creazione di oggetti del kernel.</span><span class="sxs-lookup"><span data-stu-id="2f23b-106">The application does not have permissions to create kernel objects.</span></span> <span data-ttu-id="2f23b-107">Per ulteriori informazioni sugli oggetti kernel, vedere [mutex](../../standard/threading/mutexes.md).</span><span class="sxs-lookup"><span data-stu-id="2f23b-107">For more information about kernel objects, see [Mutexes](../../standard/threading/mutexes.md).</span></span>  
  
     <span data-ttu-id="2f23b-108">Il nome base degli oggetti del kernel deriva dalla concatenazione del GUID dell'assembly, del numero di versione principale e del numero di versione secondario.</span><span class="sxs-lookup"><span data-stu-id="2f23b-108">The base name for the kernel objects comes from concatenating the assembly's GUID, major version number, and minor version number.</span></span> <span data-ttu-id="2f23b-109">Il nome base ad esempio potrebbe essere `3639f15d-9547-43da-8145-60da347829915.1`.</span><span class="sxs-lookup"><span data-stu-id="2f23b-109">For example, the base name could be `3639f15d-9547-43da-8145-60da347829915.1`.</span></span>  
  
## <a name="to-correct-this-error-when-developing-the-application"></a><span data-ttu-id="2f23b-110">Per correggere questo errore quando si sviluppa l'applicazione</span><span class="sxs-lookup"><span data-stu-id="2f23b-110">To correct this error when developing the application</span></span>  
  
1. <span data-ttu-id="2f23b-111">Verificare che l'applicazione non passi allo stato di non reattività.</span><span class="sxs-lookup"><span data-stu-id="2f23b-111">Check that the application does not go into an unresponsive state.</span></span>  
  
2. <span data-ttu-id="2f23b-112">Verificare che l'applicazione abbia autorizzazioni sufficienti per creare oggetti kernel.</span><span class="sxs-lookup"><span data-stu-id="2f23b-112">Check that the application has sufficient permissions to create kernel objects.</span></span>  
  
3. <span data-ttu-id="2f23b-113">Riavviare l'istanza originale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2f23b-113">Restart the original instance of the application.</span></span>  
  
4. <span data-ttu-id="2f23b-114">Riavviare il computer per cancellare i processi che stanno usando la risorsa necessaria per la connessione all'istanza originale.</span><span class="sxs-lookup"><span data-stu-id="2f23b-114">Restart the computer to clear any process that may be using the resource that is required to connect to the original instance application.</span></span>  
  
5. <span data-ttu-id="2f23b-115">Prendere nota delle circostanze in cui si è verificato l'errore e chiamare il Servizio supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2f23b-115">Note the circumstances under which the error occurred, and telephone Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f23b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f23b-116">See also</span></span>

- <span data-ttu-id="2f23b-117">[Debugger Basics](/visualstudio/debugger/debugger-feature-tour) (Nozioni di base sul debugger)</span><span class="sxs-lookup"><span data-stu-id="2f23b-117">[Debugger Basics](/visualstudio/debugger/debugger-feature-tour)</span></span>
