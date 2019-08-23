---
title: -tabella codici (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 3a5974a910303f847679f18c23e00cfaa00caa2c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962606"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="fe3b2-102">-tabella codici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe3b2-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="fe3b2-103">Specifica la tabella codici da usare per tutti i file del codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="fe3b2-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe3b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe3b2-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="fe3b2-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="fe3b2-105">Arguments</span></span>  
  
|<span data-ttu-id="fe3b2-106">Termine</span><span class="sxs-lookup"><span data-stu-id="fe3b2-106">Term</span></span>|<span data-ttu-id="fe3b2-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="fe3b2-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="fe3b2-108">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="fe3b2-108">Required.</span></span> <span data-ttu-id="fe3b2-109">Il compilatore usa la tabella codici specificata da `id` per interpretare la codifica dei file di origine.</span><span class="sxs-lookup"><span data-stu-id="fe3b2-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe3b2-110">Note</span><span class="sxs-lookup"><span data-stu-id="fe3b2-110">Remarks</span></span>  
 <span data-ttu-id="fe3b2-111">Per compilare il codice sorgente salvato con una codifica specifica, è possibile `-codepage` usare per specificare la tabella codici da usare.</span><span class="sxs-lookup"><span data-stu-id="fe3b2-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="fe3b2-112">L' `-codepage` opzione si applica a tutti i file del codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="fe3b2-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="fe3b2-113">Per ulteriori informazioni, vedere [codifica dei caratteri nella .NET Framework](../../../standard/base-types/character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="fe3b2-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="fe3b2-114">L' `-codepage` opzione non è necessaria se i file del codice sorgente sono stati salvati usando la tabella codici ANSI corrente, Unicode o UTF-8 con una firma.</span><span class="sxs-lookup"><span data-stu-id="fe3b2-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="fe3b2-115">Per impostazione predefinita, Visual Studio Salva tutti i file del codice sorgente con la tabella codici ANSI corrente, a meno che l'utente non specifichi un'altra codifica nella finestra di dialogo **codifica** .</span><span class="sxs-lookup"><span data-stu-id="fe3b2-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="fe3b2-116">Visual Studio usa la finestra di dialogo **codifica** per aprire i file di codice sorgente salvati con una tabella codici diversa.</span><span class="sxs-lookup"><span data-stu-id="fe3b2-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe3b2-117">L' `-codepage` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="fe3b2-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe3b2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe3b2-118">See also</span></span>

- [<span data-ttu-id="fe3b2-119">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fe3b2-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
