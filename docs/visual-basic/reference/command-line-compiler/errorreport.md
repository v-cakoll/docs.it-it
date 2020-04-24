---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: a9741f7a8283f8603e02dae5abea151c6ee5d75e
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775673"
---
# <a name="-errorreport"></a><span data-ttu-id="04eb8-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="04eb8-102">-errorreport</span></span>

<span data-ttu-id="04eb8-103">Specifica il modo in cui il compilatore di Visual Basic deve segnalare gli errori interni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="04eb8-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="04eb8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04eb8-104">Syntax</span></span>

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="04eb8-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="04eb8-105">Remarks</span></span>

<span data-ttu-id="04eb8-106">Questa opzione offre un modo pratico per segnalare un errore interno del compilatore Visual Basic al team di Visual Basic di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04eb8-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="04eb8-107">Per impostazione predefinita, il compilatore non invia alcuna informazione a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04eb8-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="04eb8-108">Tuttavia, se si verifica un errore interno del compilatore, questa opzione consente di segnalare l'errore a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04eb8-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="04eb8-109">Tali informazioni consentiranno ai tecnici Microsoft di identificare la cause e possono contribuire a migliorare la prossima versione di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="04eb8-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="04eb8-110">La capacità di un utente di inviare i report dipende dalle autorizzazioni dei criteri utente e del computer.</span><span class="sxs-lookup"><span data-stu-id="04eb8-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="04eb8-111">Nella tabella seguente sono riepilogati gli effetti dell' `-errorreport` opzione.</span><span class="sxs-lookup"><span data-stu-id="04eb8-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="04eb8-112">Opzione</span><span class="sxs-lookup"><span data-stu-id="04eb8-112">Option</span></span>|<span data-ttu-id="04eb8-113">Comportamento</span><span class="sxs-lookup"><span data-stu-id="04eb8-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="04eb8-114">Se si verifica un errore interno del compilatore, viene visualizzata una finestra di dialogo in cui è possibile visualizzare i dati esatti raccolti dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="04eb8-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="04eb8-115">È possibile determinare se nel report degli errori sono presenti informazioni riservate e decidere se inviarle a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04eb8-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="04eb8-116">Se si decide di inviarlo e le impostazioni dei criteri utente e del computer lo consentono, il compilatore invia i dati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04eb8-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="04eb8-117">Accoda la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="04eb8-117">Queues the error report.</span></span> <span data-ttu-id="04eb8-118">Quando si esegue l'accesso con privilegi di amministratore, è possibile segnalare eventuali errori dall'ultima volta che è stato effettuato l'accesso. non verrà richiesto di inviare i report per gli errori più di una volta ogni tre giorni.</span><span class="sxs-lookup"><span data-stu-id="04eb8-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="04eb8-119">Si tratta del comportamento predefinito quando l' `-errorreport` opzione non è specificata.</span><span class="sxs-lookup"><span data-stu-id="04eb8-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="04eb8-120">Se si verifica un errore interno del compilatore e le impostazioni dei criteri utente e del computer lo consentono, il compilatore invia i dati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04eb8-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="04eb8-121">L'opzione `-errorreport:send` tenta di inviare automaticamente le informazioni sugli errori a Microsoft se la creazione di report è abilitata dalle impostazioni di sistema [segnalazione errori Windows](/windows/desktop/wer/windows-error-reporting) .</span><span class="sxs-lookup"><span data-stu-id="04eb8-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="04eb8-122">Se si verifica un errore interno del compilatore, non verrà raccolto né inviato a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04eb8-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="04eb8-123">Il compilatore invia i dati che includono lo stack al momento dell'errore, che in genere include un codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="04eb8-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="04eb8-124">Se `-errorreport` viene usato con l'opzione [-bugreport (](../../../visual-basic/reference/command-line-compiler/bugreport.md) , viene inviato l'intero file di origine.</span><span class="sxs-lookup"><span data-stu-id="04eb8-124">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="04eb8-125">Questa opzione è ideale per l'uso con l'opzione [-bugreport (](../../../visual-basic/reference/command-line-compiler/bugreport.md) , perché consente ai tecnici Microsoft di riprodurre più facilmente l'errore.</span><span class="sxs-lookup"><span data-stu-id="04eb8-125">This option is best used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="04eb8-126">L' `-errorreport` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="04eb8-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="04eb8-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="04eb8-127">Example</span></span>

<span data-ttu-id="04eb8-128">Il codice seguente tenta di compilare `T2.vb`e se il compilatore rileva un errore interno del compilatore, viene richiesto di inviare la segnalazione di errore a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04eb8-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="04eb8-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="04eb8-129">See also</span></span>

- [<span data-ttu-id="04eb8-130">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04eb8-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="04eb8-131">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="04eb8-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="04eb8-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="04eb8-132">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
