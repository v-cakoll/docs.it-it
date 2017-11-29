---
title: -keyfile (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d120b325f433108cd1b01dd1c25d2a0e55da401b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="keyfile-c-compiler-options"></a><span data-ttu-id="b61c3-102">/keyfile (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="b61c3-102">/keyfile (C# Compiler Options)</span></span>
<span data-ttu-id="b61c3-103">Specifica il nome file contenente la chiave crittografica.</span><span class="sxs-lookup"><span data-stu-id="b61c3-103">Specifies the filename containing the cryptographic key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b61c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b61c3-104">Syntax</span></span>  
  
```console  
/keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="b61c3-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b61c3-105">Arguments</span></span>  
  
|<span data-ttu-id="b61c3-106">Termine</span><span class="sxs-lookup"><span data-stu-id="b61c3-106">Term</span></span>|<span data-ttu-id="b61c3-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="b61c3-107">Definition</span></span>|  
|----------|----------------|  
|`file`|<span data-ttu-id="b61c3-108">Nome del file che contiene la chiave con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="b61c3-108">The name of the file containing the strong name key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b61c3-109">Note</span><span class="sxs-lookup"><span data-stu-id="b61c3-109">Remarks</span></span>  
 <span data-ttu-id="b61c3-110">Se si usa questa opzione, il compilatore inserisce la chiave pubblica dal file specificato nel manifesto dell'assembly e quindi firma l'assembly finale con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="b61c3-110">When this option is used, the compiler inserts the public key from the specified file into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="b61c3-111">Per generare un file di chiave, digitare sn -k `file` nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b61c3-111">To generate a key file, type sn -k `file` at the command line.</span></span>  
  
 <span data-ttu-id="b61c3-112">Se si esegue la compilazione con **/target: module**, il nome del file di chiave verrà mantenuto nel modulo e incorporato nell'assembly creato quando si compila un assembly con [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="b61c3-112">If you compile with **/target:module**, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="b61c3-113">È possibile passare al compilatore le informazioni di crittografia anche tramite [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="b61c3-113">You can also pass your encryption information to the compiler with [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span> <span data-ttu-id="b61c3-114">Usare [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) se si vuole che l'assembly abbia una firma parziale.</span><span class="sxs-lookup"><span data-stu-id="b61c3-114">Use [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="b61c3-115">Se nella stessa compilazione vengono specificate sia /keyfile che /keycontainer (tramite opzione della riga di comando o attributo personalizzato), verrà tentato prima il contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="b61c3-115">In case both /keyfile and /keycontainer are specified (either by command line option or by custom attribute) in the same compilation, the compiler will first try the key container.</span></span> <span data-ttu-id="b61c3-116">Se l'operazione riesce, l'assembly viene firmato con le informazioni incluse nel contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="b61c3-116">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="b61c3-117">Se invece il compilatore non trova il contenitore di chiavi, effettua un tentativo con il file specificato in /keyfile.</span><span class="sxs-lookup"><span data-stu-id="b61c3-117">If the compiler does not find the key container, it will try the file specified with /keyfile.</span></span> <span data-ttu-id="b61c3-118">Se l'operazione riesce, l'assembly verrà firmato con le informazioni contenute nel file di chiave e le informazioni sulla chiave verranno installate nel contenitore di chiavi (in modo analogo a sn -i) in modo che nella compilazione successiva il contenitore di chiavi sia valido.</span><span class="sxs-lookup"><span data-stu-id="b61c3-118">If that succeeds, the assembly is signed with the information in the key file and the key information will be installed in the key container (similar to sn -i) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="b61c3-119">Si noti che un file di chiave può contenere solo la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="b61c3-119">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="b61c3-120">Per altre informazioni, vedere [Creazione e uso degli assembly con nome sicuro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) e [Ritardo della firma di un assembly](../../../framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="b61c3-120">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="b61c3-121">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b61c3-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="b61c3-122">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="b61c3-122">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="b61c3-123">Fare clic sulla pagina della proprietà **Firma**.</span><span class="sxs-lookup"><span data-stu-id="b61c3-123">Click the **Signing** property page.</span></span>  
  
3.  <span data-ttu-id="b61c3-124">Modificare la proprietà **Scegli un file chiave con nome sicuro**.</span><span class="sxs-lookup"><span data-stu-id="b61c3-124">Modify the **Choose a strong name key file** property.</span></span>  
  
 <span data-ttu-id="b61c3-125">È possibile accedere a questa opzione del compilatore a livello di codice con <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="b61c3-125">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b61c3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b61c3-126">See Also</span></span>  
 [<span data-ttu-id="b61c3-127">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="b61c3-127">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="b61c3-128">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="b61c3-128">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
