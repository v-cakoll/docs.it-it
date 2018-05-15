---
title: -filealign (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /filealign
helpviewer_keywords:
- /alignment compiler option [C#]
- filealign compiler option [C#]
- -filealign compiler option [C#]
- /sections compiler option [C#]
- alignment compiler option [C#]
- sections compiler option [C#]
- -sections compiler option [C#]
- /filealign compiler option [C#]
- file sharing [C#]
- -alignment compiler option [C#]
- section alignment [C#]
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
ms.openlocfilehash: d51dd0d63bec251d879ffb5e59ce5f7edaf136b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-filealign-c-compiler-options"></a><span data-ttu-id="6ec68-102">-filealign (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="6ec68-102">-filealign (C# Compiler Options)</span></span>
<span data-ttu-id="6ec68-103">L'opzione **-filealign** consente di specificare le dimensioni delle sezioni nel file di output.</span><span class="sxs-lookup"><span data-stu-id="6ec68-103">The **-filealign** option lets you specify the size of sections in your output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ec68-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ec68-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="6ec68-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6ec68-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="6ec68-106">Valore che specifica le dimensioni delle sezioni nel file di output.</span><span class="sxs-lookup"><span data-stu-id="6ec68-106">A value that specifies the size of sections in the output file.</span></span> <span data-ttu-id="6ec68-107">I valori validi sono 512, 1024, 2048, 4096 e 8192.</span><span class="sxs-lookup"><span data-stu-id="6ec68-107">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="6ec68-108">I valori sono in byte.</span><span class="sxs-lookup"><span data-stu-id="6ec68-108">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ec68-109">Note</span><span class="sxs-lookup"><span data-stu-id="6ec68-109">Remarks</span></span>  
 <span data-ttu-id="6ec68-110">Ogni sezione sarà allineata in base a un limite corrispondente multiplo del valore **-filealign**.</span><span class="sxs-lookup"><span data-stu-id="6ec68-110">Each section will be aligned on a boundary that is a multiple of the **-filealign** value.</span></span> <span data-ttu-id="6ec68-111">Non vi è alcun valore predefinito fisso.</span><span class="sxs-lookup"><span data-stu-id="6ec68-111">There is no fixed default.</span></span> <span data-ttu-id="6ec68-112">Se **-filealign** non è specificato, Common Language Runtime sceglie un valore predefinito in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6ec68-112">If **-filealign** is not specified, the common language runtime picks a default at compile time.</span></span>  
  
 <span data-ttu-id="6ec68-113">Specificando le dimensioni della sezione, si influisce sulla dimensione del file di output.</span><span class="sxs-lookup"><span data-stu-id="6ec68-113">By specifying the section size, you affect the size of the output file.</span></span> <span data-ttu-id="6ec68-114">La modifica delle dimensioni della sezione può essere utile per i programmi che verranno eseguiti su dispositivi di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="6ec68-114">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
 <span data-ttu-id="6ec68-115">Usare [DUMPBIN](/cpp/build/reference/dumpbin-options) per visualizzare informazioni sulle sezioni nel file di output.</span><span class="sxs-lookup"><span data-stu-id="6ec68-115">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) to see information about sections in your output file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="6ec68-116">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6ec68-116">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="6ec68-117">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="6ec68-117">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="6ec68-118">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="6ec68-118">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="6ec68-119">Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="6ec68-119">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="6ec68-120">Modificare la proprietà **Allineamento file**.</span><span class="sxs-lookup"><span data-stu-id="6ec68-120">Modify the **File Alignment** property.</span></span>  
  
 <span data-ttu-id="6ec68-121">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ec68-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec68-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ec68-122">See Also</span></span>  
 [<span data-ttu-id="6ec68-123">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="6ec68-123">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="6ec68-124">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="6ec68-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
