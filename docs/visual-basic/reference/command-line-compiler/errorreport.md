---
title: /errorreport | Documenti di Microsoft
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
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c2f9a9daf6aed6348baeb2c4de2fe5caef70f52b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="errorreport"></a><span data-ttu-id="fd7e2-102">/errorreport</span><span class="sxs-lookup"><span data-stu-id="fd7e2-102">/errorreport</span></span>
<span data-ttu-id="fd7e2-103">Specifica la modalità di segnalazione degli errori interni del compilatore [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd7e2-103">Specifies how the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler should report internal compiler errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd7e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd7e2-104">Syntax</span></span>  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a><span data-ttu-id="fd7e2-105">Note</span><span class="sxs-lookup"><span data-stu-id="fd7e2-105">Remarks</span></span>  
 <span data-ttu-id="fd7e2-106">Questa opzione offre un modo pratico per segnalare un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] errore interno del compilatore (ICE) per il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] team di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-106">This option provides a convenient way to report a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] internal compiler error (ICE) to the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] team at Microsoft.</span></span> <span data-ttu-id="fd7e2-107">Per impostazione predefinita, il compilatore non invia alcuna informazione a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="fd7e2-108">Tuttavia, se si verifica un errore interno del compilatore, questa opzione consente di segnalare l'errore a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="fd7e2-109">Tali informazioni consentiranno tecnici Microsoft di identificare la causa e potrebbe contribuire a migliorare la prossima versione di [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd7e2-109">That information will help Microsoft engineers identify the cause and may help improve the next release of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="fd7e2-110">Capacità di un utente di inviare report dipende dalle autorizzazioni di criteri utente e computer.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>  
  
 <span data-ttu-id="fd7e2-111">Nella tabella seguente sono riepilogati gli effetti di `/errorreport` (opzione).</span><span class="sxs-lookup"><span data-stu-id="fd7e2-111">The following table summarizes the effect of the `/errorreport` option.</span></span>  
  
|<span data-ttu-id="fd7e2-112">Opzione</span><span class="sxs-lookup"><span data-stu-id="fd7e2-112">Option</span></span>|<span data-ttu-id="fd7e2-113">Comportamento</span><span class="sxs-lookup"><span data-stu-id="fd7e2-113">Behavior</span></span>|  
|---|---|  
|`prompt`|<span data-ttu-id="fd7e2-114">Se si verifica un errore interno del compilatore, una finestra di dialogo viene visualizzata in modo che sia possibile visualizzare i dati esatti raccolti dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="fd7e2-115">È possibile determinare se c'è informazioni riservate nella segnalazione errori e decidere se inviarlo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="fd7e2-116">Se si decide di inviarlo, e le impostazioni dei criteri computer e l'utente lo consentono, il compilatore invia i dati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|  
|`queue`|<span data-ttu-id="fd7e2-117">Accoda la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-117">Queues the error report.</span></span> <span data-ttu-id="fd7e2-118">Quando si accede con privilegi di amministratore, è possibile segnalare gli eventuali errori dall'ultima volta che si fosse connessi in (non verrà richiesto di inviare segnalazioni di errori più di una volta ogni tre giorni).</span><span class="sxs-lookup"><span data-stu-id="fd7e2-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="fd7e2-119">Questo è il comportamento predefinito quando il `/errorreport` opzione non è specificata.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-119">This is the default behavior when the `/errorreport` option is not specified.</span></span>|  
|`send`|<span data-ttu-id="fd7e2-120">Se si verifica un errore interno del compilatore e le impostazioni di criteri computer e l'utente lo consentono, il compilatore invia i dati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="fd7e2-121">L'opzione `/errorReport:send` tenta di inviare automaticamente informazioni sugli errori a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-121">The option `/errorReport:send` attempts to automatically send error information to Microsoft.</span></span> <span data-ttu-id="fd7e2-122">Questa opzione varia a seconda del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-122">This option depends on the registry.</span></span> <span data-ttu-id="fd7e2-123">Per ulteriori informazioni sull'impostazione i valori appropriati nel Registro di sistema, vedere [come attivare la segnalazione degli errori automatica negli strumenti della riga di comando di Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695).</span><span class="sxs-lookup"><span data-stu-id="fd7e2-123">For more information about setting the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695).</span></span>|  
|`none`|<span data-ttu-id="fd7e2-124">Se si verifica un errore interno del compilatore, non verrà essere raccolti né inviato a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-124">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|  
  
 <span data-ttu-id="fd7e2-125">Il compilatore invia i dati che includono lo stack al momento dell'errore, che in genere include codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-125">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="fd7e2-126">Se `/errorreport` viene utilizzato con il [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opzione, viene inviato l'intero file di origine.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-126">If `/errorreport` is used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>  
  
 <span data-ttu-id="fd7e2-127">Questa opzione risulta particolarmente utile con il [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opzione perché consente tecnici Microsoft più facilmente riprodurre l'errore.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-127">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd7e2-128">Il `/errorreport` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-128">The `/errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd7e2-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd7e2-129">Example</span></span>  
 <span data-ttu-id="fd7e2-130">Il codice seguente tenta di compilare `T2.vb`, e se il compilatore rileva un errore interno del compilatore, viene richiesto di inviare una segnalazione a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd7e2-130">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd7e2-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd7e2-131">See Also</span></span>  
 <span data-ttu-id="fd7e2-132">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="fd7e2-132">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="fd7e2-133"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="fd7e2-133"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="fd7e2-134"> [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)</span><span class="sxs-lookup"><span data-stu-id="fd7e2-134"> [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)</span></span>
