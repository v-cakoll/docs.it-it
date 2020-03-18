---
title: -keycontainer (opzioni del compilatore C#)
ms.date: 05/16/2018
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
ms.openlocfilehash: fead2d4296cfa6fb0195cb4b43f6448c0fc7e6a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970143"
---
# <a name="-keycontainer-c-compiler-options"></a><span data-ttu-id="47f5d-102">-keycontainer (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="47f5d-102">-keycontainer (C# Compiler Options)</span></span>
<span data-ttu-id="47f5d-103">Specifica il nome del contenitore di chiavi crittografiche.</span><span class="sxs-lookup"><span data-stu-id="47f5d-103">Specifies the name of the cryptographic key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47f5d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47f5d-104">Syntax</span></span>  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a><span data-ttu-id="47f5d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="47f5d-105">Arguments</span></span>  
 `string`  
 <span data-ttu-id="47f5d-106">Nome del contenitore di chiavi con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="47f5d-106">The name of the strong name key container.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47f5d-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="47f5d-107">Remarks</span></span>  
 <span data-ttu-id="47f5d-108">Quando si usa l'opzione **-keycontainer**, il compilatore crea un componente condivisibile.</span><span class="sxs-lookup"><span data-stu-id="47f5d-108">When the **-keycontainer** option is used, the compiler creates a sharable component.</span></span> <span data-ttu-id="47f5d-109">Il compilatore inserisce una chiave pubblica dal contenitore specificato nel manifesto dell'assembly e firma l'assembly finale con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="47f5d-109">The compiler inserts a public key from the specified container into the assembly manifest and signs the final assembly with the private key.</span></span> <span data-ttu-id="47f5d-110">Per generare un file di chiave, digitare `sn -k file` nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="47f5d-110">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="47f5d-111">`sn -i` installa la coppia di chiavi in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="47f5d-111">`sn -i` installs the key pair into a container.</span></span> <span data-ttu-id="47f5d-112">Questa opzione non è supportata quando il compilatore viene eseguito in CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="47f5d-112">This option is not supported when the compiler runs on CoreCLR.</span></span> <span data-ttu-id="47f5d-113">Per firmare un assembly quando si compila in CoreCLR, usare l'opzione [-keyfile](keyfile-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="47f5d-113">To sign an assembly when building on CoreCLR, use the [-keyfile](keyfile-compiler-option.md) option.</span></span>
  
 <span data-ttu-id="47f5d-114">Se si esegue la compilazione con [-target:module](./target-module-compiler-option.md), il nome del file di chiave verrà mantenuto nel modulo e incorporato nell'assembly quando il modulo verrà compilato in un assembly con [-addmodule](./addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="47f5d-114">If you compile with [-target:module](./target-module-compiler-option.md), the name of the key file is held in the module and incorporated into the assembly when you compile this module into an assembly with [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="47f5d-115">Questa opzione può essere specificata anche come attributo personalizzato <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType> nel codice sorgente di qualsiasi modulo MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="47f5d-115">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="47f5d-116">È possibile passare al compilatore le informazioni di crittografia anche tramite [-keyfile](./keyfile-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="47f5d-116">You can also pass your encryption information to the compiler with [-keyfile](./keyfile-compiler-option.md).</span></span> <span data-ttu-id="47f5d-117">Usare [-delaysign](./delaysign-compiler-option.md) se si vuole aggiungere la chiave pubblica al manifesto dell'assembly, ma si preferisce rimandare la firma dell'assembly a dopo il test di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="47f5d-117">Use [-delaysign](./delaysign-compiler-option.md) if you want the public key added to the assembly manifest but want to delay signing the assembly until it has been tested.</span></span>  
  
 <span data-ttu-id="47f5d-118">Per altre informazioni, vedere [Creazione e uso degli assembly con nome sicuro](../../../standard/assembly/create-use-strong-named.md) e [Ritardo della firma di un assembly](../../../standard/assembly/delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="47f5d-118">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="47f5d-119">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="47f5d-119">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="47f5d-120">Questa opzione del compilatore non è disponibile nell'ambiente di sviluppo di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="47f5d-120">This compiler option is not available in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="47f5d-121">È possibile accedere a questa opzione del compilatore a livello di codice con <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span><span class="sxs-lookup"><span data-stu-id="47f5d-121">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47f5d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47f5d-122">See also</span></span>

- [<span data-ttu-id="47f5d-123">Opzione -keyfile del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="47f5d-123">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="47f5d-124">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="47f5d-124">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="47f5d-125">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="47f5d-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
