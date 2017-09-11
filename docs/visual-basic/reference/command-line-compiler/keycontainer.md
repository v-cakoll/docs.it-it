---
title: /keycontainer | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a783ef85e6ff2b7c6f889f809291ca8c275e709a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="keycontainer"></a><span data-ttu-id="42239-102">/keycontainer</span><span class="sxs-lookup"><span data-stu-id="42239-102">/keycontainer</span></span>
<span data-ttu-id="42239-103">Specifica il nome di un contenitore di chiavi per una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="42239-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42239-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42239-104">Syntax</span></span>  
  
```  
/keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="42239-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="42239-105">Arguments</span></span>  
  
|<span data-ttu-id="42239-106">Termine</span><span class="sxs-lookup"><span data-stu-id="42239-106">Term</span></span>|<span data-ttu-id="42239-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="42239-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="42239-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="42239-108">Required.</span></span> <span data-ttu-id="42239-109">File contenitore che contiene la chiave.</span><span class="sxs-lookup"><span data-stu-id="42239-109">Container file that contains the key.</span></span> <span data-ttu-id="42239-110">Racchiudere il nome del file tra virgolette ("") se il nome contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="42239-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42239-111">Note</span><span class="sxs-lookup"><span data-stu-id="42239-111">Remarks</span></span>  
 <span data-ttu-id="42239-112">Il compilatore crea il componente condivisibile inserendo una chiave pubblica nel manifesto dell'assembly e firmando l'assembly finale con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="42239-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="42239-113">Per generare un file di chiave, digitare `sn -k``file` nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="42239-113">To generate a key file, type `sn -k``file` at the command line.</span></span> <span data-ttu-id="42239-114">Il `-i` opzione installa la coppia di chiavi in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="42239-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="42239-115">Per altre informazioni, vedere [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span><span class="sxs-lookup"><span data-stu-id="42239-115">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
 <span data-ttu-id="42239-116">Se si compila con `/target:module`, il nome del file di chiave verrà conservato nel modulo e incorporato nell'assembly che viene creato quando si compila un assembly con [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="42239-116">If you compile with `/target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="42239-117">È possibile specificare questa opzione anche come attributo personalizzato (<xref:System.Reflection.AssemblyKeyNameAttribute>) nel codice sorgente per qualsiasi modulo di Microsoft intermediate language (MSIL).</xref:System.Reflection.AssemblyKeyNameAttribute></span><span class="sxs-lookup"><span data-stu-id="42239-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="42239-118">È inoltre possibile passare le informazioni di crittografia per il compilatore con [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span><span class="sxs-lookup"><span data-stu-id="42239-118">You can also pass your encryption information to the compiler with [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="42239-119">Utilizzare [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) se si desidera che un assembly parzialmente firmato.</span><span class="sxs-lookup"><span data-stu-id="42239-119">Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="42239-120">Vedere [creazione e uso degli assembly](https://msdn.microsoft.com/library/xwb8f617) per ulteriori informazioni su come firmare un assembly.</span><span class="sxs-lookup"><span data-stu-id="42239-120">See [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42239-121">Il `/keycontainer` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="42239-121">The `/keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42239-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="42239-122">Example</span></span>  
 <span data-ttu-id="42239-123">Il codice seguente consente di compilare file di origine `Input.vb` e specifica un contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="42239-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```  
vbc /keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="42239-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42239-124">See Also</span></span>  
 <span data-ttu-id="42239-125">[Gli assembly e Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="42239-125">[Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="42239-126"> [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="42239-126"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="42239-127"> [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="42239-127"> [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
<span data-ttu-id="42239-128"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="42239-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
