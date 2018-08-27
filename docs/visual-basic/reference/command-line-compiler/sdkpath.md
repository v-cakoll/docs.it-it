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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 162c7d58350c381ec667e8a4cd11c03e83fcdf44
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925685"
---
# <a name="-sdkpath"></a><span data-ttu-id="4c855-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="4c855-102">-sdkpath</span></span>
<span data-ttu-id="4c855-103">Specifica il percorso dei file mscorlib. dll e VisualBasic.</span><span class="sxs-lookup"><span data-stu-id="4c855-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c855-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c855-104">Syntax</span></span>  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="4c855-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4c855-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="4c855-106">La directory che contiene le versioni di mscorlib. dll e VisualBasic da utilizzare per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="4c855-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="4c855-107">Questo percorso non viene verificato fino a quando non viene caricato.</span><span class="sxs-lookup"><span data-stu-id="4c855-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="4c855-108">Racchiudere il nome della directory tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="4c855-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c855-109">Note</span><span class="sxs-lookup"><span data-stu-id="4c855-109">Remarks</span></span>  
 <span data-ttu-id="4c855-110">Questa opzione indica al compilatore di Visual Basic per caricare il file mscorlib. dll e file VisualBasic da un percorso non predefinito.</span><span class="sxs-lookup"><span data-stu-id="4c855-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="4c855-111">Il `-sdkpath` opzione è stata progettata per essere usata con [- netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span><span class="sxs-lookup"><span data-stu-id="4c855-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="4c855-112">Il [!INCLUDE[Compact](~/includes/compact-md.md)] Usa diverse versioni di queste librerie di supporto per evitare l'utilizzo di tipi e le funzionalità del linguaggio non trovate nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4c855-112">The [!INCLUDE[Compact](~/includes/compact-md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c855-113">Il `-sdkpath` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="4c855-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="4c855-114">Il `-sdkpath` opzione viene impostata quando viene caricato un progetto di Visual Basic dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c855-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="4c855-115">È possibile specificare che il compilatore esegue la compilazione senza un riferimento alla libreria di Runtime di Visual Basic usando il `-vbruntime` opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="4c855-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="4c855-116">Per altre informazioni, vedere [- /vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="4c855-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c855-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c855-117">Example</span></span>  
 <span data-ttu-id="4c855-118">Il codice seguente Compila `Myfile.vb` con il [!INCLUDE[Compact](~/includes/compact-md.md)], con le versioni di mscorlib. dll e VisualBasic trovato nella directory di installazione predefinita del [!INCLUDE[Compact](~/includes/compact-md.md)] nell'unità C.</span><span class="sxs-lookup"><span data-stu-id="4c855-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="4c855-119">In genere, si utilizzerebbe la versione più recente del [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c855-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c855-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c855-120">See Also</span></span>  
 [<span data-ttu-id="4c855-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c855-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="4c855-122">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="4c855-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="4c855-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="4c855-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [<span data-ttu-id="4c855-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="4c855-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
