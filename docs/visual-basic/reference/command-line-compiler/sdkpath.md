---
title: /sdkpath
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- /sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 876922385124db3e8db12c93c75194da83d2526c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sdkpath"></a><span data-ttu-id="18226-102">/sdkpath</span><span class="sxs-lookup"><span data-stu-id="18226-102">/sdkpath</span></span>
<span data-ttu-id="18226-103">Specifica il percorso dei file Mscorlib.dll e Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="18226-103">Specifies the location of Mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18226-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18226-104">Syntax</span></span>  
  
```  
/sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="18226-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="18226-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="18226-106">La directory che contiene le versioni dei file Mscorlib.dll e Microsoft.VisualBasic.dll da utilizzare per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="18226-106">The directory containing the versions of Mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="18226-107">Questo percorso non è stato verificato finché viene caricato.</span><span class="sxs-lookup"><span data-stu-id="18226-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="18226-108">Racchiudere il nome della directory tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="18226-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18226-109">Note</span><span class="sxs-lookup"><span data-stu-id="18226-109">Remarks</span></span>  
 <span data-ttu-id="18226-110">Questa opzione indica il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore per caricare i file Mscorlib.dll e Microsoft.VisualBasic.dll da un percorso non predefinito.</span><span class="sxs-lookup"><span data-stu-id="18226-110">This option tells the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler to load the Mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="18226-111">Il `/sdkpath` opzione è stata progettata per essere utilizzato con [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span><span class="sxs-lookup"><span data-stu-id="18226-111">The `/sdkpath` option was designed to be used with [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="18226-112">Il [!INCLUDE[Compact](~/includes/compact-md.md)] Usa diverse versioni di queste librerie di supporto per evitare l'utilizzo di tipi e le funzionalità del linguaggio non trovate nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="18226-112">The [!INCLUDE[Compact](~/includes/compact-md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18226-113">Il `/sdkpath` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="18226-113">The `/sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="18226-114">Il `/sdkpath` opzione viene impostata quando un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] viene caricato il progetto di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="18226-114">The `/sdkpath` option is set when a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="18226-115">È possibile specificare che il compilatore deve compilare senza un riferimento alla libreria di Runtime di Visual Basic utilizzando il `/vbruntime` l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="18226-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `/vbruntime` compiler option.</span></span> <span data-ttu-id="18226-116">Per ulteriori informazioni, vedere [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="18226-116">For more information, see [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="18226-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="18226-117">Example</span></span>  
 <span data-ttu-id="18226-118">Il codice seguente Compila `Myfile.vb` con il [!INCLUDE[Compact](~/includes/compact-md.md)], usando le versioni dei file Mscorlib.dll e Microsoft.VisualBasic.dll trovato nella directory di installazione predefinita di [!INCLUDE[Compact](~/includes/compact-md.md)] nell'unità C.</span><span class="sxs-lookup"><span data-stu-id="18226-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="18226-119">In genere, si utilizzerà la versione più recente di [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18226-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="18226-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18226-120">See Also</span></span>  
 [<span data-ttu-id="18226-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="18226-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="18226-122">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="18226-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="18226-123">/netcf</span><span class="sxs-lookup"><span data-stu-id="18226-123">/netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [<span data-ttu-id="18226-124">/vbruntime</span><span class="sxs-lookup"><span data-stu-id="18226-124">/vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
