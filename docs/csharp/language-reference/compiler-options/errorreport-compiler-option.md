---
title: -errorreport (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /errorreport
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
caps.latest.revision: "35"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3063a29452d90a09d5904d2a598b62530104d739
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="errorreport-c-compiler-options"></a><span data-ttu-id="f2111-102">/errorreport (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f2111-102">/errorreport (C# Compiler Options)</span></span>
<span data-ttu-id="f2111-103">Questa opzione rappresenta un modo pratico per segnalare a Microsoft un errore del compilatore interno C#.</span><span class="sxs-lookup"><span data-stu-id="f2111-103">This option provides a convenient way to report a C# internal compiler error to Microsoft.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2111-104">In Windows Vista e Windows Server 2008 le impostazioni di segnalazione errori apportate per Visual Studio non eseguono l'override delle impostazioni apportate tramite Segnalazioni errori Windows.</span><span class="sxs-lookup"><span data-stu-id="f2111-104">On Windows Vista and Windows Server 2008, the error reporting settings that you make for Visual Studio do not override the settings made through Windows Error Reporting (WER).</span></span> <span data-ttu-id="f2111-105">Le impostazioni di Segnalazione errori Windows hanno sempre la precedenza sulle impostazioni della funzione di segnalazione errori di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f2111-105">WER settings always take precedence over Visual Studio error reporting settings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2111-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2111-106">Syntax</span></span>  
  
```console  
/errorreport:{ none | prompt | queue | send }  
```  
  
## <a name="arguments"></a><span data-ttu-id="f2111-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f2111-107">Arguments</span></span>  
 <span data-ttu-id="f2111-108">**none**</span><span class="sxs-lookup"><span data-stu-id="f2111-108">**none**</span></span>  
 <span data-ttu-id="f2111-109">Le segnalazioni sugli errori interni del compilatore non verranno raccolte o inviate a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2111-109">Reports about internal compiler errors will not be collected or sent to Microsoft.</span></span>  
  
 <span data-ttu-id="f2111-110">**prompt**</span><span class="sxs-lookup"><span data-stu-id="f2111-110">**prompt**</span></span>  
 <span data-ttu-id="f2111-111">Chiede di inviare una segnalazione quando si riceve un errore interno del compilatore.</span><span class="sxs-lookup"><span data-stu-id="f2111-111">Prompts you to send a report when you receive an internal compiler error.</span></span> <span data-ttu-id="f2111-112">**prompt** è l'impostazione predefinita se si compila un'applicazione all'interno dell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="f2111-112">**prompt** is the default when you compile an application in the development environment.</span></span>  
  
 <span data-ttu-id="f2111-113">**queue**</span><span class="sxs-lookup"><span data-stu-id="f2111-113">**queue**</span></span>  
 <span data-ttu-id="f2111-114">Accoda la segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="f2111-114">Queues the error report.</span></span> <span data-ttu-id="f2111-115">Se si accede con credenziali amministrative, è possibile segnalare qualsiasi errore dall'ultima volta che è stato effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f2111-115">When you log on with administrative credentials, you can report any failures since the last time that you were logged on.</span></span> <span data-ttu-id="f2111-116">Non verrà richiesto di inviare report di errori più di una volta ogni tre giorni.</span><span class="sxs-lookup"><span data-stu-id="f2111-116">You will not be prompted to send reports for failures more than once every three days.</span></span> <span data-ttu-id="f2111-117">**queue** è l'impostazione predefinita se si compila un'applicazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f2111-117">**queue** is the default when you compile an application at the command line.</span></span>  
  
 <span data-ttu-id="f2111-118">**send**</span><span class="sxs-lookup"><span data-stu-id="f2111-118">**send**</span></span>  
 <span data-ttu-id="f2111-119">Invia automaticamente a Microsoft le segnalazioni di errori interni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="f2111-119">Automatically sends reports of internal compiler errors to Microsoft.</span></span> <span data-ttu-id="f2111-120">Per abilitare questa opzione, è necessario prima di tutto accettare i Criteri per la raccolta dati Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2111-120">To enable this option, you must first agree to the Microsoft data collection policy.</span></span> <span data-ttu-id="f2111-121">La prima volta che si specifica **/errorreport:send** con un computer, viene visualizzato un messaggio del compilatore che indirizza a un sito Web contenente questi criteri.</span><span class="sxs-lookup"><span data-stu-id="f2111-121">The first time that you specify **/errorreport:send** on a computer, a compiler message will refer you to a Web site that contains the Microsoft data collection policy.</span></span>  
    
## <a name="remarks"></a><span data-ttu-id="f2111-122">Note</span><span class="sxs-lookup"><span data-stu-id="f2111-122">Remarks</span></span>  
 <span data-ttu-id="f2111-123">Se il compilatore non è in grado di elaborare un file del codice sorgente, viene restituito un errore interno del compilatore (ICE, Internal Compiler Error).</span><span class="sxs-lookup"><span data-stu-id="f2111-123">An internal compiler error (ICE) results when the compiler cannot process a source code file.</span></span> <span data-ttu-id="f2111-124">Quando si verifica un ICE, il compilatore non genera né un file di output né informazioni di diagnostica utili per correggere il codice.</span><span class="sxs-lookup"><span data-stu-id="f2111-124">When an ICE occurs, the compiler does not produce an output file or any useful diagnostic that you can use to fix your code.</span></span>  
  
 <span data-ttu-id="f2111-125">Nelle versioni precedenti, quando si riceveva un ICE si riceveva anche l'invito a contattare il Servizio supporto tecnico Microsoft per segnalare il problema.</span><span class="sxs-lookup"><span data-stu-id="f2111-125">In previous releases, when you received an ICE, you were encouraged to contact Microsoft Product Support Services to report the problem.</span></span> <span data-ttu-id="f2111-126">Con **/errorreport** è possibile fornire informazioni sugli errori interni del compilatore al team Visual C#.</span><span class="sxs-lookup"><span data-stu-id="f2111-126">By using **/errorreport**, you can provide ICE information to the Visual C# team.</span></span> <span data-ttu-id="f2111-127">Le segnalazioni degli errori consentono di migliorare le versioni future del compilatore.</span><span class="sxs-lookup"><span data-stu-id="f2111-127">Your error reports can help improve future compiler releases.</span></span>  
  
 <span data-ttu-id="f2111-128">La capacità di un utente di inviare report dipende dalle autorizzazioni relative ai criteri utente e computer.</span><span class="sxs-lookup"><span data-stu-id="f2111-128">A user's ability to send reports depends on computer and user policy permissions.</span></span>  
  
 <span data-ttu-id="f2111-129">Per altre informazioni sul debugger degli errori, vedere [Descrizione dello strumento Dr. Watson per Windows (Drwtsn32.exe)](http://go.microsoft.com/fwlink/?LinkId=147286).</span><span class="sxs-lookup"><span data-stu-id="f2111-129">For more information about error debugger, see [Description of the Dr. Watson for Windows (Drwtsn32.exe) Tool](http://go.microsoft.com/fwlink/?LinkId=147286).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f2111-130">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f2111-130">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="f2111-131">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="f2111-131">Open the project's **Properties** page.</span></span> <span data-ttu-id="f2111-132">Per altre informazioni, vedere [Pagina Compilazione, Creazione progetti (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="f2111-132">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="f2111-133">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="f2111-133">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="f2111-134">Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="f2111-134">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="f2111-135">Modificare la proprietà **Segnalazione errori interni del compilatore**.</span><span class="sxs-lookup"><span data-stu-id="f2111-135">Modify the **Internal Compiler Error Reporting** property.</span></span>  
  
 <span data-ttu-id="f2111-136">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span><span class="sxs-lookup"><span data-stu-id="f2111-136">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2111-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2111-137">See Also</span></span>  
 [<span data-ttu-id="f2111-138">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="f2111-138">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
