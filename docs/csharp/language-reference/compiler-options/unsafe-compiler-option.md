---
title: -unsafe (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.assetid: fdb77ed9-da03-45bd-bb7f-250704da1bcc
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 146977522b400418a26f6a83e1a0ccdca8675bf9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="unsafe-c-compiler-options"></a><span data-ttu-id="0b083-102">/unsafe (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="0b083-102">/unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="0b083-103">L'opzione del compilatore **/unsafe** consente la compilazione del codice che usa la parola chiave [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="0b083-103">The **/unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b083-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b083-104">Syntax</span></span>  
  
```console  
/unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="0b083-105">Note</span><span class="sxs-lookup"><span data-stu-id="0b083-105">Remarks</span></span>  
 <span data-ttu-id="0b083-106">Per altre informazioni sul codice unsafe, vedere [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="0b083-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="0b083-107">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0b083-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="0b083-108">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="0b083-108">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="0b083-109">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="0b083-109">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="0b083-110">Selezionare la casella di controllo **Consenti codice unsafe**.</span><span class="sxs-lookup"><span data-stu-id="0b083-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
 <span data-ttu-id="0b083-111">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="0b083-111">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b083-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b083-112">Example</span></span>  
 <span data-ttu-id="0b083-113">Compilare `in.cs` per la modalità unsafe:</span><span class="sxs-lookup"><span data-stu-id="0b083-113">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc /unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b083-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b083-114">See Also</span></span>  
 [<span data-ttu-id="0b083-115">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="0b083-115">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="0b083-116">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="0b083-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
