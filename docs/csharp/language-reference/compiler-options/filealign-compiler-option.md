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
ms.openlocfilehash: aed8b412ea1580f7dfa4f87333598d76a85b5e64
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69603018"
---
# <a name="-filealign-c-compiler-options"></a><span data-ttu-id="6fb3b-102">-filealign (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="6fb3b-102">-filealign (C# Compiler Options)</span></span>
<span data-ttu-id="6fb3b-103">L'opzione **-filealign** consente di specificare le dimensioni delle sezioni nel file di output.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-103">The **-filealign** option lets you specify the size of sections in your output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fb3b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fb3b-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="6fb3b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6fb3b-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="6fb3b-106">Valore che specifica le dimensioni delle sezioni nel file di output.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-106">A value that specifies the size of sections in the output file.</span></span> <span data-ttu-id="6fb3b-107">I valori validi sono 512, 1024, 2048, 4096 e 8192.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-107">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="6fb3b-108">I valori sono in byte.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-108">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fb3b-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6fb3b-109">Remarks</span></span>  
 <span data-ttu-id="6fb3b-110">Ogni sezione sarà allineata in base a un limite corrispondente multiplo del valore **-filealign**.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-110">Each section will be aligned on a boundary that is a multiple of the **-filealign** value.</span></span> <span data-ttu-id="6fb3b-111">Non vi è alcun valore predefinito fisso.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-111">There is no fixed default.</span></span> <span data-ttu-id="6fb3b-112">Se **-filealign** non è specificato, Common Language Runtime sceglie un valore predefinito in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-112">If **-filealign** is not specified, the common language runtime picks a default at compile time.</span></span>  
  
 <span data-ttu-id="6fb3b-113">Specificando le dimensioni della sezione, si influisce sulla dimensione del file di output.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-113">By specifying the section size, you affect the size of the output file.</span></span> <span data-ttu-id="6fb3b-114">La modifica delle dimensioni della sezione può essere utile per i programmi che verranno eseguiti su dispositivi di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-114">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
 <span data-ttu-id="6fb3b-115">Usare [DUMPBIN](/cpp/build/reference/dumpbin-options) per visualizzare informazioni sulle sezioni nel file di output.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-115">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) to see information about sections in your output file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="6fb3b-116">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6fb3b-116">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="6fb3b-117">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-117">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="6fb3b-118">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-118">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="6fb3b-119">Fare clic sul pulsante **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-119">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="6fb3b-120">Modificare la proprietà **Allineamento file**.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-120">Modify the **File Alignment** property.</span></span>  
  
 <span data-ttu-id="6fb3b-121">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="6fb3b-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fb3b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fb3b-122">See also</span></span>

- [<span data-ttu-id="6fb3b-123">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="6fb3b-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="6fb3b-124">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="6fb3b-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
