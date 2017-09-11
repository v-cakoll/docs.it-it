---
title: /sdkpath | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- /sdkpath
dev_langs:
- VB
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2e32bb403347063edcf0d47fd4a7511a0da1f340
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="sdkpath"></a><span data-ttu-id="2c18f-102">/sdkpath</span><span class="sxs-lookup"><span data-stu-id="2c18f-102">/sdkpath</span></span>
<span data-ttu-id="2c18f-103">Specifica il percorso dei file Mscorlib.dll e Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="2c18f-103">Specifies the location of Mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c18f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c18f-104">Syntax</span></span>  
  
```  
/sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="2c18f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2c18f-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="2c18f-106">La directory che contiene le versioni di mscorlib. dll e Microsoft.VisualBasic.dll da utilizzare per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="2c18f-106">The directory containing the versions of Mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="2c18f-107">Questo percorso non viene verificato finché viene caricato.</span><span class="sxs-lookup"><span data-stu-id="2c18f-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="2c18f-108">Racchiudere il nome della directory tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="2c18f-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c18f-109">Note</span><span class="sxs-lookup"><span data-stu-id="2c18f-109">Remarks</span></span>  
 <span data-ttu-id="2c18f-110">Questa opzione indica la [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore di caricare i file mscorlib. dll e Microsoft.VisualBasic.dll da un percorso non predefinito.</span><span class="sxs-lookup"><span data-stu-id="2c18f-110">This option tells the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to load the Mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="2c18f-111">Il `/sdkpath` opzione è stata progettata per essere utilizzato con [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span><span class="sxs-lookup"><span data-stu-id="2c18f-111">The `/sdkpath` option was designed to be used with [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="2c18f-112">Il [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] vengono utilizzate versioni diverse di queste librerie di supporto per evitare l'utilizzo di tipi e le funzionalità di linguaggio non disponibili nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="2c18f-112">The [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c18f-113">Il `/sdkpath` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="2c18f-113">The `/sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="2c18f-114">Il `/sdkpath` opzione viene impostata quando un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] dispositivo progetto viene caricato.</span><span class="sxs-lookup"><span data-stu-id="2c18f-114">The `/sdkpath` option is set when a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="2c18f-115">È possibile specificare che il compilatore esegue la compilazione senza un riferimento alla libreria di Runtime di Visual Basic utilizzando il `/vbruntime` l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="2c18f-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `/vbruntime` compiler option.</span></span> <span data-ttu-id="2c18f-116">Per ulteriori informazioni, vedere [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="2c18f-116">For more information, see [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c18f-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c18f-117">Example</span></span>  
 <span data-ttu-id="2c18f-118">Il codice seguente Compila `Myfile.vb` con il [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], con le versioni di mscorlib. dll e Microsoft.VisualBasic.dll trovato nella directory di installazione predefinita di [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] nell'unità C.</span><span class="sxs-lookup"><span data-stu-id="2c18f-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] on the C drive.</span></span> <span data-ttu-id="2c18f-119">In genere, si utilizzerà la versione più recente di [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c18f-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c18f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c18f-120">See Also</span></span>  
 <span data-ttu-id="2c18f-121">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="2c18f-121">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="2c18f-122"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="2c18f-122"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="2c18f-123"> [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md) </span><span class="sxs-lookup"><span data-stu-id="2c18f-123"> [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md) </span></span>  
<span data-ttu-id="2c18f-124"> [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)</span><span class="sxs-lookup"><span data-stu-id="2c18f-124"> [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)</span></span>
