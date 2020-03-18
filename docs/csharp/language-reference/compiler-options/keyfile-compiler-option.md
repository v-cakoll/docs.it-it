---
title: -keyfile (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
ms.openlocfilehash: bf271cc6b6887e930911071d4603b51daed55e61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970265"
---
# <a name="-keyfile-c-compiler-options"></a><span data-ttu-id="e2afd-102">-keyfile (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="e2afd-102">-keyfile (C# Compiler Options)</span></span>
<span data-ttu-id="e2afd-103">Specifica il nome file contenente la chiave crittografica.</span><span class="sxs-lookup"><span data-stu-id="e2afd-103">Specifies the filename containing the cryptographic key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2afd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2afd-104">Syntax</span></span>  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="e2afd-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e2afd-105">Arguments</span></span>  
  
|<span data-ttu-id="e2afd-106">Termine</span><span class="sxs-lookup"><span data-stu-id="e2afd-106">Term</span></span>|<span data-ttu-id="e2afd-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="e2afd-107">Definition</span></span>|  
|----------|----------------|  
|`file`|<span data-ttu-id="e2afd-108">Nome del file che contiene la chiave con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="e2afd-108">The name of the file containing the strong name key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2afd-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e2afd-109">Remarks</span></span>  
 <span data-ttu-id="e2afd-110">Se si usa questa opzione, il compilatore inserisce la chiave pubblica dal file specificato nel manifesto dell'assembly e quindi firma l'assembly finale con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="e2afd-110">When this option is used, the compiler inserts the public key from the specified file into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="e2afd-111">Per generare un file di chiave, digitare sn -k `file` nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="e2afd-111">To generate a key file, type sn -k `file` at the command line.</span></span>  
  
 <span data-ttu-id="e2afd-112">Se si esegue la compilazione con **-target:module**, il nome del file di chiave verrà mantenuto nel modulo e incorporato nell'assembly creato quando si compila un assembly con [-addmodule](./addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e2afd-112">If you compile with **-target:module**, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="e2afd-113">È possibile passare al compilatore le informazioni di crittografia anche tramite [-keycontainer](./keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e2afd-113">You can also pass your encryption information to the compiler with [-keycontainer](./keycontainer-compiler-option.md).</span></span> <span data-ttu-id="e2afd-114">Usare [-delaysign](./delaysign-compiler-option.md) se si vuole un assembly con firma parziale.</span><span class="sxs-lookup"><span data-stu-id="e2afd-114">Use [-delaysign](./delaysign-compiler-option.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="e2afd-115">Se nella stessa compilazione vengono specificate entrambe le opzioni -keyfile e -keycontainer (tramite opzione della riga di comando o attributo personalizzato), verrà tentato prima il contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="e2afd-115">In case both -keyfile and -keycontainer are specified (either by command line option or by custom attribute) in the same compilation, the compiler will first try the key container.</span></span> <span data-ttu-id="e2afd-116">Se l'operazione riesce, l'assembly viene firmato con le informazioni incluse nel contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="e2afd-116">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="e2afd-117">Se invece il compilatore non trova il contenitore di chiavi, effettua un tentativo con il file specificato in -keyfile.</span><span class="sxs-lookup"><span data-stu-id="e2afd-117">If the compiler does not find the key container, it will try the file specified with -keyfile.</span></span> <span data-ttu-id="e2afd-118">Se l'operazione riesce, l'assembly verrà firmato con le informazioni contenute nel file di chiave e le informazioni sulla chiave verranno installate nel contenitore di chiavi (in modo analogo a sn -i) in modo che nella compilazione successiva il contenitore di chiavi sia valido.</span><span class="sxs-lookup"><span data-stu-id="e2afd-118">If that succeeds, the assembly is signed with the information in the key file and the key information will be installed in the key container (similar to sn -i) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="e2afd-119">Si noti che un file di chiave può contenere solo la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="e2afd-119">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="e2afd-120">Per altre informazioni, vedere [Creazione e uso degli assembly con nome sicuro](../../../standard/assembly/create-use-strong-named.md) e [Ritardo della firma di un assembly](../../../standard/assembly/delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="e2afd-120">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e2afd-121">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e2afd-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="e2afd-122">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="e2afd-122">Open the **Properties** page for the project.</span></span>  
  
2. <span data-ttu-id="e2afd-123">Fare clic sulla pagina della proprietà **Firma**.</span><span class="sxs-lookup"><span data-stu-id="e2afd-123">Click the **Signing** property page.</span></span>  
  
3. <span data-ttu-id="e2afd-124">Modificare la proprietà **Scegli un file chiave con nome sicuro**.</span><span class="sxs-lookup"><span data-stu-id="e2afd-124">Modify the **Choose a strong name key file** property.</span></span>  
  
 <span data-ttu-id="e2afd-125">È possibile accedere a questa opzione del compilatore a livello di codice con <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2afd-125">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2afd-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2afd-126">See also</span></span>

- [<span data-ttu-id="e2afd-127">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="e2afd-127">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e2afd-128">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="e2afd-128">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
