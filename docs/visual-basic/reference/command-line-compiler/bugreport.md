---
title: -bugreport
ms.date: 03/08/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 766a4252fd77be95e2641239cba53a4d90e0cb1d
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-bugreport"></a><span data-ttu-id="d6f68-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="d6f68-102">-bugreport</span></span>
<span data-ttu-id="d6f68-103">Crea un file che è possibile utilizzare quando si invia una segnalazione bug.</span><span class="sxs-lookup"><span data-stu-id="d6f68-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6f68-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6f68-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d6f68-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d6f68-105">Arguments</span></span>  
  
|<span data-ttu-id="d6f68-106">Termine</span><span class="sxs-lookup"><span data-stu-id="d6f68-106">Term</span></span>|<span data-ttu-id="d6f68-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="d6f68-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="d6f68-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d6f68-108">Required.</span></span> <span data-ttu-id="d6f68-109">Il nome del file che conterrà il report sui bug.</span><span class="sxs-lookup"><span data-stu-id="d6f68-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="d6f68-110">Racchiudere il nome del file tra virgolette ("") se il nome contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="d6f68-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6f68-111">Note</span><span class="sxs-lookup"><span data-stu-id="d6f68-111">Remarks</span></span>  
 <span data-ttu-id="d6f68-112">Le informazioni seguenti vengono aggiunte a `file`:</span><span class="sxs-lookup"><span data-stu-id="d6f68-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="d6f68-113">Una copia di tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="d6f68-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="d6f68-114">Un elenco di opzioni del compilatore utilizzate nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="d6f68-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="d6f68-115">Informazioni sulla versione relative del compilatore, common language runtime e del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d6f68-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="d6f68-116">L'eventuale output del compilatore.</span><span class="sxs-lookup"><span data-stu-id="d6f68-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="d6f68-117">Descrizione del problema, per cui viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="d6f68-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="d6f68-118">Una descrizione di come si ritiene che il problema deve essere corretto per il quale viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="d6f68-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="d6f68-119">Poiché una copia di tutti i file di codice sorgente è incluso `file`, è possibile riprodurre l'errore del codice (sospetta) nel programma più breve possibile.</span><span class="sxs-lookup"><span data-stu-id="d6f68-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d6f68-120">Il `-bugreport` opzione produce un file che contiene informazioni potenzialmente riservate.</span><span class="sxs-lookup"><span data-stu-id="d6f68-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="d6f68-121">Ora corrente, la versione del compilatore, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] versione, versione del sistema operativo, nome utente, gli argomenti della riga di comando con cui è stato eseguito il compilatore, tutto il codice sorgente e il formato binario di qualsiasi assembly a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="d6f68-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="d6f68-122">Questa opzione è possibile accedere mediante le opzioni della riga di comando nel file Web. config per una compilazione sul lato server di un [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6f68-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="d6f68-123">Per evitare questo problema, modificare il file Machine. config per impedire agli utenti di compilazione sul server.</span><span class="sxs-lookup"><span data-stu-id="d6f68-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="d6f68-124">Se questa opzione viene utilizzata con `-errorreport:prompt`, `-errorreport:queue`, o `-errorreport:send`, e nell'applicazione viene rilevato un errore interno del compilatore, le informazioni contenute in `file` viene inviato a Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="d6f68-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="d6f68-125">Tali informazioni consentiranno tecnici Microsoft di identificare la causa dell'errore e potrebbe contribuire a migliorare la versione successiva di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6f68-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="d6f68-126">Per impostazione predefinita, nessuna informazione viene inviata a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6f68-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="d6f68-127">Tuttavia, quando si compila un'applicazione utilizzando `-errorreport:queue`, cui è abilitata per impostazione predefinita, l'applicazione recupera i report degli errori.</span><span class="sxs-lookup"><span data-stu-id="d6f68-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="d6f68-128">Quindi, quando l'amministratore del computer si connette, il sistema di segnalazione errori consente di visualizzare una finestra popup che consente all'amministratore di inoltrare a Microsoft i report degli errori che si sono verificati dopo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d6f68-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6f68-129">Il `/bugreport` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo quando esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d6f68-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6f68-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6f68-130">Example</span></span>  
 <span data-ttu-id="d6f68-131">Nell'esempio seguente viene compilata `T2.vb` e tutte le informazioni di segnalazione nel file `Problem.txt`.</span><span class="sxs-lookup"><span data-stu-id="d6f68-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6f68-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6f68-132">See Also</span></span>  
 [<span data-ttu-id="d6f68-133">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6f68-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d6f68-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6f68-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="d6f68-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="d6f68-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)  
 [<span data-ttu-id="d6f68-136">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="d6f68-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="d6f68-137">trustLevel elemento per securityPolicy (Schema delle impostazioni ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="d6f68-137">trustLevel Element for securityPolicy (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/library/729ab04c-03da-4ee5-86b1-be9d08a09369)
