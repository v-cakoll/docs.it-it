---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 75c3e5842447a8f0812d5a90d7157f7a6a496936
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962441"
---
# <a name="-bugreport"></a><span data-ttu-id="6e1a6-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="6e1a6-102">-bugreport</span></span>
<span data-ttu-id="6e1a6-103">Consente di creare un file che è possibile utilizzare per il file di un report sui bug.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e1a6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e1a6-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="6e1a6-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6e1a6-105">Arguments</span></span>  
  
|<span data-ttu-id="6e1a6-106">Termine</span><span class="sxs-lookup"><span data-stu-id="6e1a6-106">Term</span></span>|<span data-ttu-id="6e1a6-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="6e1a6-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="6e1a6-108">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-108">Required.</span></span> <span data-ttu-id="6e1a6-109">Nome del file che conterrà il report sui bug.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="6e1a6-110">Racchiudere il nome file tra virgolette ("") se il nome contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e1a6-111">Note</span><span class="sxs-lookup"><span data-stu-id="6e1a6-111">Remarks</span></span>  
 <span data-ttu-id="6e1a6-112">Vengono aggiunte le informazioni seguenti a `file`:</span><span class="sxs-lookup"><span data-stu-id="6e1a6-112">The following information is added to `file`:</span></span>  
  
- <span data-ttu-id="6e1a6-113">Copia di tutti i file del codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-113">A copy of all source-code files in the compilation.</span></span>  
  
- <span data-ttu-id="6e1a6-114">Elenco delle opzioni del compilatore utilizzate nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-114">A list of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="6e1a6-115">Informazioni sulla versione del compilatore, della Common Language Runtime e del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
- <span data-ttu-id="6e1a6-116">L'eventuale output del compilatore.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-116">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="6e1a6-117">Una descrizione del problema, per cui viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-117">A description of the problem, for which you are prompted.</span></span>  
  
- <span data-ttu-id="6e1a6-118">Una descrizione del modo in cui si ritiene che il problema venga risolto, per cui viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="6e1a6-119">Poiché una copia di tutti i file di codice sorgente è inclusa `file`in, potrebbe essere necessario riprodurre l'errore del codice (sospetto) nel programma più breve possibile.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6e1a6-120">L' `-bugreport` opzione produce un file che contiene informazioni potenzialmente riservate.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="6e1a6-121">Sono inclusi l'ora corrente, la versione del compilatore, la versione .NET Framework, la versione del sistema operativo, il nome utente, gli argomenti della riga di comando con cui è stato eseguito il compilatore, tutto il codice sorgente e il formato binario di qualsiasi assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="6e1a6-122">Per accedere a questa opzione, è possibile specificare le opzioni della riga di comando nel file Web. config per una compilazione lato server di un'applicazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="6e1a6-123">Per evitare questo problema, modificare il file Machine. config per non consentire agli utenti di eseguire la compilazione nel server.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="6e1a6-124">Se questa opzione viene utilizzata con `-errorreport:prompt`, `-errorreport:queue`o `-errorreport:send`e l'applicazione rileva un errore interno del compilatore, le informazioni contenute in `file` vengono inviate a Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="6e1a6-125">Tali informazioni consentiranno ai tecnici Microsoft di identificare la ragione dell'errore e contribuire a migliorare la prossima versione di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="6e1a6-126">Per impostazione predefinita, nessuna informazione viene inviata a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="6e1a6-127">Tuttavia, quando si compila un'applicazione utilizzando `-errorreport:queue`, che è abilitata per impostazione predefinita, l'applicazione raccoglie i report degli errori.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="6e1a6-128">Quindi, quando l'amministratore del computer accede, il sistema di segnalazione degli errori Visualizza una finestra popup che consente all'amministratore di trasmettere a Microsoft eventuali segnalazioni di errore che si sono verificate dopo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e1a6-129">L' `/bugreport` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6e1a6-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e1a6-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e1a6-130">Example</span></span>  
 <span data-ttu-id="6e1a6-131">Nell'esempio seguente vengono compilate `T2.vb` e inserite tutte le informazioni di segnalazione dei bug nel file. `Problem.txt`</span><span class="sxs-lookup"><span data-stu-id="6e1a6-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e1a6-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e1a6-132">See also</span></span>

- [<span data-ttu-id="6e1a6-133">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e1a6-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6e1a6-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e1a6-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="6e1a6-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="6e1a6-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [<span data-ttu-id="6e1a6-136">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="6e1a6-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="6e1a6-137">[Elemento trustLevel per securityPolicy (schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6e1a6-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
