---
title: /win32manifest (Visual Basic) | Documenti di Microsoft
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
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: 9
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
ms.openlocfilehash: 4a9693bd7eb03dee5a2a9f2d43360b963e9fd876
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="win32manifest-visual-basic"></a><span data-ttu-id="1c37d-102">/win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c37d-102">/win32manifest (Visual Basic)</span></span>
<span data-ttu-id="1c37d-103">Identifica un file manifesto dell'applicazione Win32 definito dall'utente da incorporare nel file eseguibile di tipo PE di un progetto.</span><span class="sxs-lookup"><span data-stu-id="1c37d-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c37d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c37d-104">Syntax</span></span>  
  
```  
/win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="1c37d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1c37d-105">Arguments</span></span>  
  
|<span data-ttu-id="1c37d-106">Termine</span><span class="sxs-lookup"><span data-stu-id="1c37d-106">Term</span></span>|<span data-ttu-id="1c37d-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="1c37d-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="1c37d-108">Il percorso del file manifesto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1c37d-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c37d-109">Note</span><span class="sxs-lookup"><span data-stu-id="1c37d-109">Remarks</span></span>  
 <span data-ttu-id="1c37d-110">Per impostazione predefinita, il compilatore Visual Basic consente di incorporare un manifesto dell'applicazione che specifica un livello di esecuzione richiesto di asInvoker.</span><span class="sxs-lookup"><span data-stu-id="1c37d-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="1c37d-111">Crea il manifesto nella stessa cartella in cui viene compilato il file eseguibile, in genere la cartella bin\Debug o bin\Release quando si utilizza Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1c37d-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="1c37d-112">Se si desidera fornire un manifesto personalizzato, ad esempio per specificare un livello di esecuzione richiesto di highestAvailable o requireAdministrator, utilizzare questa opzione per specificare il nome del file.</span><span class="sxs-lookup"><span data-stu-id="1c37d-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c37d-113">Questa opzione e [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) opzione si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="1c37d-113">This option and the [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="1c37d-114">Se si tenta di utilizzare entrambe le opzioni nella stessa riga di comando, si otterrà un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="1c37d-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="1c37d-115">Un'applicazione che non ha alcuna applicazione manifesto che specifica che un livello di esecuzione sarà soggetto alla virtualizzazione di file/registro di sistema nella funzionalità controllo Account utente in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="1c37d-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="1c37d-116">Per ulteriori informazioni sulla virtualizzazione, vedere [distribuzione ClickOnce in Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="1c37d-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="1c37d-117">L'applicazione sarà sottoposto a virtualizzazione se viene soddisfatta una delle seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="1c37d-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1.  <span data-ttu-id="1c37d-118">Utilizzare il `/nowin32manifest` opzione e non fornisce un manifesto in una successiva istruzione di compilazione o come parte di un file di risorse di Windows (con estensione res) utilizzando il `/win32resource` (opzione).</span><span class="sxs-lookup"><span data-stu-id="1c37d-118">You use the `/nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `/win32resource` option.</span></span>  
  
2.  <span data-ttu-id="1c37d-119">Fornire un manifesto personalizzato che non specifica un livello di esecuzione richiesto.</span><span class="sxs-lookup"><span data-stu-id="1c37d-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="1c37d-120">Crea un file manifesto predefinito e archiviarlo nella directory di debug e release insieme al file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="1c37d-120"> creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="1c37d-121">È possibile visualizzare o modificare il file app. manifest predefinito facendo clic su **visualizzare le impostazioni di controllo dell'account utente** sul **applicazione** scheda in Progettazione progetti.</span><span class="sxs-lookup"><span data-stu-id="1c37d-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="1c37d-122">Per ulteriori informazioni, vedere [pagina applicazione, Progettazione progetti (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="1c37d-122">For more information, see [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="1c37d-123">È possibile fornire il manifesto dell'applicazione come passaggio post-compilazione personalizzato o come parte di un file di risorse Win32 usando il `/nowin32manifest` (opzione).</span><span class="sxs-lookup"><span data-stu-id="1c37d-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `/nowin32manifest` option.</span></span> <span data-ttu-id="1c37d-124">Utilizzare la stessa opzione se si desidera che l'applicazione sia sottoposto a virtualizzazione di file o del Registro di sistema in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="1c37d-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="1c37d-125">Ciò impedirà il compilatore di creare e incorporare un manifesto predefinito nel file PE.</span><span class="sxs-lookup"><span data-stu-id="1c37d-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c37d-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c37d-126">Example</span></span>  
 <span data-ttu-id="1c37d-127">Nell'esempio seguente viene illustrato il manifesto predefinito che il compilatore Visual Basic inserisce in un file PE.</span><span class="sxs-lookup"><span data-stu-id="1c37d-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c37d-128">Il compilatore inserisce un nome dell'applicazione standard MyApplication. app nel manifesto XML.</span><span class="sxs-lookup"><span data-stu-id="1c37d-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="1c37d-129">Si tratta di una soluzione per consentire alle applicazioni per l'esecuzione in Windows Server 2003 Service Pack 3.</span><span class="sxs-lookup"><span data-stu-id="1c37d-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="1c37d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c37d-130">See Also</span></span>  
 <span data-ttu-id="1c37d-131">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="1c37d-131">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="1c37d-132"> [/nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)</span><span class="sxs-lookup"><span data-stu-id="1c37d-132"> [/nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)</span></span>
