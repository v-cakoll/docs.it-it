---
title: -baseaddress (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /dllbase
dev_langs:
- CSharp
helpviewer_keywords:
- baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: 18
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
ms.openlocfilehash: 91193ae794957b5045a225614d6322e86d18d459
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="baseaddress-c-compiler-options"></a><span data-ttu-id="77f6d-102">/baseaddress (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="77f6d-102">/baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="77f6d-103">L'opzione **/baseaddress** specifica l'indirizzo di base preferenziale in cui caricare una DLL.</span><span class="sxs-lookup"><span data-stu-id="77f6d-103">The **/baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="77f6d-104">Per altre informazioni su quando e perché usare questa opzione, vedere [Improving Application Startup Time](http://go.microsoft.com/fwlink/?LinkId=107043) (Miglioramento dei tempi di avvio dell'applicazione) e il [blog di Larry Osterman](http://go.microsoft.com/fwlink/?LinkId=107044).</span><span class="sxs-lookup"><span data-stu-id="77f6d-104">For more information about when and why to use this option, see [Improving Application Startup Time](http://go.microsoft.com/fwlink/?LinkId=107043) and [Larry Osterman's WebLog](http://go.microsoft.com/fwlink/?LinkId=107044).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77f6d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77f6d-105">Syntax</span></span>  
  
```console  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="77f6d-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="77f6d-106">Arguments</span></span>  
 `address`  
 <span data-ttu-id="77f6d-107">Indirizzo di base per la DLL.</span><span class="sxs-lookup"><span data-stu-id="77f6d-107">The base address for the DLL.</span></span> <span data-ttu-id="77f6d-108">Questo indirizzo può essere specificato come numero decimale, esadecimale o ottale.</span><span class="sxs-lookup"><span data-stu-id="77f6d-108">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77f6d-109">Note</span><span class="sxs-lookup"><span data-stu-id="77f6d-109">Remarks</span></span>  
 <span data-ttu-id="77f6d-110">L'indirizzo di base predefinito per una DLL viene impostato dal Common Language Runtime di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="77f6d-110">The default base address for a DLL is set by the .NET Framework common language runtime.</span></span>  
  
 <span data-ttu-id="77f6d-111">Tenere presente che la parola di ordine inferiore in questo indirizzo verrà arrotondata.</span><span class="sxs-lookup"><span data-stu-id="77f6d-111">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="77f6d-112">Ad esempio, se si specifica 0x11110001, il valore verrà arrotondato a 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="77f6d-112">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="77f6d-113">Per completare il processo di firma di una DLL, usare SN.EXE con l'opzione -R.</span><span class="sxs-lookup"><span data-stu-id="77f6d-113">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="77f6d-114">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="77f6d-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="77f6d-115">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="77f6d-115">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="77f6d-116">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="77f6d-116">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="77f6d-117">Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="77f6d-117">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="77f6d-118">Modificare la proprietà **Indirizzo di base DLL**.</span><span class="sxs-lookup"><span data-stu-id="77f6d-118">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="77f6d-119">Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span><span class="sxs-lookup"><span data-stu-id="77f6d-119">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77f6d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77f6d-120">See Also</span></span>  
 <span data-ttu-id="77f6d-121"><xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="77f6d-121"><xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="77f6d-122">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="77f6d-122">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="77f6d-123">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="77f6d-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

