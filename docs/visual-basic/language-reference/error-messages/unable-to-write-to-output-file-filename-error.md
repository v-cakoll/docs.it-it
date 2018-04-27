---
title: 'Impossibile scrivere nel file di output &#39; &lt;filename&gt;&#39;: &lt;errore&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a183f81a73c3c8034d9ba7366be8b36d425263da
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="unable-to-write-to-output-file-39ltfilenamegt39-lterrorgt"></a><span data-ttu-id="a7d39-102">Impossibile scrivere nel file di output &#39; &lt;filename&gt;&#39;: &lt;errore&gt;</span><span class="sxs-lookup"><span data-stu-id="a7d39-102">Unable to write to output file &#39;&lt;filename&gt;&#39;: &lt;error&gt;</span></span>
<span data-ttu-id="a7d39-103">Si è verificato un problema durante la creazione del file.</span><span class="sxs-lookup"><span data-stu-id="a7d39-103">There was a problem creating the file.</span></span>  
  
 <span data-ttu-id="a7d39-104">Non è possibile aprire un file di output per la scrittura.</span><span class="sxs-lookup"><span data-stu-id="a7d39-104">An output file cannot be opened for writing.</span></span> <span data-ttu-id="a7d39-105">È possibile che il file (o la cartella contenente il file) sia aperto per l'uso esclusivo da parte di un altro processo o è stato impostato l'attributo di sola lettura del file.</span><span class="sxs-lookup"><span data-stu-id="a7d39-105">The file (or the folder containing the file) may be opened for exclusive use by another process, or it may have its read-only attribute set.</span></span>  
  
 <span data-ttu-id="a7d39-106">Di seguito sono elencate alcune situazioni comuni in cui un file è aperto in modo esclusivo:</span><span class="sxs-lookup"><span data-stu-id="a7d39-106">Common situations where a file is opened exclusively are:</span></span>  
  
-   <span data-ttu-id="a7d39-107">L'applicazione è già in esecuzione e sta usando i file correlati.</span><span class="sxs-lookup"><span data-stu-id="a7d39-107">The application is already running and using its files.</span></span> <span data-ttu-id="a7d39-108">Per risolvere il problema, assicurarsi che l'applicazione non sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a7d39-108">To solve this problem, make sure that the application is not running.</span></span>  
  
-   <span data-ttu-id="a7d39-109">Un'altra applicazione ha aperto il file.</span><span class="sxs-lookup"><span data-stu-id="a7d39-109">Another application has opened the file.</span></span> <span data-ttu-id="a7d39-110">Per risolvere il problema, assicurarsi che altre applicazioni non accedano ai file.</span><span class="sxs-lookup"><span data-stu-id="a7d39-110">To solve this problem, make sure that no other application is accessing the files.</span></span> <span data-ttu-id="a7d39-111">Non è sempre semplice capire quale applicazione sta accedendo ai file. In questo caso, riavviare il computer potrebbe rappresentare il modo più semplice per arrestare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7d39-111">It is not always obvious which application is accessing your files; in that case, restarting the computer might be the easiest way to terminate the application.</span></span>  
  
 <span data-ttu-id="a7d39-112">Se anche uno solo dei file di output del progetto è contrassegnato come di sola lettura, sarà generata questa eccezione.</span><span class="sxs-lookup"><span data-stu-id="a7d39-112">If even one of the project output files is marked as read-only, this exception will be thrown.</span></span>  
  
 <span data-ttu-id="a7d39-113">**ID errore:** BC31019</span><span class="sxs-lookup"><span data-stu-id="a7d39-113">**Error ID:** BC31019</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a7d39-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a7d39-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="a7d39-115">Ripetere la compilazione del programma, per controllare se l'errore si verifica di nuovo.</span><span class="sxs-lookup"><span data-stu-id="a7d39-115">Compile the program again to see if the error recurs.</span></span>  
  
2.  <span data-ttu-id="a7d39-116">Se l'errore si ripresenta, salvare il lavoro e riavviare [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7d39-116">If the error continues, save your work and restart [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>  
  
3.  <span data-ttu-id="a7d39-117">Se l'errore si ripresenta, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="a7d39-117">If the error continues, restart the computer.</span></span>  
  
4.  <span data-ttu-id="a7d39-118">Se l'errore si ripete, reinstallare Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a7d39-118">If the error recurs, reinstall Visual Basic.</span></span>  
  
5.  <span data-ttu-id="a7d39-119">Se l'errore persiste dopo la reinstallazione, inviare una notifica al Servizio supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7d39-119">If the error persists after reinstallation, notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-check-file-attributes-in-file-explorer"></a><span data-ttu-id="a7d39-120">Per controllare gli attributi di file in Esplora file</span><span class="sxs-lookup"><span data-stu-id="a7d39-120">To check file attributes in File Explorer</span></span>  
  
1.  <span data-ttu-id="a7d39-121">Aprire la cartella a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="a7d39-121">Open the folder you are interested in.</span></span>  
  
2.  <span data-ttu-id="a7d39-122">Fare clic su di **viste** icona e scegliere **dettagli**.</span><span class="sxs-lookup"><span data-stu-id="a7d39-122">Click the **Views** icon and choose **Details**.</span></span>  
  
3.  <span data-ttu-id="a7d39-123">Fare doppio clic sull'intestazione di colonna e scegliere **attributi** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="a7d39-123">Right-click the column header, and choose **Attributes** from the drop-down list.</span></span>  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a><span data-ttu-id="a7d39-124">Per modificare gli attributi di un file o una cartella</span><span class="sxs-lookup"><span data-stu-id="a7d39-124">To change the attributes of a file or folder</span></span>  
  
1.  <span data-ttu-id="a7d39-125">In **Esplora File**, fare doppio clic su file o della cartella e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a7d39-125">In **File Explorer**, right-click the file or folder and choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="a7d39-126">Nel **attributi** sezione del **generale** scheda, deseleziona il **Read-only** casella.</span><span class="sxs-lookup"><span data-stu-id="a7d39-126">In the **Attributes** section of the **General** tab, clear the **Read-only** box.</span></span>  
  
3.  <span data-ttu-id="a7d39-127">Press **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7d39-127">Press **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7d39-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7d39-128">See Also</span></span>  
 <span data-ttu-id="a7d39-129">[Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)</span><span class="sxs-lookup"><span data-stu-id="a7d39-129">[Talk to Us](/visualstudio/ide/talk-to-us)</span></span>
