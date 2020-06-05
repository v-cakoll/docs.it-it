---
title: -codepage
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 34dbf36cc79a8c4715cf6a07c57d559e14f40030
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363630"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="a3a0f-102">-tabella codici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3a0f-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="a3a0f-103">Specifica la tabella codici da usare per tutti i file del codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="a3a0f-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3a0f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3a0f-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="a3a0f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a3a0f-105">Arguments</span></span>  
  
|<span data-ttu-id="a3a0f-106">Termine</span><span class="sxs-lookup"><span data-stu-id="a3a0f-106">Term</span></span>|<span data-ttu-id="a3a0f-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="a3a0f-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="a3a0f-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a3a0f-108">Required.</span></span> <span data-ttu-id="a3a0f-109">Il compilatore usa la tabella codici specificata da `id` per interpretare la codifica dei file di origine.</span><span class="sxs-lookup"><span data-stu-id="a3a0f-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3a0f-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="a3a0f-110">Remarks</span></span>  
 <span data-ttu-id="a3a0f-111">Per compilare il codice sorgente salvato con una codifica specifica, è possibile usare `-codepage` per specificare la tabella codici da usare.</span><span class="sxs-lookup"><span data-stu-id="a3a0f-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="a3a0f-112">L' `-codepage` opzione si applica a tutti i file del codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="a3a0f-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="a3a0f-113">Per ulteriori informazioni, vedere [codifica dei caratteri nella .NET Framework](../../../standard/base-types/character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="a3a0f-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="a3a0f-114">L' `-codepage` opzione non è necessaria se i file del codice sorgente sono stati salvati usando la tabella codici ANSI corrente, Unicode o UTF-8 con una firma.</span><span class="sxs-lookup"><span data-stu-id="a3a0f-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="a3a0f-115">Per impostazione predefinita, Visual Studio Salva tutti i file del codice sorgente con la tabella codici ANSI corrente, a meno che l'utente non specifichi un'altra codifica nella finestra di dialogo **codifica** .</span><span class="sxs-lookup"><span data-stu-id="a3a0f-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="a3a0f-116">Visual Studio usa la finestra di dialogo **codifica** per aprire i file di codice sorgente salvati con una tabella codici diversa.</span><span class="sxs-lookup"><span data-stu-id="a3a0f-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3a0f-117">L' `-codepage` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a3a0f-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a0f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3a0f-118">See also</span></span>

- [<span data-ttu-id="a3a0f-119">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3a0f-119">Visual Basic Command-Line Compiler</span></span>](index.md)
