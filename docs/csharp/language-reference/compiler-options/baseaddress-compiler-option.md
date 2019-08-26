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
ms.openlocfilehash: e96ab3ece6edc36c913a8efc0097ff9c4a1e3c22
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69607025"
---
# <a name="-baseaddress-c-compiler-options"></a><span data-ttu-id="5859a-102">-baseaddress (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="5859a-102">-baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="5859a-103">L'opzione **-baseaddress** consente di specificare l'indirizzo di base preferito in cui caricare una DLL.</span><span class="sxs-lookup"><span data-stu-id="5859a-103">The **-baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="5859a-104">Per altre informazioni su quando e perché usare questa opzione, vedere il [blog di Larry Osterman](https://blogs.msdn.microsoft.com/larryosterman/2004/07/06/why-should-i-even-bother-to-use-dlls-in-my-system/).</span><span class="sxs-lookup"><span data-stu-id="5859a-104">For more information about when and why to use this option, see [Larry Osterman's WebLog](https://blogs.msdn.microsoft.com/larryosterman/2004/07/06/why-should-i-even-bother-to-use-dlls-in-my-system/).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5859a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5859a-105">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="5859a-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5859a-106">Arguments</span></span>  
 `address`  
 <span data-ttu-id="5859a-107">Indirizzo di base per la DLL.</span><span class="sxs-lookup"><span data-stu-id="5859a-107">The base address for the DLL.</span></span> <span data-ttu-id="5859a-108">Questo indirizzo può essere specificato come numero decimale, esadecimale o ottale.</span><span class="sxs-lookup"><span data-stu-id="5859a-108">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5859a-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5859a-109">Remarks</span></span>  
 <span data-ttu-id="5859a-110">L'indirizzo di base predefinito per una DLL viene impostato dal Common Language Runtime di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5859a-110">The default base address for a DLL is set by the .NET Framework common language runtime.</span></span>  
  
 <span data-ttu-id="5859a-111">Tenere presente che la parola di ordine inferiore in questo indirizzo verrà arrotondata.</span><span class="sxs-lookup"><span data-stu-id="5859a-111">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="5859a-112">Ad esempio, se si specifica 0x11110001, il valore verrà arrotondato a 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="5859a-112">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="5859a-113">Per completare il processo di firma di una DLL, usare SN.EXE con l'opzione -R.</span><span class="sxs-lookup"><span data-stu-id="5859a-113">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="5859a-114">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5859a-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="5859a-115">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="5859a-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="5859a-116">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="5859a-116">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="5859a-117">Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="5859a-117">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="5859a-118">Modificare la proprietà **Indirizzo di base DLL**.</span><span class="sxs-lookup"><span data-stu-id="5859a-118">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="5859a-119">Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span><span class="sxs-lookup"><span data-stu-id="5859a-119">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5859a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5859a-120">See also</span></span>

- <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5859a-121">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="5859a-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="5859a-122">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="5859a-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
