---
title: -win32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: 6f77649365f8ca7b163cd55854aa9960d88f2984
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414259"
---
# <a name="-win32manifest-visual-basic"></a><span data-ttu-id="6e2b9-102">-win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e2b9-102">-win32manifest (Visual Basic)</span></span>
<span data-ttu-id="6e2b9-103">Identifica un file manifesto dell'applicazione Win32 definito dall'utente da incorporare nel file eseguibile di tipo PE di un progetto.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e2b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e2b9-104">Syntax</span></span>  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="6e2b9-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6e2b9-105">Arguments</span></span>  
  
|<span data-ttu-id="6e2b9-106">Termine</span><span class="sxs-lookup"><span data-stu-id="6e2b9-106">Term</span></span>|<span data-ttu-id="6e2b9-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="6e2b9-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="6e2b9-108">Percorso del file manifesto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e2b9-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="6e2b9-109">Remarks</span></span>  
 <span data-ttu-id="6e2b9-110">Per impostazione predefinita, il compilatore Visual Basic incorpora un manifesto dell'applicazione che specifica un livello di esecuzione richiesto di asInvoker.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="6e2b9-111">Crea il manifesto nella stessa cartella in cui viene compilato il file eseguibile, in genere la cartella bin\Debug o bin\Release quando si usa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="6e2b9-112">Se si desidera fornire un manifesto personalizzato, ad esempio per specificare un livello di esecuzione richiesto di highestAvailable o requireAdministrator, utilizzare questa opzione per specificare il nome del file.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e2b9-113">Questa opzione e l'opzione [-win32resource (](win32resource.md) si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-113">This option and the [-win32resource](win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="6e2b9-114">Se si tenta di usare entrambe le opzioni nella stessa riga di comando, si otterrà un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="6e2b9-115">Un'applicazione senza un manifesto dell'applicazione che specifica un livello di esecuzione richiesto sarà soggetta alla virtualizzazione dei file e del Registro di sistema con la funzionalità Controllo account utente in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="6e2b9-116">Per altre informazioni sulla virtualizzazione, vedere [Distribuzione ClickOnce in Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="6e2b9-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="6e2b9-117">L'applicazione sarà soggetta alla virtualizzazione se si verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e2b9-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1. <span data-ttu-id="6e2b9-118">Usare l' `-nowin32manifest` opzione e non si fornisce un manifesto in un'istruzione di compilazione successiva o come parte di un file di risorse Windows (res) tramite l' `-win32resource` opzione.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span></span>  
  
2. <span data-ttu-id="6e2b9-119">Si indica un manifesto personalizzato che non specifica un livello di esecuzione richiesto.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="6e2b9-120">Visual Studio crea un file manifesto predefinito e lo memorizza nelle directory di debug e versione insieme al file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-120">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="6e2b9-121">Per visualizzare o modificare il file app. manifest predefinito, fare clic su **Visualizza impostazioni UAC** nella scheda **applicazione** in Progettazione progetti.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="6e2b9-122">Per altre informazioni, vedere [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6e2b9-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="6e2b9-123">È possibile fornire il manifesto dell'applicazione come passaggio di post-compilazione personalizzato o come parte di un file di risorse Win32 utilizzando l' `-nowin32manifest` opzione.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span></span> <span data-ttu-id="6e2b9-124">Usare la stessa opzione se si vuole che l'applicazione sia sottoposta alla virtualizzazione dei file o del Registro di sistema in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="6e2b9-125">In questo modo si impedisce al compilatore di creare e incorporare un manifesto predefinito nel file PE.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e2b9-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e2b9-126">Example</span></span>  
 <span data-ttu-id="6e2b9-127">Nell'esempio seguente viene illustrato il manifesto predefinito inserito dal compilatore Visual Basic in un file PE.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e2b9-128">Il compilatore inserisce nel file XML del manifesto un nome applicazione standard MyApplication. app.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="6e2b9-129">Si tratta di una soluzione alternativa per consentire l'esecuzione delle applicazioni in Windows Server 2003 Service Pack 3.</span><span class="sxs-lookup"><span data-stu-id="6e2b9-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6e2b9-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e2b9-130">See also</span></span>

- [<span data-ttu-id="6e2b9-131">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e2b9-131">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="6e2b9-132">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e2b9-132">-nowin32manifest (Visual Basic)</span></span>](nowin32manifest.md)
