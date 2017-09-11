---
title: /noconfig | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
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
ms.openlocfilehash: fe3271e4a119e0c40370a7351bb39188f4d1c8ef
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="noconfig"></a><span data-ttu-id="ea093-102">/noconfig</span><span class="sxs-lookup"><span data-stu-id="ea093-102">/noconfig</span></span>
<span data-ttu-id="ea093-103">Specifica che il compilatore non automaticamente fare riferimento a quelle di uso comune [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assembly o importazione di `System` e `Microsoft.VisualBasic` gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ea093-103">Specifies that the compiler should not automatically reference the commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea093-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea093-104">Syntax</span></span>  
  
```  
/noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="ea093-105">Note</span><span class="sxs-lookup"><span data-stu-id="ea093-105">Remarks</span></span>  
 <span data-ttu-id="ea093-106">Il `/noconfig` opzione indica al compilatore di non eseguire la compilazione con il file Vbc. rsp, che si trova nella stessa directory del file Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="ea093-106">The `/noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="ea093-107">Il file Vbc. rsp fa riferimento il diffuso [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assembly e le importazioni di `System` e `Microsoft.VisualBasic` gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ea093-107">The Vbc.rsp file references the commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="ea093-108">Il compilatore fa riferimento in modo implicito all'assembly System. dll, a meno che il `/nostdlib` opzione specificata.</span><span class="sxs-lookup"><span data-stu-id="ea093-108">The compiler implicitly references the System.dll assembly unless the `/nostdlib` option is specified.</span></span> <span data-ttu-id="ea093-109">Il `/nostdlib` opzione indica al compilatore di non compilare con Vbc. rsp o automaticamente fare riferimento all'assembly System. dll.</span><span class="sxs-lookup"><span data-stu-id="ea093-109">The `/nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea093-110">Gli assembly mscorlib. dll e Microsoft.VisualBasic.dll fa sempre riferimento.</span><span class="sxs-lookup"><span data-stu-id="ea093-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="ea093-111">È possibile modificare il file Vbc. rsp per specificare ulteriori opzioni del compilatore che devono essere incluse in ogni compilazione Vbc.exe (tranne quando si specifica il `/noconfig` opzione).</span><span class="sxs-lookup"><span data-stu-id="ea093-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `/noconfig` option).</span></span> <span data-ttu-id="ea093-112">Per altre informazioni, vedere [@ (specifica di un file di risposta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="ea093-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="ea093-113">Il compilatore elabora le opzioni passate al `vbc` ultimo comando.</span><span class="sxs-lookup"><span data-stu-id="ea093-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="ea093-114">Di conseguenza, le opzioni della riga di comando sostituiscono l'impostazione dell'opzione stesso in tale file.</span><span class="sxs-lookup"><span data-stu-id="ea093-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea093-115">Il `/noconfig` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="ea093-115">The `/noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea093-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea093-116">See Also</span></span>  
 <span data-ttu-id="ea093-117">[/nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md) </span><span class="sxs-lookup"><span data-stu-id="ea093-117">[/nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md) </span></span>  
<span data-ttu-id="ea093-118"> [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="ea093-118"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="ea093-119"> [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) </span><span class="sxs-lookup"><span data-stu-id="ea093-119"> [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) </span></span>  
<span data-ttu-id="ea093-120"> [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)</span><span class="sxs-lookup"><span data-stu-id="ea093-120"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)</span></span>
