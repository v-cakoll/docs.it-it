---
title: /errorreport
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0abe276aaacdeb175c3af7067dffa81448450e22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="errorreport"></a><span data-ttu-id="c9a7a-102">/errorreport</span><span class="sxs-lookup"><span data-stu-id="c9a7a-102">/errorreport</span></span>
<span data-ttu-id="c9a7a-103">Specifica la modalità di segnalazione degli errori interni del compilatore [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9a7a-103">Specifies how the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler should report internal compiler errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9a7a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9a7a-104">Syntax</span></span>  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a><span data-ttu-id="c9a7a-105">Note</span><span class="sxs-lookup"><span data-stu-id="c9a7a-105">Remarks</span></span>  
 <span data-ttu-id="c9a7a-106">Questa opzione offre un modo pratico per segnalare un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] interni del compilatore sugli errori per il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] al team di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-106">This option provides a convenient way to report a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] internal compiler error (ICE) to the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] team at Microsoft.</span></span> <span data-ttu-id="c9a7a-107">Per impostazione predefinita, il compilatore non invia alcuna informazione a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="c9a7a-108">Tuttavia, se si verifica un errore interno del compilatore, questa opzione consente di segnalare l'errore a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="c9a7a-109">Tali informazioni consentiranno tecnici Microsoft di identificare la causa e potrebbe contribuire a migliorare la versione successiva di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9a7a-109">That information will help Microsoft engineers identify the cause and may help improve the next release of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="c9a7a-110">Possibilità la di inviare report dipende dalle autorizzazioni di criteri computer e utente.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>  
  
 <span data-ttu-id="c9a7a-111">Nella tabella seguente sono riepilogati gli effetti del `/errorreport` opzione.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-111">The following table summarizes the effect of the `/errorreport` option.</span></span>  
  
|<span data-ttu-id="c9a7a-112">Opzione</span><span class="sxs-lookup"><span data-stu-id="c9a7a-112">Option</span></span>|<span data-ttu-id="c9a7a-113">Comportamento</span><span class="sxs-lookup"><span data-stu-id="c9a7a-113">Behavior</span></span>|  
|---|---|  
|`prompt`|<span data-ttu-id="c9a7a-114">Se si verifica un errore interno del compilatore, una finestra di dialogo viene visualizzata in modo che è possibile visualizzare esattamente i dati raccolti dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="c9a7a-115">È possibile determinare se sono presenti eventuali informazioni sensibili nella segnalazione errori e decidere se inviarlo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="c9a7a-116">Se si decide di inviarlo, e le impostazioni dei criteri computer e l'utente lo consentono, il compilatore invierà i dati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|  
|`queue`|<span data-ttu-id="c9a7a-117">Accoda la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-117">Queues the error report.</span></span> <span data-ttu-id="c9a7a-118">Quando si accede con privilegi di amministratore, è possibile segnalare gli eventuali errori dall'ultima volta in cui è stato effettuato (non verrà richiesto di inviare segnalazioni errori più di una volta ogni tre giorni).</span><span class="sxs-lookup"><span data-stu-id="c9a7a-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="c9a7a-119">Si tratta del comportamento predefinito quando il `/errorreport` opzione non è specificata.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-119">This is the default behavior when the `/errorreport` option is not specified.</span></span>|  
|`send`|<span data-ttu-id="c9a7a-120">Se si verifica un errore interno del compilatore e le impostazioni di criteri computer e l'utente lo consentono, il compilatore invia i dati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="c9a7a-121">L'opzione `/errorReport:send` tenta di inviare automaticamente a Microsoft informazioni di errore.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-121">The option `/errorReport:send` attempts to automatically send error information to Microsoft.</span></span> <span data-ttu-id="c9a7a-122">Questa opzione varia a seconda del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-122">This option depends on the registry.</span></span> <span data-ttu-id="c9a7a-123">Per ulteriori informazioni sull'impostazione dei valori appropriati nel Registro di sistema, vedere [come attivare la segnalazione errori automatica in strumenti da riga di comando di Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695).</span><span class="sxs-lookup"><span data-stu-id="c9a7a-123">For more information about setting the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695).</span></span>|  
|`none`|<span data-ttu-id="c9a7a-124">Se si verifica un errore interno del compilatore, non verrà essere raccolti né inviato a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-124">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|  
  
 <span data-ttu-id="c9a7a-125">Il compilatore invia i dati che includono lo stack al momento dell'errore, che in genere include codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-125">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="c9a7a-126">Se `/errorreport` viene utilizzato con il [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opzione, viene inviato l'intero file di origine.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-126">If `/errorreport` is used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>  
  
 <span data-ttu-id="c9a7a-127">Questa opzione risulta particolarmente utile con il [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opzione ammette tecnici di Microsoft più facilmente riprodurre l'errore.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-127">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9a7a-128">Il `/errorreport` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-128">The `/errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9a7a-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="c9a7a-129">Example</span></span>  
 <span data-ttu-id="c9a7a-130">Il codice seguente si tenterà di compilare `T2.vb`, e se il compilatore rileva un errore interno del compilatore, viene richiesto di inviare una segnalazione a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9a7a-130">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9a7a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9a7a-131">See Also</span></span>  
 [<span data-ttu-id="c9a7a-132">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9a7a-132">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c9a7a-133">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="c9a7a-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="c9a7a-134">/bugreport</span><span class="sxs-lookup"><span data-stu-id="c9a7a-134">/bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
