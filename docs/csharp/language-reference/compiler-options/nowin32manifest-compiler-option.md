---
title: -nowin32manifest (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nowin32manifest
dev_langs:
- CSharp
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8314fd661ccce968238b480b54847abf7cbece74
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="nowin32manifest-c-compiler-options"></a><span data-ttu-id="cc9b7-102">/nowin32manifest (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="cc9b7-102">/nowin32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="cc9b7-103">Usare l'opzione **/nowin32manifest** per indicare al compilatore di non incorporare un manifesto dell'applicazione nel file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="cc9b7-103">Use the **/nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc9b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc9b7-104">Syntax</span></span>  
  
```console  
/nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="cc9b7-105">Note</span><span class="sxs-lookup"><span data-stu-id="cc9b7-105">Remarks</span></span>  
 <span data-ttu-id="cc9b7-106">Quando viene usata questa opzione, l'applicazione è soggetta a virtualizzazione in Windows Vista a meno che non venga specificato un manifesto dell'applicazione in un file di risorsa Win32 file o durante una istruzione di compilazione successiva.</span><span class="sxs-lookup"><span data-stu-id="cc9b7-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="cc9b7-107">In Visual Studio impostare l'opzione nella **pagina delle proprietà dell'applicazione** selezionando l'opzione **Crea applicazione senza manifesto** nell'elenco a discesa **Manifesto**.</span><span class="sxs-lookup"><span data-stu-id="cc9b7-107">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="cc9b7-108">Per altre informazioni, vedere [Pagina Applicazione, Creazione progetti (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="cc9b7-108">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="cc9b7-109">Per altre informazioni sulla creazione di manifesti, vedere [/win32manifest (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="cc9b7-109">For more information about manifest creation, see [/win32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc9b7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc9b7-110">See Also</span></span>  
 <span data-ttu-id="cc9b7-111">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="cc9b7-111">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="cc9b7-112">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="cc9b7-112">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

