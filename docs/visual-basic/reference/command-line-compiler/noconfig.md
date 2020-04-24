---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: c57ed1699d110959e9faf3dc3d43bcc200851c1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005441"
---
# <a name="-noconfig"></a><span data-ttu-id="07efb-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="07efb-102">-noconfig</span></span>
<span data-ttu-id="07efb-103">Specifica che il compilatore non deve fare riferimento automaticamente agli assembly .NET Framework di uso comune o `System` importare `Microsoft.VisualBasic` gli spazi dei nomi e.</span><span class="sxs-lookup"><span data-stu-id="07efb-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07efb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07efb-104">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="07efb-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="07efb-105">Remarks</span></span>  
 <span data-ttu-id="07efb-106">L' `-noconfig` opzione indica al compilatore di non eseguire la compilazione con il file Vbc. rsp, che si trova nella stessa directory del file Vbc. exe.</span><span class="sxs-lookup"><span data-stu-id="07efb-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="07efb-107">Il file Vbc. rsp fa riferimento agli assembly di .NET Framework di uso comune `System` e `Microsoft.VisualBasic` importa gli spazi dei nomi e.</span><span class="sxs-lookup"><span data-stu-id="07efb-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="07efb-108">Il compilatore fa riferimento in modo implicito all'assembly System. dll `-nostdlib` , a meno che non venga specificata l'opzione.</span><span class="sxs-lookup"><span data-stu-id="07efb-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="07efb-109">L' `-nostdlib` opzione indica al compilatore di non eseguire la compilazione con Vbc. rsp o di fare automaticamente riferimento all'assembly System. dll.</span><span class="sxs-lookup"><span data-stu-id="07efb-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07efb-110">Viene sempre fatto riferimento agli assembly mscorlib. dll e Microsoft. VisualBasic. dll.</span><span class="sxs-lookup"><span data-stu-id="07efb-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="07efb-111">È possibile modificare il file Vbc. rsp per specificare altre opzioni del compilatore da includere in ogni compilazione vbc. exe, tranne quando si specifica l' `-noconfig` opzione.</span><span class="sxs-lookup"><span data-stu-id="07efb-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="07efb-112">Per ulteriori informazioni, vedere [@ (specificare il file di risposta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="07efb-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="07efb-113">Il compilatore elabora le opzioni passate al `vbc` comando per ultimo.</span><span class="sxs-lookup"><span data-stu-id="07efb-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="07efb-114">Pertanto, qualsiasi opzione nella riga di comando esegue l'override dell'impostazione della stessa opzione nel file Vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="07efb-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07efb-115">L' `-noconfig` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="07efb-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07efb-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="07efb-116">See also</span></span>

- [<span data-ttu-id="07efb-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07efb-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="07efb-118">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="07efb-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="07efb-119">@ (Specifica di un file di risposta)</span><span class="sxs-lookup"><span data-stu-id="07efb-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="07efb-120">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07efb-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
