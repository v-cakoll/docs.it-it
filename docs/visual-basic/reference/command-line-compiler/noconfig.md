---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: 44bc619c489fdff36f0b595f7d8934689b859adb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819437"
---
# <a name="-noconfig"></a><span data-ttu-id="a910e-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="a910e-102">-noconfig</span></span>
<span data-ttu-id="a910e-103">Specifica che il compilatore non deve automaticamente fare riferimento usati comunemente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] l'importazione o l'assembly la `System` e `Microsoft.VisualBasic` gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a910e-103">Specifies that the compiler should not automatically reference the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a910e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a910e-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="a910e-105">Note</span><span class="sxs-lookup"><span data-stu-id="a910e-105">Remarks</span></span>  
 <span data-ttu-id="a910e-106">Il `-noconfig` opzione indica al compilatore di non eseguire la compilazione con il file Vbc. rsp, che si trova nella stessa directory del file Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="a910e-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="a910e-107">Il file Vbc. rsp fa riferimento il diffuso [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] gli assembly e le importazioni il `System` e `Microsoft.VisualBasic` gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a910e-107">The Vbc.rsp file references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="a910e-108">Il compilatore fa riferimento in modo implicito all'assembly System. dll, a meno che il `-nostdlib` opzione specificata.</span><span class="sxs-lookup"><span data-stu-id="a910e-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="a910e-109">Il `-nostdlib` opzione indica al compilatore di non eseguire la compilazione con Vbc. rsp o automaticamente fare riferimento all'assembly System. dll.</span><span class="sxs-lookup"><span data-stu-id="a910e-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a910e-110">Gli assembly mscorlib. dll e VisualBasic vengono sempre fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="a910e-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="a910e-111">È possibile modificare il file Vbc. per specificare altre opzioni del compilatore che devono essere incluse in ogni compilazione Vbc.exe (tranne quando si specifica il `-noconfig` opzione).</span><span class="sxs-lookup"><span data-stu-id="a910e-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="a910e-112">Per altre informazioni, vedere [@ (specifica di un file di risposta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="a910e-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="a910e-113">Il compilatore elabora le opzioni passate al `vbc` ultimo comando.</span><span class="sxs-lookup"><span data-stu-id="a910e-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="a910e-114">Pertanto, qualsiasi opzione nella riga di comando sostituisce l'impostazione dell'opzione stesso nel file Vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="a910e-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a910e-115">Il `-noconfig` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a910e-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a910e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a910e-116">See also</span></span>

- [<span data-ttu-id="a910e-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a910e-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="a910e-118">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a910e-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a910e-119">@ (Specifica di un file di risposta)</span><span class="sxs-lookup"><span data-stu-id="a910e-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="a910e-120">-riferimenti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a910e-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
