---
title: -unsafe (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /unsafe
dev_langs:
- CSharp
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.assetid: fdb77ed9-da03-45bd-bb7f-250704da1bcc
caps.latest.revision: 19
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
ms.openlocfilehash: 8f285af57d6a06d38d20b2c28e4a637fbc3ecf2c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="unsafe-c-compiler-options"></a><span data-ttu-id="f90a9-102">/unsafe (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f90a9-102">/unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="f90a9-103">L'opzione del compilatore **/unsafe** consente la compilazione del codice che usa la parola chiave [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="f90a9-103">The **/unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f90a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f90a9-104">Syntax</span></span>  
  
```console  
/unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="f90a9-105">Note</span><span class="sxs-lookup"><span data-stu-id="f90a9-105">Remarks</span></span>  
 <span data-ttu-id="f90a9-106">Per altre informazioni sul codice unsafe, vedere [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="f90a9-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f90a9-107">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f90a9-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="f90a9-108">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="f90a9-108">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="f90a9-109">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="f90a9-109">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="f90a9-110">Selezionare la casella di controllo **Consenti codice unsafe**.</span><span class="sxs-lookup"><span data-stu-id="f90a9-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
 <span data-ttu-id="f90a9-111">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="f90a9-111">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f90a9-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="f90a9-112">Example</span></span>  
 <span data-ttu-id="f90a9-113">Compilare `in.cs` per la modalità unsafe:</span><span class="sxs-lookup"><span data-stu-id="f90a9-113">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc /unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="f90a9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f90a9-114">See Also</span></span>  
 <span data-ttu-id="f90a9-115">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f90a9-115">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="f90a9-116">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="f90a9-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

