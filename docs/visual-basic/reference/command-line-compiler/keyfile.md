---
title: /keyfile
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b7f41b659399ae5a12663d4e359c02606bb6f952
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2017
---
# <a name="keyfile"></a><span data-ttu-id="6fd94-102">/keyfile</span><span class="sxs-lookup"><span data-stu-id="6fd94-102">/keyfile</span></span>
<span data-ttu-id="6fd94-103">Specifica un file contenente una chiave o una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="6fd94-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fd94-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fd94-104">Syntax</span></span>  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="6fd94-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6fd94-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="6fd94-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6fd94-106">Required.</span></span> <span data-ttu-id="6fd94-107">File che contiene la chiave.</span><span class="sxs-lookup"><span data-stu-id="6fd94-107">File that contains the key.</span></span> <span data-ttu-id="6fd94-108">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="6fd94-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fd94-109">Note</span><span class="sxs-lookup"><span data-stu-id="6fd94-109">Remarks</span></span>  
 <span data-ttu-id="6fd94-110">Il compilatore inserisce la chiave pubblica nel manifesto dell'assembly e l'assembly finale verrà firmato con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="6fd94-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="6fd94-111">Per generare un file di chiave, digitare `sn -k file` nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6fd94-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="6fd94-112">Per altre informazioni, vedere [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span><span class="sxs-lookup"><span data-stu-id="6fd94-112">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
 <span data-ttu-id="6fd94-113">Se si compila con `/target:module`, il nome del file di chiave verrà conservato nel modulo e incorporato nell'assembly che viene creato quando si compila un assembly con [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="6fd94-113">If you compile with `/target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="6fd94-114">È possibile passare al compilatore le informazioni di crittografia anche tramite [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="6fd94-114">You can also pass your encryption information to the compiler with [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="6fd94-115">Usare [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) se si vuole che l'assembly abbia una firma parziale.</span><span class="sxs-lookup"><span data-stu-id="6fd94-115">Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="6fd94-116">È possibile specificare questa opzione anche come attributo personalizzato (<xref:System.Reflection.AssemblyKeyFileAttribute>) nel codice sorgente di qualsiasi modulo di Microsoft intermediate language.</span><span class="sxs-lookup"><span data-stu-id="6fd94-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="6fd94-117">In caso `/keyfile` e [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) vengono specificati (tramite opzione della riga di comando o un attributo personalizzato) nella stessa compilazione, il compilatore tenta innanzitutto il contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="6fd94-117">In case both `/keyfile` and [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="6fd94-118">Se l'operazione riesce, l'assembly viene firmato con le informazioni incluse nel contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="6fd94-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="6fd94-119">Se il compilatore non trova il contenitore di chiavi, prova nuovamente con il file specificato con `/keyfile`.</span><span class="sxs-lookup"><span data-stu-id="6fd94-119">If the compiler does not find the key container, it tries the file specified with `/keyfile`.</span></span> <span data-ttu-id="6fd94-120">Se l'esito è positivo, l'assembly è firmato con le informazioni nel file di chiave e le informazioni sulla chiave è installati nel contenitore di chiavi (simile a `sn -i`) in modo che alla successiva compilazione, il contenitore di chiavi valido.</span><span class="sxs-lookup"><span data-stu-id="6fd94-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="6fd94-121">Si noti che un file di chiave può contenere solo la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="6fd94-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="6fd94-122">Vedere [creazione e uso degli assembly](../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) per ulteriori informazioni su come firmare un assembly.</span><span class="sxs-lookup"><span data-stu-id="6fd94-122">See [Creating and Using Strong-Named Assemblies](../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fd94-123">Il `/keyfile` opzione non è disponibile all'interno di [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] ambiente di sviluppo; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6fd94-123">The `/keyfile` option is not available from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fd94-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fd94-124">Example</span></span>  
 <span data-ttu-id="6fd94-125">Il codice seguente compila i file di origine `Input.vb` e specifica un file di chiave.</span><span class="sxs-lookup"><span data-stu-id="6fd94-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6fd94-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fd94-126">See Also</span></span>  
 [<span data-ttu-id="6fd94-127">Assembly e Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="6fd94-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="6fd94-128">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6fd94-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="6fd94-129">/Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fd94-129">/reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="6fd94-130">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="6fd94-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
