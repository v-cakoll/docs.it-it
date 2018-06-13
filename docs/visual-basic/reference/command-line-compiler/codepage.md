---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 383b6adae94c27efdd236de31ddfa8d16a6d4648
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648528"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="c8e89-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8e89-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="c8e89-103">Specifica la tabella codici da usare per tutti i file del codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="c8e89-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8e89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8e89-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="c8e89-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c8e89-105">Arguments</span></span>  
  
|<span data-ttu-id="c8e89-106">Termine</span><span class="sxs-lookup"><span data-stu-id="c8e89-106">Term</span></span>|<span data-ttu-id="c8e89-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="c8e89-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="c8e89-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c8e89-108">Required.</span></span> <span data-ttu-id="c8e89-109">Il compilatore Usa la tabella codici specificata da `id` per interpretare la codifica dei file di origine.</span><span class="sxs-lookup"><span data-stu-id="c8e89-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8e89-110">Note</span><span class="sxs-lookup"><span data-stu-id="c8e89-110">Remarks</span></span>  
 <span data-ttu-id="c8e89-111">Per compilare codice sorgente salvato con una codifica specifica, è possibile utilizzare `-codepage` per specificare la tabella codici da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="c8e89-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="c8e89-112">Il `-codepage` opzione si applica a tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="c8e89-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="c8e89-113">Per ulteriori informazioni, vedere [codifica dei caratteri in .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span><span class="sxs-lookup"><span data-stu-id="c8e89-113">For more information, see [Character Encoding in the .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span></span>  
  
 <span data-ttu-id="c8e89-114">Il `-codepage` opzione non è necessaria se sono stati salvati i file di codice sorgente utilizzando la tabella codici ANSI corrente, Unicode o UTF-8 con una firma.</span><span class="sxs-lookup"><span data-stu-id="c8e89-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="c8e89-115">Visual Studio Salva tutti i file del codice sorgente con la tabella codici ANSI corrente per impostazione predefinita, a meno che l'utente specifica un'altra codifica nel **codifica** finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="c8e89-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="c8e89-116">Visual Studio Usa il **codifica** finestra di dialogo per aprire i file di codice sorgente salvati con una tabella codici diversa.</span><span class="sxs-lookup"><span data-stu-id="c8e89-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8e89-117">Il `-codepage` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c8e89-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e89-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8e89-118">See Also</span></span>  
 [<span data-ttu-id="c8e89-119">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c8e89-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
