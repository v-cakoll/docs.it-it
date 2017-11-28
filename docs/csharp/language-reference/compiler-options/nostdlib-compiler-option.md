---
title: -nostdlib (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ad3ca7775512623de43c7fe6b7fe1cf481ccca87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="nostdlib-c-compiler-options"></a><span data-ttu-id="d3b05-102">/nostdlib (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="d3b05-102">/nostdlib (C# Compiler Options)</span></span>
<span data-ttu-id="d3b05-103">**/nostdlib** impedisce l'importazione di mscorlib.dll, che definisce l'intero spazio dei nomi System.</span><span class="sxs-lookup"><span data-stu-id="d3b05-103">**/nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3b05-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3b05-104">Syntax</span></span>  
  
```console  
/nostdlib[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="d3b05-105">Note</span><span class="sxs-lookup"><span data-stu-id="d3b05-105">Remarks</span></span>  
 <span data-ttu-id="d3b05-106">Usare questa opzione se si vuole definire o creare uno spazio dei nomi e oggetti System personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d3b05-106">Use this option if you want to define or create your own System namespace and objects.</span></span>  
  
 <span data-ttu-id="d3b05-107">Se non si specifica **/nostdlib**, mscorlib.dll verrà importata nel programma (equivale a specificare **/nostdlib-**).</span><span class="sxs-lookup"><span data-stu-id="d3b05-107">If you do not specify **/nostdlib**, mscorlib.dll will be imported into your program (same as specifying **/nostdlib-**).</span></span> <span data-ttu-id="d3b05-108">Specificare **/nostdlib** equivale a specificare **/nostdlib+**.</span><span class="sxs-lookup"><span data-stu-id="d3b05-108">Specifying **/nostdlib** is the same as specifying **/nostdlib+**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="d3b05-109">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d3b05-109">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="d3b05-110">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="d3b05-110">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="d3b05-111">Fare clic sulla pagina di proprietà **Compilazione** .</span><span class="sxs-lookup"><span data-stu-id="d3b05-111">Click the **Build** properties page.</span></span>  
  
3.  <span data-ttu-id="d3b05-112">Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="d3b05-112">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="d3b05-113">Modificare la proprietà **Ometti riferimenti a libreria standard (mscorlib.dll)** .</span><span class="sxs-lookup"><span data-stu-id="d3b05-113">Modify the **Do not reference mscorlib.dll** property.</span></span>  
  
 <span data-ttu-id="d3b05-114">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3b05-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3b05-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3b05-115">See Also</span></span>  
 [<span data-ttu-id="d3b05-116">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="d3b05-116">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
