---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: 382dcc6571aa06ecdfc32bf43080c4b7a36eb1f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961295"
---
# <a name="-win32resource"></a><span data-ttu-id="f88a8-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="f88a8-102">-win32resource</span></span>
<span data-ttu-id="f88a8-103">Inserisce un file di risorse Win32 nel file di output.</span><span class="sxs-lookup"><span data-stu-id="f88a8-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f88a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f88a8-104">Syntax</span></span>  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="f88a8-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f88a8-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="f88a8-106">Nome del file di risorse da aggiungere al file di output.</span><span class="sxs-lookup"><span data-stu-id="f88a8-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="f88a8-107">Racchiudere il nome file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="f88a8-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f88a8-108">Note</span><span class="sxs-lookup"><span data-stu-id="f88a8-108">Remarks</span></span>  
 <span data-ttu-id="f88a8-109">È possibile creare un file di risorse Win32 con il compilatore di risorse di Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="f88a8-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="f88a8-110">Una risorsa Win32 può contenere informazioni sulla versione o sulla bitmap (icona) che consentono di identificare l'applicazione in **Esplora file**.</span><span class="sxs-lookup"><span data-stu-id="f88a8-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="f88a8-111">Se non si specifica `-win32resource`, il compilatore genera le informazioni sulla versione in base alla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f88a8-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="f88a8-112">Le `-win32resource` opzioni `-win32icon` e si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="f88a8-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="f88a8-113">Vedere [-linkresource ((Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento a un file di risorse .NET Framework o [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) per alleghire un file di risorse .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f88a8-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f88a8-114">L' `-win32resource` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f88a8-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f88a8-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="f88a8-115">Example</span></span>  
 <span data-ttu-id="f88a8-116">Il codice seguente compila `In.vb` e connette un `Rf.res`file di risorse Win32:</span><span class="sxs-lookup"><span data-stu-id="f88a8-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f88a8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f88a8-117">See also</span></span>

- [<span data-ttu-id="f88a8-118">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f88a8-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f88a8-119">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="f88a8-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
