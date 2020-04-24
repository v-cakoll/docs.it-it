---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 46cec7ac3cb78c4fc97e299535f9085eff6daeff
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004686"
---
# <a name="-sdkpath"></a><span data-ttu-id="be78f-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="be78f-102">-sdkpath</span></span>
<span data-ttu-id="be78f-103">Specifica il percorso dei file mscorlib. dll e Microsoft. VisualBasic. dll.</span><span class="sxs-lookup"><span data-stu-id="be78f-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be78f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be78f-104">Syntax</span></span>  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="be78f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="be78f-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="be78f-106">Directory contenente le versioni di mscorlib. dll e Microsoft. VisualBasic. dll da utilizzare per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="be78f-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="be78f-107">Questo percorso non viene verificato fino a quando non viene caricato.</span><span class="sxs-lookup"><span data-stu-id="be78f-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="be78f-108">Racchiudere il nome della directory tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="be78f-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be78f-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="be78f-109">Remarks</span></span>  
 <span data-ttu-id="be78f-110">Questa opzione indica al compilatore Visual Basic di caricare i file mscorlib. dll e Microsoft. VisualBasic. dll da un percorso non predefinito.</span><span class="sxs-lookup"><span data-stu-id="be78f-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="be78f-111">L' `-sdkpath` opzione è stata progettata per essere utilizzata con [-netcf (](../../../visual-basic/reference/command-line-compiler/netcf.md).</span><span class="sxs-lookup"><span data-stu-id="be78f-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="be78f-112">Il .NET Compact Framework utilizza versioni diverse di queste librerie di supporto per evitare l'utilizzo di tipi e funzionalità del linguaggio non disponibili nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="be78f-112">The .NET Compact Framework uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be78f-113">L' `-sdkpath` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="be78f-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="be78f-114">L' `-sdkpath` opzione viene impostata quando viene caricato un progetto Visual Basic dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be78f-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="be78f-115">È possibile specificare che il compilatore deve eseguire la compilazione senza un riferimento alla libreria di runtime Visual Basic usando `-vbruntime` l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="be78f-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="be78f-116">Per ulteriori informazioni, vedere [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="be78f-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be78f-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="be78f-117">Example</span></span>  
 <span data-ttu-id="be78f-118">Il codice seguente viene compilato `Myfile.vb` con il .NET Compact Framework, usando le versioni di mscorlib. dll e Microsoft. VisualBasic. dll disponibili nella directory di installazione predefinita del .NET Compact Framework nell'unità C.</span><span class="sxs-lookup"><span data-stu-id="be78f-118">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="be78f-119">In genere, si utilizzerà la versione più recente del .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="be78f-119">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="be78f-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="be78f-120">See also</span></span>

- [<span data-ttu-id="be78f-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be78f-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="be78f-122">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="be78f-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="be78f-123">-netcf (</span><span class="sxs-lookup"><span data-stu-id="be78f-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [<span data-ttu-id="be78f-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="be78f-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
