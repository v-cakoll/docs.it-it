---
title: -win32manifest (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /win32manifest
helpviewer_keywords:
- /win32manifest compiler option [C#]
- win32manifest compiler option [C#]
- -win32manifest compiler option [C#]
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
ms.openlocfilehash: 24677b145974af03e6ddcac1b9bab5907ab70c7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69924679"
---
# <a name="-win32manifest-c-compiler-options"></a><span data-ttu-id="c3b91-102">-win32manifest (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="c3b91-102">-win32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="c3b91-103">Usare l'opzione **-win32manifest** per specificare un file manifesto dell'applicazione Win32 definito dall'utente da incorporare nel file PE (Portable Executable) di un progetto.</span><span class="sxs-lookup"><span data-stu-id="c3b91-103">Use the **-win32manifest** option to specify a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b91-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3b91-104">Syntax</span></span>  
  
```console  
-win32manifest: filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="c3b91-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c3b91-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="c3b91-106">Nome e percorso del file manifesto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c3b91-106">The name and location of the custom manifest file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3b91-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c3b91-107">Remarks</span></span>  
 <span data-ttu-id="c3b91-108">Per impostazione predefinita, il compilatore Visual C# incorpora un manifesto dell'applicazione che specifica il livello di esecuzione richiesto "asInvoker".</span><span class="sxs-lookup"><span data-stu-id="c3b91-108">By default, the Visual C# compiler embeds an application manifest that specifies a requested execution level of "asInvoker."</span></span> <span data-ttu-id="c3b91-109">Viene creato il manifesto nella stessa cartella in cui viene compilato l'eseguibile, in genere la cartella bin\Debug o bin\Release quando si utilizza Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c3b91-109">It creates the manifest in the same folder in which the executable is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="c3b91-110">Se si desidera fornire un manifesto personalizzato, ad esempio per specificare un livello di esecuzione richiesto "highestAvailable" o "requireAdministrator", utilizzare questa opzione per specificare il nome del file.</span><span class="sxs-lookup"><span data-stu-id="c3b91-110">If you want to supply a custom manifest, for example to specify a requested execution level of "highestAvailable" or "requireAdministrator," use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3b91-111">Questa opzione e l'opzione [-win32res (opzioni del compilatore C#)](./win32res-compiler-option.md) si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="c3b91-111">This option and the [-win32res (C# Compiler Options)](./win32res-compiler-option.md) option are mutually exclusive.</span></span> <span data-ttu-id="c3b91-112">Se si tenta di usare entrambe le opzioni nella stessa riga di comando si otterrà un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c3b91-112">If you try to use both options in the same command line you will get a build error.</span></span>  
  
 <span data-ttu-id="c3b91-113">Un'applicazione senza un manifesto che specifichi il livello di esecuzione richiesto è soggetta alla virtualizzazione dei file e del Registro di sistema con la funzionalità Controllo account utente in Windows.</span><span class="sxs-lookup"><span data-stu-id="c3b91-113">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows.</span></span> <span data-ttu-id="c3b91-114">Per altre informazioni, vedere [Controllo dell'account utente](/windows/access-protection/user-account-control/user-account-control-overview).</span><span class="sxs-lookup"><span data-stu-id="c3b91-114">For more information, see [User Account Control](/windows/access-protection/user-account-control/user-account-control-overview).</span></span>  
  
 <span data-ttu-id="c3b91-115">L'applicazione sarà sottoposta a virtualizzazione se una di queste condizioni è vera:</span><span class="sxs-lookup"><span data-stu-id="c3b91-115">Your application will be subject to virtualization if either of these conditions is true:</span></span>  
  
- <span data-ttu-id="c3b91-116">Si usa l'opzione **-nowin32manifest** e non si specifica un manifesto in una fase successiva della compilazione o come parte di un file di risorse di Windows (con estensione res) usando l'opzione **-win32res**.</span><span class="sxs-lookup"><span data-stu-id="c3b91-116">You use the **-nowin32manifest** option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the **-win32res** option.</span></span>  
  
- <span data-ttu-id="c3b91-117">Si indica un manifesto personalizzato che non specifica un livello di esecuzione richiesto.</span><span class="sxs-lookup"><span data-stu-id="c3b91-117">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="c3b91-118">Visual Studio crea un file manifesto predefinito e lo memorizza nelle directory di debug e versione insieme al file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="c3b91-118">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="c3b91-119">Per aggiungere un manifesto personalizzato, crearne uno in qualsiasi editor di testo e quindi aggiungere il file al progetto.</span><span class="sxs-lookup"><span data-stu-id="c3b91-119">You can add a custom manifest by creating one in any text editor and then adding the file to the project.</span></span> <span data-ttu-id="c3b91-120">In alternativa, fare clic con il pulsante destro del mouse sull'icona **Progetto** in **Esplora soluzioni**, fare clic su **Aggiungi nuovo elemento** e quindi scegliere **File manifesto applicazione**.</span><span class="sxs-lookup"><span data-stu-id="c3b91-120">Alternatively, you can right-click the **Project** icon in **Solution Explorer**, click **Add New Item**, and then click **Application Manifest File**.</span></span> <span data-ttu-id="c3b91-121">Dopo aver aggiunto il file manifesto nuovo o esistente, il file apparirà nell'elenco a discesa **Manifesto**.</span><span class="sxs-lookup"><span data-stu-id="c3b91-121">After you have added your new or existing manifest file, it will appear in the **Manifest** drop down list.</span></span> <span data-ttu-id="c3b91-122">Per altre informazioni, vedere [Pagina dell'applicazione, Progettazione progetti (C )](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="c3b91-122">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="c3b91-123">È possibile inserire il manifesto dell'applicazione come passaggio personalizzato dopo la compilazione o come parte di un file di risorse Win32 usando l'opzione [-nowin32manifest (opzioni del compilatore C#)](./nowin32manifest-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c3b91-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the [-nowin32manifest (C# Compiler Options)](./nowin32manifest-compiler-option.md) option.</span></span> <span data-ttu-id="c3b91-124">Usare la stessa opzione se si vuole che l'applicazione sia sottoposta alla virtualizzazione dei file o del Registro di sistema in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="c3b91-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="c3b91-125">Ciò impedirà al compilatore di creare e incorporare un manifesto predefinito nel file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="c3b91-125">This will prevent the compiler from creating and embedding a default manifest in the portable executable (PE) file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3b91-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="c3b91-126">Example</span></span>  
 <span data-ttu-id="c3b91-127">Nell'esempio seguente viene illustrato il manifesto predefinito che il compilatore Visual C# inserisce in un file PE.</span><span class="sxs-lookup"><span data-stu-id="c3b91-127">The following example shows the default manifest that the Visual C# compiler inserts into a PE.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3b91-128">Il compilatore inserisce un nome di applicazione standard "MyApplication.app" nel file XML.</span><span class="sxs-lookup"><span data-stu-id="c3b91-128">The compiler inserts a standard application name " MyApplication.app " into the xml.</span></span> <span data-ttu-id="c3b91-129">Si tratta di una soluzione alternativa per consentire l'esecuzione delle applicazioni in Windows Server 2003 Service Pack 3.</span><span class="sxs-lookup"><span data-stu-id="c3b91-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c3b91-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3b91-130">See also</span></span>

- [<span data-ttu-id="c3b91-131">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="c3b91-131">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="c3b91-132">-nowin32manifest (opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="c3b91-132">-nowin32manifest (C# Compiler Options)</span></span>](./nowin32manifest-compiler-option.md)
- [<span data-ttu-id="c3b91-133">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="c3b91-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
