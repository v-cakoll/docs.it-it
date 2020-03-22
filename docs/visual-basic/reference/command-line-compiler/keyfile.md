---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: cffc3c5f0ff3dd48ca2c74bde346a967b209dc5f
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266742"
---
# <a name="-keyfile"></a><span data-ttu-id="59c02-102">-keyfile</span><span class="sxs-lookup"><span data-stu-id="59c02-102">-keyfile</span></span>
<span data-ttu-id="59c02-103">Specifica un file contenente una chiave o una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="59c02-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59c02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59c02-104">Syntax</span></span>  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="59c02-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="59c02-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="59c02-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="59c02-106">Required.</span></span> <span data-ttu-id="59c02-107">File che contiene la chiave.</span><span class="sxs-lookup"><span data-stu-id="59c02-107">File that contains the key.</span></span> <span data-ttu-id="59c02-108">Se il nome del file contiene uno spazio, racchiuderlo tra virgolette (" ").</span><span class="sxs-lookup"><span data-stu-id="59c02-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59c02-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="59c02-109">Remarks</span></span>  
 <span data-ttu-id="59c02-110">Il compilatore inserisce la chiave pubblica nel manifesto dell'assembly e quindi firma l'assembly finale con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="59c02-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="59c02-111">Per generare un file di chiave, digitare `sn -k file` nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="59c02-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="59c02-112">Per ulteriori informazioni, vedere [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="59c02-112">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="59c02-113">Se si `-target:module`esegue la compilazione con , il nome del file di chiave viene mantenuto nel modulo e incorporato nell'assembly creato quando si compila un assembly con [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="59c02-113">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="59c02-114">È possibile passare al compilatore le informazioni di crittografia anche tramite [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="59c02-114">You can also pass your encryption information to the compiler with [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="59c02-115">Usare [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) se si vuole un assembly con firma parziale.</span><span class="sxs-lookup"><span data-stu-id="59c02-115">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="59c02-116">È inoltre possibile specificare questa<xref:System.Reflection.AssemblyKeyFileAttribute>opzione come attributo personalizzato ( ) nel codice sorgente per qualsiasi modulo di linguaggio intermedio Microsoft.You can also specify this option as a custom attribute ( ) in the source code for any Microsoft intermediate language module.</span><span class="sxs-lookup"><span data-stu-id="59c02-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="59c02-117">Nel caso `-keyfile` in cui entrambi e [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) vengono specificati (dall'opzione della riga di comando o dall'attributo personalizzato) nella stessa compilazione, il compilatore tenta innanzitutto il contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="59c02-117">In case both `-keyfile` and [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="59c02-118">Se l'operazione riesce, l'assembly viene firmato con le informazioni incluse nel contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="59c02-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="59c02-119">Se il compilatore non trova il contenitore `-keyfile`di chiavi, tenta il file specificato con .</span><span class="sxs-lookup"><span data-stu-id="59c02-119">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="59c02-120">Se l'operazione riesce, l'assembly viene firmato con le informazioni nel file di `sn -i`chiave e le informazioni sulla chiave vengono installate nel contenitore di chiavi (simile a ) in modo che alla compilazione successiva il contenitore di chiavi sia valido.</span><span class="sxs-lookup"><span data-stu-id="59c02-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="59c02-121">Si noti che un file di chiave può contenere solo la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="59c02-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="59c02-122">Per ulteriori informazioni sulla firma di un assembly, vedere Creazione e utilizzo di [assembly con nome sicuro.](../../../standard/assembly/create-use-strong-named.md)</span><span class="sxs-lookup"><span data-stu-id="59c02-122">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59c02-123">L'opzione `-keyfile` non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="59c02-123">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="59c02-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="59c02-124">Example</span></span>

<span data-ttu-id="59c02-125">Il codice seguente compila `Input.vb` il file di origine e specifica un file di chiave.</span><span class="sxs-lookup"><span data-stu-id="59c02-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a><span data-ttu-id="59c02-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59c02-126">See also</span></span>

- [<span data-ttu-id="59c02-127">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="59c02-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="59c02-128">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="59c02-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="59c02-129">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59c02-129">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="59c02-130">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="59c02-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
