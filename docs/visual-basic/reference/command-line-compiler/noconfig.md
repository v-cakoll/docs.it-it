---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: bce2d98a8915e80cdecd7b67029b0c872cf70140
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650842"
---
# <a name="-noconfig"></a><span data-ttu-id="9c007-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="9c007-102">-noconfig</span></span>
<span data-ttu-id="9c007-103">Specifica che il compilatore non deve automaticamente fare riferimento usati comunemente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assembly o importazione di `System` e `Microsoft.VisualBasic` gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9c007-103">Specifies that the compiler should not automatically reference the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c007-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c007-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="9c007-105">Note</span><span class="sxs-lookup"><span data-stu-id="9c007-105">Remarks</span></span>  
 <span data-ttu-id="9c007-106">Il `-noconfig` opzione indica al compilatore di non eseguire la compilazione con tale file si trova nella stessa directory del file Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="9c007-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="9c007-107">Il file Vbc.rsp fa riferimento a usati comunemente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assembly e le importazioni di `System` e `Microsoft.VisualBasic` gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9c007-107">The Vbc.rsp file references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="9c007-108">Il compilatore fa riferimento in modo implicito all'assembly System. dll, a meno che il `-nostdlib` è specificata l'opzione.</span><span class="sxs-lookup"><span data-stu-id="9c007-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="9c007-109">Il `-nostdlib` opzione indica al compilatore di non eseguire la compilazione con Vbc.rsp o automaticamente riferimento all'assembly System. dll.</span><span class="sxs-lookup"><span data-stu-id="9c007-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c007-110">Gli assembly Mscorlib.dll e Microsoft.VisualBasic.dll vengono sempre fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="9c007-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="9c007-111">È possibile modificare il file Vbc.rsp per specificare ulteriori opzioni del compilatore che devono essere incluse in ogni compilazione Vbc.exe (tranne quando si specifica il `-noconfig` opzione).</span><span class="sxs-lookup"><span data-stu-id="9c007-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="9c007-112">Per altre informazioni, vedere [@ (specifica di un file di risposta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="9c007-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="9c007-113">Il compilatore elabora le opzioni passate per il `vbc` ultimo comando.</span><span class="sxs-lookup"><span data-stu-id="9c007-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="9c007-114">Pertanto, qualsiasi opzione della riga di comando sostituisce l'impostazione dell'opzione stesso in tale file.</span><span class="sxs-lookup"><span data-stu-id="9c007-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c007-115">Il `-noconfig` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="9c007-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c007-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c007-116">See Also</span></span>  
 [<span data-ttu-id="9c007-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c007-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)  
 [<span data-ttu-id="9c007-118">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9c007-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="9c007-119">@ (Specifica di un file di risposta)</span><span class="sxs-lookup"><span data-stu-id="9c007-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)  
 [<span data-ttu-id="9c007-120">-riferimenti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c007-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
