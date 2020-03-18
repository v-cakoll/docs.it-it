---
title: -nowin32manifest (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: 8820410bfdbce2f9986605f37af4d14957471126
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602710"
---
# <a name="-nowin32manifest-c-compiler-options"></a><span data-ttu-id="d3c34-102">-nowin32manifest (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="d3c34-102">-nowin32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="d3c34-103">Usare l'opzione **-nowin32manifest** per indicare al compilatore di non incorporare un manifesto dell'applicazione nel file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="d3c34-103">Use the **-nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3c34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3c34-104">Syntax</span></span>  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="d3c34-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d3c34-105">Remarks</span></span>  
 <span data-ttu-id="d3c34-106">Quando viene usata questa opzione, l'applicazione è soggetta a virtualizzazione in Windows Vista a meno che non venga specificato un manifesto dell'applicazione in un file di risorsa Win32 file o durante una istruzione di compilazione successiva.</span><span class="sxs-lookup"><span data-stu-id="d3c34-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="d3c34-107">In Visual Studio impostare l'opzione nella **pagina delle proprietà dell'applicazione** selezionando l'opzione **Crea applicazione senza manifesto** nell'elenco a discesa **Manifesto**.</span><span class="sxs-lookup"><span data-stu-id="d3c34-107">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="d3c34-108">Per altre informazioni, vedere [Pagina dell'applicazione, Progettazione progetti (C )](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="d3c34-108">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="d3c34-109">Per altre informazioni sulla creazione di manifesti, vedere [/win32manifest (opzioni del compilatore C#)](./win32manifest-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="d3c34-109">For more information about manifest creation, see [-win32manifest (C# Compiler Options)](./win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3c34-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3c34-110">See also</span></span>

- [<span data-ttu-id="d3c34-111">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="d3c34-111">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="d3c34-112">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="d3c34-112">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
