---
title: -resource
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: cf9fe8dae0d35df694891633a6e3cf950bfb7376
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363617"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="393f9-102">-Resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="393f9-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="393f9-103">Incorpora una risorsa gestita in un assembly.</span><span class="sxs-lookup"><span data-stu-id="393f9-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="393f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="393f9-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="393f9-105">Oppure</span><span class="sxs-lookup"><span data-stu-id="393f9-105">or</span></span>  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="393f9-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="393f9-106">Arguments</span></span>  
  
|<span data-ttu-id="393f9-107">Termine</span><span class="sxs-lookup"><span data-stu-id="393f9-107">Term</span></span>|<span data-ttu-id="393f9-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="393f9-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="393f9-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="393f9-109">Required.</span></span> <span data-ttu-id="393f9-110">Nome del file di risorse da incorporare nel file di output.</span><span class="sxs-lookup"><span data-stu-id="393f9-110">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="393f9-111">Per impostazione predefinita, `filename` è Public nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="393f9-111">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="393f9-112">Racchiudere il nome file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="393f9-112">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="393f9-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="393f9-113">Optional.</span></span> <span data-ttu-id="393f9-114">Nome logico della risorsa. nome usato per caricarlo.</span><span class="sxs-lookup"><span data-stu-id="393f9-114">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="393f9-115">L'impostazione predefinita corrisponde al nome del file.</span><span class="sxs-lookup"><span data-stu-id="393f9-115">The default is the name of the file.</span></span> <span data-ttu-id="393f9-116">Facoltativamente, è possibile specificare se la risorsa è pubblica o privata nel manifesto dell'assembly, come nel seguente esempio:`-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="393f9-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="393f9-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="393f9-117">Remarks</span></span>  
 <span data-ttu-id="393f9-118">Usare `-linkresource` per collegare una risorsa a un assembly senza inserire il file di risorse nel file di output.</span><span class="sxs-lookup"><span data-stu-id="393f9-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="393f9-119">Se `filename` è un file di risorse .NET Framework creato, ad esempio da [Resgen. exe (Generatore di file di risorse)](../../../framework/tools/resgen-exe-resource-file-generator.md) o nell'ambiente di sviluppo, è possibile accedervi con i membri dello <xref:System.Resources> spazio dei nomi ( <xref:System.Resources.ResourceManager> per ulteriori informazioni, vedere).</span><span class="sxs-lookup"><span data-stu-id="393f9-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="393f9-120">Per accedere a tutte le altre risorse in fase di esecuzione, usare uno dei metodi seguenti: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A> , <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A> .</span><span class="sxs-lookup"><span data-stu-id="393f9-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="393f9-121">La forma breve di `-resource` è `-res`.</span><span class="sxs-lookup"><span data-stu-id="393f9-121">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="393f9-122">Per informazioni su come impostare `-resource` nell'IDE di Visual Studio, vedere [gestione delle risorse dell'applicazione (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="393f9-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="393f9-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="393f9-123">Example</span></span>  
 <span data-ttu-id="393f9-124">Il codice seguente compila `In.vb` e connette il file di risorse `Rf.resource` .</span><span class="sxs-lookup"><span data-stu-id="393f9-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="393f9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="393f9-125">See also</span></span>

- [<span data-ttu-id="393f9-126">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="393f9-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="393f9-127">-win32resource</span><span class="sxs-lookup"><span data-stu-id="393f9-127">-win32resource</span></span>](win32resource.md)
- [<span data-ttu-id="393f9-128">-linkresource ((Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="393f9-128">-linkresource (Visual Basic)</span></span>](linkresource.md)
- [<span data-ttu-id="393f9-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="393f9-129">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="393f9-130">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="393f9-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
