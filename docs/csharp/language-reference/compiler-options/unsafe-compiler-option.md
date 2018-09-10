---
title: -unsafe (opzioni del compilatore C#)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 138c7cce83fd069f44025c57e52b2d01bcb23432
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518050"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="6f3ee-102">-unsafe (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="6f3ee-102">-unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="6f3ee-103">L'opzione del compilatore **-unsafe** consente la compilazione del codice che usa la parola chiave [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="6f3ee-103">The **-unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f3ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f3ee-104">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="6f3ee-105">Note</span><span class="sxs-lookup"><span data-stu-id="6f3ee-105">Remarks</span></span>  
 <span data-ttu-id="6f3ee-106">Per altre informazioni sul codice unsafe, vedere [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="6f3ee-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="6f3ee-107">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6f3ee-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="6f3ee-108">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-108">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="6f3ee-109">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-109">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="6f3ee-110">Selezionare la casella di controllo **Consenti codice unsafe**.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="6f3ee-111">Per aggiungere questa opzione in un file csproj</span><span class="sxs-lookup"><span data-stu-id="6f3ee-111">To add this option in a csproj file</span></span>

<span data-ttu-id="6f3ee-112">Aprire il file con estensione csproj per un progetto e aggiungere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f3ee-112">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="6f3ee-113">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-113">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f3ee-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="6f3ee-114">Example</span></span>  
 <span data-ttu-id="6f3ee-115">Compilare `in.cs` per la modalità unsafe:</span><span class="sxs-lookup"><span data-stu-id="6f3ee-115">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f3ee-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f3ee-116">See Also</span></span>  

- [<span data-ttu-id="6f3ee-117">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="6f3ee-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="6f3ee-118">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="6f3ee-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
