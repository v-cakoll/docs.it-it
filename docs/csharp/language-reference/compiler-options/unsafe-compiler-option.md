---
title: -unsafe (opzioni del compilatore C#)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 4a8f7d099b2cd3c1b4331c87f853b617fef505ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726533"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="daeb3-102">-unsafe (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="daeb3-102">-unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="daeb3-103">L'opzione del compilatore **-unsafe** consente la compilazione del codice che usa la parola chiave [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="daeb3-103">The **-unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daeb3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="daeb3-104">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="daeb3-105">Note</span><span class="sxs-lookup"><span data-stu-id="daeb3-105">Remarks</span></span>  
 <span data-ttu-id="daeb3-106">Per altre informazioni sul codice unsafe, vedere [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="daeb3-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="daeb3-107">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="daeb3-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="daeb3-108">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="daeb3-108">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="daeb3-109">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="daeb3-109">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="daeb3-110">Selezionare la casella di controllo **Consenti codice unsafe**.</span><span class="sxs-lookup"><span data-stu-id="daeb3-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="daeb3-111">Per aggiungere questa opzione in un file csproj</span><span class="sxs-lookup"><span data-stu-id="daeb3-111">To add this option in a csproj file</span></span>

<span data-ttu-id="daeb3-112">Aprire il file con estensione csproj per un progetto e aggiungere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="daeb3-112">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="daeb3-113">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="daeb3-113">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="daeb3-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="daeb3-114">Example</span></span>  
 <span data-ttu-id="daeb3-115">Compilare `in.cs` per la modalità unsafe:</span><span class="sxs-lookup"><span data-stu-id="daeb3-115">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="daeb3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="daeb3-116">See also</span></span>

- [<span data-ttu-id="daeb3-117">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="daeb3-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="daeb3-118">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="daeb3-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
