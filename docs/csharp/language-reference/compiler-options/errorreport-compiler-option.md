---
title: -errorreport (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /errorreport
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
ms.openlocfilehash: 52b58aac5e82d4228dfda9c4d77c1d1c5de3e0cd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253888"
---
# <a name="-errorreport-c-compiler-options"></a><span data-ttu-id="30553-102">-errorreport (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="30553-102">-errorreport (C# Compiler Options)</span></span>
<span data-ttu-id="30553-103">Questa opzione rappresenta un modo pratico per segnalare a Microsoft un errore del compilatore interno C#.</span><span class="sxs-lookup"><span data-stu-id="30553-103">This option provides a convenient way to report a C# internal compiler error to Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="30553-104">In Windows Vista e Windows Server 2008 le impostazioni di segnalazione errori apportate per Visual Studio non eseguono l'override delle impostazioni apportate tramite Segnalazioni errori Windows.</span><span class="sxs-lookup"><span data-stu-id="30553-104">On Windows Vista and Windows Server 2008, the error reporting settings that you make for Visual Studio do not override the settings made through Windows Error Reporting (WER).</span></span> <span data-ttu-id="30553-105">Le impostazioni di Segnalazione errori Windows hanno sempre la precedenza sulle impostazioni della funzione di segnalazione errori di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="30553-105">WER settings always take precedence over Visual Studio error reporting settings.</span></span>

## <a name="syntax"></a><span data-ttu-id="30553-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30553-106">Syntax</span></span>

```console
-errorreport:{ none | prompt | queue | send }
```

## <a name="arguments"></a><span data-ttu-id="30553-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="30553-107">Arguments</span></span>
 <span data-ttu-id="30553-108">**none**</span><span class="sxs-lookup"><span data-stu-id="30553-108">**none**</span></span>  
 <span data-ttu-id="30553-109">Le segnalazioni sugli errori interni del compilatore non verranno raccolte o inviate a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="30553-109">Reports about internal compiler errors will not be collected or sent to Microsoft.</span></span>

 <span data-ttu-id="30553-110">**messaggio di richiesta** Richiede di inviare un report quando si riceve un errore interno del compilatore.</span><span class="sxs-lookup"><span data-stu-id="30553-110">**prompt** Prompts you to send a report when you receive an internal compiler error.</span></span> <span data-ttu-id="30553-111">**prompt** è l'impostazione predefinita se si compila un'applicazione all'interno dell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="30553-111">**prompt** is the default when you compile an application in the development environment.</span></span>

 <span data-ttu-id="30553-112">**coda** di Accoda la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="30553-112">**queue** Queues the error report.</span></span> <span data-ttu-id="30553-113">Se si accede con credenziali amministrative, è possibile segnalare qualsiasi errore dall'ultima volta che è stato effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="30553-113">When you log on with administrative credentials, you can report any failures since the last time that you were logged on.</span></span> <span data-ttu-id="30553-114">Non verrà richiesto di inviare report di errori più di una volta ogni tre giorni.</span><span class="sxs-lookup"><span data-stu-id="30553-114">You will not be prompted to send reports for failures more than once every three days.</span></span> <span data-ttu-id="30553-115">**queue** è l'impostazione predefinita se si compila un'applicazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="30553-115">**queue** is the default when you compile an application at the command line.</span></span>

 <span data-ttu-id="30553-116">**Invia** Invia automaticamente i report degli errori interni del compilatore a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="30553-116">**send** Automatically sends reports of internal compiler errors to Microsoft.</span></span> <span data-ttu-id="30553-117">Per abilitare questa opzione, è necessario prima di tutto accettare i Criteri per la raccolta dati Microsoft.</span><span class="sxs-lookup"><span data-stu-id="30553-117">To enable this option, you must first agree to the Microsoft data collection policy.</span></span> <span data-ttu-id="30553-118">La prima volta che si specifica **-errorreport:send** in un computer, viene visualizzato un messaggio del compilatore che indirizza a un sito Web contenente questi criteri.</span><span class="sxs-lookup"><span data-stu-id="30553-118">The first time that you specify **-errorreport:send** on a computer, a compiler message will refer you to a Web site that contains the Microsoft data collection policy.</span></span>

## <a name="remarks"></a><span data-ttu-id="30553-119">Note</span><span class="sxs-lookup"><span data-stu-id="30553-119">Remarks</span></span>
 <span data-ttu-id="30553-120">Se il compilatore non è in grado di elaborare un file del codice sorgente, viene restituito un errore interno del compilatore (ICE, Internal Compiler Error).</span><span class="sxs-lookup"><span data-stu-id="30553-120">An internal compiler error (ICE) results when the compiler cannot process a source code file.</span></span> <span data-ttu-id="30553-121">Quando si verifica un ICE, il compilatore non genera né un file di output né informazioni di diagnostica utili per correggere il codice.</span><span class="sxs-lookup"><span data-stu-id="30553-121">When an ICE occurs, the compiler does not produce an output file or any useful diagnostic that you can use to fix your code.</span></span>

 <span data-ttu-id="30553-122">Nelle versioni precedenti, quando si riceveva un ICE si riceveva anche l'invito a contattare il Servizio supporto tecnico Microsoft per segnalare il problema.</span><span class="sxs-lookup"><span data-stu-id="30553-122">In previous releases, when you received an ICE, you were encouraged to contact Microsoft Product Support Services to report the problem.</span></span> <span data-ttu-id="30553-123">Con **-errorreport** è possibile offrire informazioni sugli errori interni del compilatore al team Visual C#.</span><span class="sxs-lookup"><span data-stu-id="30553-123">By using **-errorreport**, you can provide ICE information to the Visual C# team.</span></span> <span data-ttu-id="30553-124">Le segnalazioni degli errori consentono di migliorare le versioni future del compilatore.</span><span class="sxs-lookup"><span data-stu-id="30553-124">Your error reports can help improve future compiler releases.</span></span>

 <span data-ttu-id="30553-125">La capacità di un utente di inviare report dipende dalle autorizzazioni relative ai criteri utente e computer.</span><span class="sxs-lookup"><span data-stu-id="30553-125">A user's ability to send reports depends on computer and user policy permissions.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="30553-126">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="30553-126">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="30553-127">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="30553-127">Open the project's **Properties** page.</span></span> <span data-ttu-id="30553-128">Per altre informazioni, vedere [Pagina Compilazione, Creazione progetti (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="30553-128">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>

2. <span data-ttu-id="30553-129">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="30553-129">Click the **Build** property page.</span></span>

3. <span data-ttu-id="30553-130">Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="30553-130">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="30553-131">Modificare la proprietà **Segnalazione errori interni del compilatore**.</span><span class="sxs-lookup"><span data-stu-id="30553-131">Modify the **Internal Compiler Error Reporting** property.</span></span>

 <span data-ttu-id="30553-132">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span><span class="sxs-lookup"><span data-stu-id="30553-132">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="30553-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30553-133">See also</span></span>

- [<span data-ttu-id="30553-134">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="30553-134">C# Compiler Options</span></span>](./index.md)
