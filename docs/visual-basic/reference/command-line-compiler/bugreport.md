---
title: /bugreport | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: 22
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
ms.openlocfilehash: b959ef7958cffbbb31f3907eaf8749ca93ac538d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="bugreport"></a><span data-ttu-id="8b76b-102">/bugreport</span><span class="sxs-lookup"><span data-stu-id="8b76b-102">/bugreport</span></span>
<span data-ttu-id="8b76b-103">Crea un file che è possibile utilizzare quando si invia una segnalazione di bug.</span><span class="sxs-lookup"><span data-stu-id="8b76b-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b76b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b76b-104">Syntax</span></span>  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="8b76b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8b76b-105">Arguments</span></span>  
  
|<span data-ttu-id="8b76b-106">Termine</span><span class="sxs-lookup"><span data-stu-id="8b76b-106">Term</span></span>|<span data-ttu-id="8b76b-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="8b76b-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="8b76b-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8b76b-108">Required.</span></span> <span data-ttu-id="8b76b-109">Il nome del file che conterrà il report sui bug.</span><span class="sxs-lookup"><span data-stu-id="8b76b-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="8b76b-110">Racchiudere il nome del file tra virgolette ("") se il nome contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="8b76b-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b76b-111">Note</span><span class="sxs-lookup"><span data-stu-id="8b76b-111">Remarks</span></span>  
 <span data-ttu-id="8b76b-112">Le informazioni seguenti vengono aggiunte a `file`:</span><span class="sxs-lookup"><span data-stu-id="8b76b-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="8b76b-113">Una copia di tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="8b76b-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="8b76b-114">Un elenco di opzioni del compilatore utilizzate nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="8b76b-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="8b76b-115">Informazioni sulla versione su cui il compilatore, common language runtime e del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8b76b-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="8b76b-116">Compilatore di output, se presente.</span><span class="sxs-lookup"><span data-stu-id="8b76b-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="8b76b-117">Descrizione del problema, per cui viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="8b76b-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="8b76b-118">Una descrizione di come si ritiene che il problema deve essere corretto per il quale viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="8b76b-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="8b76b-119">Poiché una copia di tutti i file di codice sorgente è incluso `file`, è possibile riprodurre l'errore del codice (sospetta) nel programma più breve.</span><span class="sxs-lookup"><span data-stu-id="8b76b-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b76b-120">Il `/bugreport` opzione produce un file che contiene informazioni potenzialmente riservate.</span><span class="sxs-lookup"><span data-stu-id="8b76b-120">The `/bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="8b76b-121">Ora corrente, versione del compilatore, [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] versione, versione del sistema operativo, nome utente, gli argomenti della riga di comando con cui il compilatore è stato eseguito, tutto il codice sorgente e il formato binario di qualsiasi assembly a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="8b76b-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="8b76b-122">Questa opzione è possibile accedere specificando le opzioni della riga di comando nel file Web. config per una compilazione sul lato server di un [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8b76b-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] application.</span></span> <span data-ttu-id="8b76b-123">Per evitare questo problema, modificare il file Machine. config per impedire agli utenti di compilazione sul server.</span><span class="sxs-lookup"><span data-stu-id="8b76b-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="8b76b-124">Se questa opzione viene utilizzata con `/errorreport:prompt`, `/errorreport:queue`, o `/errorreport:send`, e l'applicazione rileva un errore interno del compilatore, le informazioni contenute in `file` viene inviato a Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="8b76b-124">If this option is used with `/errorreport:prompt`, `/errorreport:queue`, or `/errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="8b76b-125">Tali informazioni consentirà tecnici Microsoft di identificare la causa dell'errore e di migliorare la prossima versione di [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b76b-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="8b76b-126">Per impostazione predefinita, viene inviata alcuna informazione a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8b76b-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="8b76b-127">Tuttavia, quando si compila un'applicazione utilizzando `/errorreport:queue`, che è attivata per impostazione predefinita, l'applicazione recupera i report degli errori.</span><span class="sxs-lookup"><span data-stu-id="8b76b-127">However, when you compile an application by using `/errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="8b76b-128">Quindi, quando l'amministratore del computer accede, il sistema di segnalazione errori visualizza una finestra popup che consente all'amministratore di inoltrare a Microsoft i report degli errori che si sono verificati dopo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8b76b-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b76b-129">Il `/bugreport` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo quando si compila dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="8b76b-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b76b-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="8b76b-130">Example</span></span>  
 <span data-ttu-id="8b76b-131">Nell'esempio seguente viene compilato `T2.vb` e tutte le informazioni di segnalazione dei bug nel file `Problem.txt`.</span><span class="sxs-lookup"><span data-stu-id="8b76b-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b76b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b76b-132">See Also</span></span>  
 <span data-ttu-id="8b76b-133">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="8b76b-133">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="8b76b-134"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span><span class="sxs-lookup"><span data-stu-id="8b76b-134"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span></span>  
<span data-ttu-id="8b76b-135"> [/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md) </span><span class="sxs-lookup"><span data-stu-id="8b76b-135"> [/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md) </span></span>  
<span data-ttu-id="8b76b-136"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="8b76b-136"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="8b76b-137"> [Elemento trustLevel per securityPolicy (Schema delle impostazioni ASP.NET)](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)</span><span class="sxs-lookup"><span data-stu-id="8b76b-137"> [trustLevel Element for securityPolicy (ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)</span></span>
