---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: 1666c7743f1116f86bc4457af53711cb6f1a6b7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54579823"
---
# <a name="-keycontainer"></a><span data-ttu-id="155e2-102">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="155e2-102">-keycontainer</span></span>
<span data-ttu-id="155e2-103">Specifica il nome di un contenitore di chiavi per una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="155e2-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="155e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="155e2-104">Syntax</span></span>  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="155e2-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="155e2-105">Arguments</span></span>  
  
|<span data-ttu-id="155e2-106">Termine</span><span class="sxs-lookup"><span data-stu-id="155e2-106">Term</span></span>|<span data-ttu-id="155e2-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="155e2-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="155e2-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="155e2-108">Required.</span></span> <span data-ttu-id="155e2-109">File contenitore che contiene la chiave.</span><span class="sxs-lookup"><span data-stu-id="155e2-109">Container file that contains the key.</span></span> <span data-ttu-id="155e2-110">Racchiudere il nome file racchiuso tra virgolette ("") se il nome contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="155e2-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="155e2-111">Note</span><span class="sxs-lookup"><span data-stu-id="155e2-111">Remarks</span></span>  
 <span data-ttu-id="155e2-112">Il compilatore crea il componente condivisibile inserendo una chiave pubblica nel manifesto dell'assembly e firmando l'assembly finale con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="155e2-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="155e2-113">Per generare un file di chiave, digitare `sn -k file` nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="155e2-113">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="155e2-114">Il `-i` opzione installa la coppia di chiavi in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="155e2-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="155e2-115">Per altre informazioni, vedere [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="155e2-115">For more information, see [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="155e2-116">Se esegue la compilazione con `-target:module`, il nome del file di chiave verrà mantenuto nel modulo e incorporato nell'assembly che viene creato quando si compila un assembly con [- addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="155e2-116">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="155e2-117">Questa opzione può essere specificata anche come attributo personalizzato <xref:System.Reflection.AssemblyKeyNameAttribute> nel codice sorgente di qualsiasi modulo MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="155e2-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="155e2-118">È possibile passare al compilatore le informazioni di crittografia anche tramite [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span><span class="sxs-lookup"><span data-stu-id="155e2-118">You can also pass your encryption information to the compiler with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="155e2-119">Usare [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) se si vuole un assembly con firma parziale.</span><span class="sxs-lookup"><span data-stu-id="155e2-119">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="155e2-120">Visualizzare [creazione e assembly con nome sicuro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) per altre informazioni su come firmare un assembly.</span><span class="sxs-lookup"><span data-stu-id="155e2-120">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="155e2-121">Il `-keycontainer` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="155e2-121">The `-keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="155e2-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="155e2-122">Example</span></span>  
 <span data-ttu-id="155e2-123">Il codice seguente consente di compilare file sorgente `Input.vb` e specifica un contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="155e2-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="155e2-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="155e2-124">See also</span></span>
- [<span data-ttu-id="155e2-125">Assembly e Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="155e2-125">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [<span data-ttu-id="155e2-126">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="155e2-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="155e2-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="155e2-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="155e2-128">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="155e2-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
