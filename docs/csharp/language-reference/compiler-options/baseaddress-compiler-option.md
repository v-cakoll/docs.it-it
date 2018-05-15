---
title: -baseaddress (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
ms.openlocfilehash: 3759067731902ba4f460ff850fb5e81f2e544e99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-baseaddress-c-compiler-options"></a><span data-ttu-id="97f6b-102">-baseaddress (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="97f6b-102">-baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="97f6b-103">L'opzione **-baseaddress** consente di specificare l'indirizzo di base preferito in cui caricare una DLL.</span><span class="sxs-lookup"><span data-stu-id="97f6b-103">The **-baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="97f6b-104">Per altre informazioni su quando e perché usare questa opzione, vedere il [blog di Larry Osterman](https://blogs.msdn.microsoft.com/larryosterman/2004/07/06/why-should-i-even-bother-to-use-dlls-in-my-system/).</span><span class="sxs-lookup"><span data-stu-id="97f6b-104">For more information about when and why to use this option, see [Larry Osterman's WebLog](https://blogs.msdn.microsoft.com/larryosterman/2004/07/06/why-should-i-even-bother-to-use-dlls-in-my-system/).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f6b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97f6b-105">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="97f6b-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="97f6b-106">Arguments</span></span>  
 `address`  
 <span data-ttu-id="97f6b-107">Indirizzo di base per la DLL.</span><span class="sxs-lookup"><span data-stu-id="97f6b-107">The base address for the DLL.</span></span> <span data-ttu-id="97f6b-108">Questo indirizzo può essere specificato come numero decimale, esadecimale o ottale.</span><span class="sxs-lookup"><span data-stu-id="97f6b-108">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97f6b-109">Note</span><span class="sxs-lookup"><span data-stu-id="97f6b-109">Remarks</span></span>  
 <span data-ttu-id="97f6b-110">L'indirizzo di base predefinito per una DLL viene impostato dal Common Language Runtime di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97f6b-110">The default base address for a DLL is set by the .NET Framework common language runtime.</span></span>  
  
 <span data-ttu-id="97f6b-111">Tenere presente che la parola di ordine inferiore in questo indirizzo verrà arrotondata.</span><span class="sxs-lookup"><span data-stu-id="97f6b-111">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="97f6b-112">Ad esempio, se si specifica 0x11110001, il valore verrà arrotondato a 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="97f6b-112">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="97f6b-113">Per completare il processo di firma di una DLL, usare SN.EXE con l'opzione -R.</span><span class="sxs-lookup"><span data-stu-id="97f6b-113">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="97f6b-114">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="97f6b-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="97f6b-115">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="97f6b-115">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="97f6b-116">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="97f6b-116">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="97f6b-117">Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="97f6b-117">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="97f6b-118">Modificare la proprietà **Indirizzo di base DLL**.</span><span class="sxs-lookup"><span data-stu-id="97f6b-118">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="97f6b-119">Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span><span class="sxs-lookup"><span data-stu-id="97f6b-119">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f6b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97f6b-120">See Also</span></span>  
 <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="97f6b-121">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="97f6b-121">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="97f6b-122">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="97f6b-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
