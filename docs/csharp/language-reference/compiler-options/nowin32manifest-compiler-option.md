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
ms.openlocfilehash: 3ab52d541c169850f6ae7ba7e7cfded290f890e7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43420619"
---
# <a name="-nowin32manifest-c-compiler-options"></a><span data-ttu-id="e8e99-102">-nowin32manifest (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="e8e99-102">-nowin32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="e8e99-103">Usare l'opzione **-nowin32manifest** per indicare al compilatore di non incorporare un manifesto dell'applicazione nel file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="e8e99-103">Use the **-nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8e99-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8e99-104">Syntax</span></span>  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="e8e99-105">Note</span><span class="sxs-lookup"><span data-stu-id="e8e99-105">Remarks</span></span>  
 <span data-ttu-id="e8e99-106">Quando viene usata questa opzione, l'applicazione è soggetta a virtualizzazione in Windows Vista a meno che non venga specificato un manifesto dell'applicazione in un file di risorsa Win32 file o durante una istruzione di compilazione successiva.</span><span class="sxs-lookup"><span data-stu-id="e8e99-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="e8e99-107">In Visual Studio impostare l'opzione nella **pagina delle proprietà dell'applicazione** selezionando l'opzione **Crea applicazione senza manifesto** nell'elenco a discesa **Manifesto**.</span><span class="sxs-lookup"><span data-stu-id="e8e99-107">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="e8e99-108">Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="e8e99-108">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="e8e99-109">Per altre informazioni sulla creazione di manifesti, vedere [/win32manifest (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e8e99-109">For more information about manifest creation, see [-win32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8e99-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8e99-110">See Also</span></span>  

- [<span data-ttu-id="e8e99-111">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="e8e99-111">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="e8e99-112">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="e8e99-112">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
