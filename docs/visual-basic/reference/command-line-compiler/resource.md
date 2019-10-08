---
title: -Resource (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 5bedc346381f6de293933dce14a8c5c3044b246f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005199"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="18ba1-102">-Resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18ba1-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="18ba1-103">Incorpora una risorsa gestita in un assembly.</span><span class="sxs-lookup"><span data-stu-id="18ba1-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18ba1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18ba1-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="18ba1-105">oppure</span><span class="sxs-lookup"><span data-stu-id="18ba1-105">or</span></span>  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="18ba1-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="18ba1-106">Arguments</span></span>  
  
|<span data-ttu-id="18ba1-107">Nome</span><span class="sxs-lookup"><span data-stu-id="18ba1-107">Term</span></span>|<span data-ttu-id="18ba1-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="18ba1-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="18ba1-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="18ba1-109">Required.</span></span> <span data-ttu-id="18ba1-110">Nome del file di risorse da incorporare nel file di output.</span><span class="sxs-lookup"><span data-stu-id="18ba1-110">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="18ba1-111">Per impostazione predefinita, `filename` è pubblico nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="18ba1-111">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="18ba1-112">Racchiudere il nome file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="18ba1-112">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="18ba1-113">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="18ba1-113">Optional.</span></span> <span data-ttu-id="18ba1-114">Nome logico della risorsa. nome usato per caricarlo.</span><span class="sxs-lookup"><span data-stu-id="18ba1-114">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="18ba1-115">L'impostazione predefinita corrisponde al nome del file.</span><span class="sxs-lookup"><span data-stu-id="18ba1-115">The default is the name of the file.</span></span> <span data-ttu-id="18ba1-116">Facoltativamente, è possibile specificare se la risorsa è pubblica o privata nel manifesto dell'assembly, come nel seguente esempio: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="18ba1-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18ba1-117">Note</span><span class="sxs-lookup"><span data-stu-id="18ba1-117">Remarks</span></span>  
 <span data-ttu-id="18ba1-118">Usare `-linkresource` per collegare una risorsa a un assembly senza inserire il file di risorse nel file di output.</span><span class="sxs-lookup"><span data-stu-id="18ba1-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="18ba1-119">Se `filename` è un file di risorse .NET Framework creato, ad esempio da [Resgen. exe (Generatore di file di risorse)](../../../framework/tools/resgen-exe-resource-file-generator.md) o nell'ambiente di sviluppo, è possibile accedervi con membri nello spazio dei nomi <xref:System.Resources> (per altre informazioni, vedere <xref:System.Resources.ResourceManager>).</span><span class="sxs-lookup"><span data-stu-id="18ba1-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="18ba1-120">Per accedere a tutte le altre risorse in fase di esecuzione, usare uno dei metodi seguenti: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="18ba1-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="18ba1-121">La forma breve di `-resource` è `-res`.</span><span class="sxs-lookup"><span data-stu-id="18ba1-121">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="18ba1-122">Per informazioni su come impostare `-resource` nell'IDE di Visual Studio, vedere [gestione delle risorse dell'applicazione (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="18ba1-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="18ba1-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="18ba1-123">Example</span></span>  
 <span data-ttu-id="18ba1-124">Il codice seguente compila `In.vb` e connette il file di risorse `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="18ba1-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="18ba1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18ba1-125">See also</span></span>

- [<span data-ttu-id="18ba1-126">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="18ba1-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="18ba1-127">-win32resource</span><span class="sxs-lookup"><span data-stu-id="18ba1-127">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [<span data-ttu-id="18ba1-128">-linkresource ((Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18ba1-128">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [<span data-ttu-id="18ba1-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18ba1-129">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="18ba1-130">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="18ba1-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
