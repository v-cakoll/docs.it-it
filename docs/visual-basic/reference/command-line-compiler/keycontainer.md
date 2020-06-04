---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: 575b337c262fbb36a9e118aa293916c296cc2db3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408562"
---
# <a name="-keycontainer"></a><span data-ttu-id="0cd5d-102">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="0cd5d-102">-keycontainer</span></span>
<span data-ttu-id="0cd5d-103">Specifica il nome di un contenitore di chiavi per una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="0cd5d-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cd5d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0cd5d-104">Syntax</span></span>  
  
```console  
-keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="0cd5d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0cd5d-105">Arguments</span></span>  
  
|<span data-ttu-id="0cd5d-106">Termine</span><span class="sxs-lookup"><span data-stu-id="0cd5d-106">Term</span></span>|<span data-ttu-id="0cd5d-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="0cd5d-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="0cd5d-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0cd5d-108">Required.</span></span> <span data-ttu-id="0cd5d-109">File contenitore contenente la chiave.</span><span class="sxs-lookup"><span data-stu-id="0cd5d-109">Container file that contains the key.</span></span> <span data-ttu-id="0cd5d-110">Racchiudere il nome file tra virgolette ("") se il nome contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="0cd5d-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cd5d-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="0cd5d-111">Remarks</span></span>  
 <span data-ttu-id="0cd5d-112">Il compilatore crea il componente condivisibile inserendo una chiave pubblica nel manifesto dell'assembly e firmando l'assembly finale con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="0cd5d-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="0cd5d-113">Per generare un file di chiave, digitare `sn -k file` nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0cd5d-113">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="0cd5d-114">L' `-i` opzione installa la coppia di chiavi in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="0cd5d-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="0cd5d-115">Per ulteriori informazioni, vedere [sn. exe (strumento nome sicuro)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="0cd5d-115">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="0cd5d-116">Se si esegue la compilazione con `-target:module` , il nome del file di chiave viene mantenuto nel modulo e incorporato nell'assembly creato quando si compila un assembly con [-addmodule](addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="0cd5d-116">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](addmodule.md).</span></span>  
  
 <span data-ttu-id="0cd5d-117">Questa opzione può essere specificata anche come attributo personalizzato <xref:System.Reflection.AssemblyKeyNameAttribute> nel codice sorgente di qualsiasi modulo MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="0cd5d-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="0cd5d-118">È possibile passare al compilatore le informazioni di crittografia anche tramite [-keyfile](keyfile.md).</span><span class="sxs-lookup"><span data-stu-id="0cd5d-118">You can also pass your encryption information to the compiler with [-keyfile](keyfile.md).</span></span> <span data-ttu-id="0cd5d-119">Usare [-delaysign](delaysign.md) se si vuole un assembly con firma parziale.</span><span class="sxs-lookup"><span data-stu-id="0cd5d-119">Use [-delaysign](delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="0cd5d-120">Per ulteriori informazioni sulla firma di un assembly [, vedere Creazione e utilizzo di assembly con nome sicuro](../../../standard/assembly/create-use-strong-named.md) .</span><span class="sxs-lookup"><span data-stu-id="0cd5d-120">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0cd5d-121">L' `-keycontainer` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0cd5d-121">The `-keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cd5d-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="0cd5d-122">Example</span></span>  
 <span data-ttu-id="0cd5d-123">Il codice seguente compila il file `Input.vb` di origine e specifica un contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="0cd5d-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```console  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0cd5d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cd5d-124">See also</span></span>

- [<span data-ttu-id="0cd5d-125">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="0cd5d-125">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="0cd5d-126">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0cd5d-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="0cd5d-127">-filefile</span><span class="sxs-lookup"><span data-stu-id="0cd5d-127">-keyfile</span></span>](keyfile.md)
- [<span data-ttu-id="0cd5d-128">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="0cd5d-128">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
