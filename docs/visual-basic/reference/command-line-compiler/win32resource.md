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
ms.openlocfilehash: cee06adec89aac4b3e3f170df3bf932e466f3070
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004969"
---
# <a name="-win32resource"></a><span data-ttu-id="9991b-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="9991b-102">-win32resource</span></span>
<span data-ttu-id="9991b-103">Inserisce un file di risorse Win32 nel file di output.</span><span class="sxs-lookup"><span data-stu-id="9991b-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9991b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9991b-104">Syntax</span></span>  
  
```console  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="9991b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9991b-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="9991b-106">Nome del file di risorse da aggiungere al file di output.</span><span class="sxs-lookup"><span data-stu-id="9991b-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="9991b-107">Racchiudere il nome file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="9991b-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9991b-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9991b-108">Remarks</span></span>  
 <span data-ttu-id="9991b-109">È possibile creare un file di risorse Win32 con il compilatore di risorse di Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="9991b-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="9991b-110">Una risorsa Win32 può contenere informazioni sulla versione o sulla bitmap (icona) che consentono di identificare l'applicazione in **Esplora file**.</span><span class="sxs-lookup"><span data-stu-id="9991b-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="9991b-111">Se non si specifica `-win32resource`, il compilatore genera le informazioni sulla versione in base alla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9991b-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="9991b-112">Le opzioni `-win32resource` e `-win32icon` si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="9991b-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="9991b-113">Vedere [-linkresource ((Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento a un file di risorse .NET Framework o [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) per alleghire un file di risorse .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9991b-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9991b-114">L' `-win32resource` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="9991b-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9991b-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="9991b-115">Example</span></span>  
 <span data-ttu-id="9991b-116">Il codice seguente compila `In.vb` e connette un file di risorse Win32: `Rf.res`</span><span class="sxs-lookup"><span data-stu-id="9991b-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9991b-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="9991b-117">See also</span></span>

- [<span data-ttu-id="9991b-118">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9991b-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9991b-119">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="9991b-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
