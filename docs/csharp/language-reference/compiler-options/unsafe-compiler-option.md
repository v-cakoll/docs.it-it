---
title: -unsafe (opzioni del compilatore C#)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 146299fda103567b111c66400c17edf36addd843
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "65877985"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="5453a-102">-unsafe (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="5453a-102">-unsafe (C# Compiler Options)</span></span>

<span data-ttu-id="5453a-103">L'opzione del compilatore **-unsafe** consente la compilazione del codice che usa la parola chiave [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="5453a-103">The **-unsafe** compiler option allows code that uses the [unsafe](../keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5453a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5453a-104">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="5453a-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5453a-105">Remarks</span></span>

<span data-ttu-id="5453a-106">Per altre informazioni sul codice unsafe, vedere [Codice unsafe e puntatori](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="5453a-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="5453a-107">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5453a-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="5453a-108">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="5453a-108">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="5453a-109">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="5453a-109">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="5453a-110">Selezionare la casella di controllo **Consenti codice unsafe**.</span><span class="sxs-lookup"><span data-stu-id="5453a-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="5453a-111">Per aggiungere questa opzione in un file csproj</span><span class="sxs-lookup"><span data-stu-id="5453a-111">To add this option in a csproj file</span></span>

<span data-ttu-id="5453a-112">Aprire il file con estensione csproj per un progetto e aggiungere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5453a-112">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="5453a-113">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="5453a-113">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5453a-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="5453a-114">Example</span></span>

<span data-ttu-id="5453a-115">Compilare `in.cs` per la modalità unsafe:</span><span class="sxs-lookup"><span data-stu-id="5453a-115">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="5453a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5453a-116">See also</span></span>

- [<span data-ttu-id="5453a-117">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="5453a-117">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="5453a-118">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="5453a-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
