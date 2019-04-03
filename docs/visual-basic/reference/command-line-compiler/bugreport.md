---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: e7b4ebc58b6fe9850b92ef945cb0d715e4369efe
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820911"
---
# <a name="-bugreport"></a><span data-ttu-id="0a89d-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="0a89d-102">-bugreport</span></span>
<span data-ttu-id="0a89d-103">Crea un file che è possibile usare quando si elabora un report sui bug.</span><span class="sxs-lookup"><span data-stu-id="0a89d-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a89d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a89d-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="0a89d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0a89d-105">Arguments</span></span>  
  
|<span data-ttu-id="0a89d-106">Termine</span><span class="sxs-lookup"><span data-stu-id="0a89d-106">Term</span></span>|<span data-ttu-id="0a89d-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="0a89d-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="0a89d-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0a89d-108">Required.</span></span> <span data-ttu-id="0a89d-109">Il nome del file che conterrà il report sui bug.</span><span class="sxs-lookup"><span data-stu-id="0a89d-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="0a89d-110">Racchiudere il nome file racchiuso tra virgolette ("") se il nome contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="0a89d-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a89d-111">Note</span><span class="sxs-lookup"><span data-stu-id="0a89d-111">Remarks</span></span>  
 <span data-ttu-id="0a89d-112">Le informazioni seguenti vengono aggiunte a `file`:</span><span class="sxs-lookup"><span data-stu-id="0a89d-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="0a89d-113">Una copia di tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="0a89d-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="0a89d-114">Un elenco delle opzioni del compilatore usata nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="0a89d-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="0a89d-115">Informazioni sulla versione su compilatore, common language runtime e del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0a89d-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="0a89d-116">L'eventuale output del compilatore.</span><span class="sxs-lookup"><span data-stu-id="0a89d-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="0a89d-117">Descrizione del problema per cui viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="0a89d-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="0a89d-118">Una descrizione del modo in cui si può risolvere il problema dovrebbe essere risolto, per cui viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="0a89d-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="0a89d-119">Poiché una copia di tutti i file di codice sorgente è incluso `file`, è possibile riprodurre l'errore del codice (sospetti) nel programma più breve possibile.</span><span class="sxs-lookup"><span data-stu-id="0a89d-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0a89d-120">Il `-bugreport` opzione produce un file che contiene informazioni potenzialmente riservate.</span><span class="sxs-lookup"><span data-stu-id="0a89d-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="0a89d-121">Ciò include l'ora corrente, la versione del compilatore, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] versione, versione del sistema operativo, nome utente, gli argomenti della riga di comando con cui il compilatore è stato eseguito, tutto il codice sorgente e il formato binario di qualsiasi assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="0a89d-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="0a89d-122">Questa opzione è possibile accedere specificando le opzioni della riga di comando nel file Web. config per una compilazione lato server di un [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0a89d-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="0a89d-123">Per evitare questo problema, modificare il file Machine. config per impedire agli utenti di compilazione sul server.</span><span class="sxs-lookup"><span data-stu-id="0a89d-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="0a89d-124">Se questa opzione viene usata con `-errorreport:prompt`, `-errorreport:queue`, o `-errorreport:send`, e l'applicazione rileva un errore interno del compilatore, le informazioni contenute in `file` verranno inviate a Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="0a89d-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="0a89d-125">Tali informazioni consentono i tecnici Microsoft di identificare la causa dell'errore e potrebbero contribuire a migliorare la prossima versione di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0a89d-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="0a89d-126">Per impostazione predefinita, nessuna informazione viene inviata a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0a89d-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="0a89d-127">Tuttavia, quando si compila un'applicazione usando `-errorreport:queue`, che è abilitato per impostazione predefinita, l'applicazione raccoglie le segnalazioni degli errori.</span><span class="sxs-lookup"><span data-stu-id="0a89d-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="0a89d-128">Quindi, quando l'amministratore del computer si connette, il sistema di segnalazione errori consente di visualizzare una finestra popup che consente all'amministratore di inoltrare a Microsoft i report degli errori che si sono verificati dopo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="0a89d-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a89d-129">Il `/bugreport` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo quando esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0a89d-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a89d-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a89d-130">Example</span></span>  
 <span data-ttu-id="0a89d-131">L'esempio seguente viene compilato `T2.vb` e tutte le informazioni di segnalazione di errori nel file `Problem.txt`.</span><span class="sxs-lookup"><span data-stu-id="0a89d-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a89d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a89d-132">See also</span></span>

- [<span data-ttu-id="0a89d-133">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0a89d-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="0a89d-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a89d-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="0a89d-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="0a89d-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [<span data-ttu-id="0a89d-136">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="0a89d-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="0a89d-137">[Elemento trustLevel per securityPolicy (Schema delle impostazioni ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0a89d-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
