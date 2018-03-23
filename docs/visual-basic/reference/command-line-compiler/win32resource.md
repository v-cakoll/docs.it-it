---
title: -win32resource
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e210d88d32ac7341ab881ca6ff0e44961469a31
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-win32resource"></a><span data-ttu-id="f1358-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="f1358-102">-win32resource</span></span>
<span data-ttu-id="f1358-103">Inserisce un file di risorse Win32 nel file di output.</span><span class="sxs-lookup"><span data-stu-id="f1358-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1358-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1358-104">Syntax</span></span>  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="f1358-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f1358-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="f1358-106">Il nome del file di risorse da aggiungere al file di output.</span><span class="sxs-lookup"><span data-stu-id="f1358-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="f1358-107">Racchiudere il nome del file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="f1358-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1358-108">Note</span><span class="sxs-lookup"><span data-stu-id="f1358-108">Remarks</span></span>  
 <span data-ttu-id="f1358-109">È possibile creare un file di risorse Win32 con il compilatore di risorse (RC) di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="f1358-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="f1358-110">Una risorsa Win32 può contenere una versione o le informazioni di bitmap (icona) che consente di identificare l'applicazione in **Esplora File**.</span><span class="sxs-lookup"><span data-stu-id="f1358-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="f1358-111">Se non si specifica `-win32resource`, il compilatore genera le informazioni sulla versione in base alla versione di assembly.</span><span class="sxs-lookup"><span data-stu-id="f1358-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="f1358-112">Il `-win32resource` e `-win32icon` opzioni si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="f1358-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="f1358-113">Vedere [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse, o [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) per collegare un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse.</span><span class="sxs-lookup"><span data-stu-id="f1358-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1358-114">Il `-win32resource` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f1358-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1358-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="f1358-115">Example</span></span>  
 <span data-ttu-id="f1358-116">Il codice seguente Compila `In.vb` e allegare il file di risorse Win32, `Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="f1358-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1358-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1358-117">See Also</span></span>  
 [<span data-ttu-id="f1358-118">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f1358-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="f1358-119">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="f1358-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
