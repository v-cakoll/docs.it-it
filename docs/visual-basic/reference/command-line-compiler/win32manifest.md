---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 901ea984a8e8e90329953a8936e68f2fc07f8847
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="-win32manifest-visual-basic"></a><span data-ttu-id="a813a-102">-win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a813a-102">-win32manifest (Visual Basic)</span></span>
<span data-ttu-id="a813a-103">Identifica un file manifesto dell'applicazione Win32 definito dall'utente da incorporare nel file eseguibile di tipo PE di un progetto.</span><span class="sxs-lookup"><span data-stu-id="a813a-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a813a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a813a-104">Syntax</span></span>  
  
```  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="a813a-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a813a-105">Arguments</span></span>  
  
|<span data-ttu-id="a813a-106">Termine</span><span class="sxs-lookup"><span data-stu-id="a813a-106">Term</span></span>|<span data-ttu-id="a813a-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="a813a-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="a813a-108">Il percorso del file manifesto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="a813a-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a813a-109">Note</span><span class="sxs-lookup"><span data-stu-id="a813a-109">Remarks</span></span>  
 <span data-ttu-id="a813a-110">Per impostazione predefinita, il compilatore Visual Basic consente di incorporare un manifesto dell'applicazione che specifica un livello di esecuzione richiesto asInvoker.</span><span class="sxs-lookup"><span data-stu-id="a813a-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="a813a-111">Viene creato il manifesto nella stessa cartella in cui il file eseguibile viene compilato, in genere la cartella bin\Debug o bin\Release quando si utilizza Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a813a-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="a813a-112">Se si desidera fornire un manifesto personalizzato, ad esempio per specificare un livello di esecuzione richiesto highestAvailable o requireAdministrator, di utilizzare questa opzione per specificare il nome del file.</span><span class="sxs-lookup"><span data-stu-id="a813a-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a813a-113">Questa opzione e il [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) opzione si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="a813a-113">This option and the [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="a813a-114">Se si tenta di utilizzare entrambe le opzioni nella stessa riga di comando, si otterrà un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a813a-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="a813a-115">Un'applicazione senza un manifesto dell'applicazione che specifica un livello di esecuzione richiesto sarà soggetta alla virtualizzazione dei file e del Registro di sistema con la funzionalità Controllo account utente in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="a813a-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="a813a-116">Per ulteriori informazioni sulla virtualizzazione, vedere [distribuzione ClickOnce in Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="a813a-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="a813a-117">L'applicazione sarà soggetta a virtualizzazione in presenza di una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a813a-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1.  <span data-ttu-id="a813a-118">Utilizzare il `-nowin32manifest` opzione e non fornisce un manifesto in una successiva istruzione di compilazione o come parte di un file di risorse di Windows (. res) utilizzando il `-win32resource` opzione.</span><span class="sxs-lookup"><span data-stu-id="a813a-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span></span>  
  
2.  <span data-ttu-id="a813a-119">Si indica un manifesto personalizzato che non specifica un livello di esecuzione richiesto.</span><span class="sxs-lookup"><span data-stu-id="a813a-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="a813a-120">Visual Studio crea un file manifesto predefinito e lo archivia nella directory di debug e rilascio insieme al file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="a813a-120">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="a813a-121">È possibile visualizzare o modificare il file app. manifest predefinito facendo **Visualizza impostazioni di controllo dell'account utente** sul **applicazione** scheda della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a813a-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="a813a-122">Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a813a-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="a813a-123">È possibile fornire il manifesto dell'applicazione come passaggio post-compilazione personalizzato o come parte di un file di risorse Win32 usando il `-nowin32manifest` opzione.</span><span class="sxs-lookup"><span data-stu-id="a813a-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span></span> <span data-ttu-id="a813a-124">Usare la stessa opzione se si vuole che l'applicazione sia sottoposta alla virtualizzazione dei file o del Registro di sistema in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="a813a-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="a813a-125">Ciò impedirà al compilatore di creare e incorporare un manifesto predefinito nel file PE.</span><span class="sxs-lookup"><span data-stu-id="a813a-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a813a-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="a813a-126">Example</span></span>  
 <span data-ttu-id="a813a-127">Nell'esempio seguente viene illustrato il manifesto predefinito che il compilatore Visual Basic inserisce in un file PE.</span><span class="sxs-lookup"><span data-stu-id="a813a-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a813a-128">Il compilatore inserisce un nome di applicazione standard MyApplication. app nel manifesto XML.</span><span class="sxs-lookup"><span data-stu-id="a813a-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="a813a-129">Si tratta di una soluzione alternativa per consentire l'esecuzione delle applicazioni in Windows Server 2003 Service Pack 3.</span><span class="sxs-lookup"><span data-stu-id="a813a-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a813a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a813a-130">See Also</span></span>  
 [<span data-ttu-id="a813a-131">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a813a-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="a813a-132">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a813a-132">-nowin32manifest (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
