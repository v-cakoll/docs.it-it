---
title: Ritardo della firma di un assembly
ms.date: 07/31/2017
ms.prod: .net-framework
ms.technology: dotnet-bcl
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- deferring assembly signing
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, delaying assembly signing
- partial assembly signing
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 08f0f48a71415878cd24640272a41de4c0a5ade6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="delay-signing-an-assembly"></a><span data-ttu-id="e894a-102">Ritardo della firma di un assembly</span><span class="sxs-lookup"><span data-stu-id="e894a-102">Delay Signing an Assembly</span></span>
<span data-ttu-id="e894a-103">È possibile che in un'organizzazione venga usata una coppia di chiavi sottoposta a una rigorosa sicurezza e quindi non accessibile giornalmente agli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="e894a-103">An organization can have a closely guarded key pair that developers do not have access to on a daily basis.</span></span> <span data-ttu-id="e894a-104">La chiave pubblica è spesso disponibile, ma l'accesso alla chiave privata è consentito solo ad alcune persone.</span><span class="sxs-lookup"><span data-stu-id="e894a-104">The public key is often available, but access to the private key is restricted to only a few individuals.</span></span> <span data-ttu-id="e894a-105">Quando si sviluppano assembly con nome sicuro, in ogni assembly che fa riferimento all'assembly con nome sicuro di destinazione è contenuto un token della chiave pubblica usata per assegnare un nome sicuro all'assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e894a-105">When developing assemblies with strong names, each assembly that references the strong-named target assembly contains the token of the public key used to give the target assembly a strong name.</span></span> <span data-ttu-id="e894a-106">È quindi necessario che la chiave pubblica risulti disponibile durante il processo di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="e894a-106">This requires that the public key be available during the development process.</span></span>  
  
 <span data-ttu-id="e894a-107">È possibile usare il ritardo della firma o la firma parziale in fase di compilazione per riservare nel file eseguibile trasportabile (PE, Portable Executable) lo spazio per la firma con nome sicuro, posticipando la firma effettiva a una fase successiva, solitamente prima della consegna dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e894a-107">You can use delayed or partial signing at build time to reserve space in the portable executable (PE) file for the strong name signature, but defer the actual signing until some later stage (typically just before shipping the assembly).</span></span>  
  
 <span data-ttu-id="e894a-108">I passaggi seguenti illustrano il processo che consente di ritardare la firma di un assembly:</span><span class="sxs-lookup"><span data-stu-id="e894a-108">The following steps outline the process to delay sign an assembly:</span></span>  
  
1.  <span data-ttu-id="e894a-109">Ottenere la parte pubblica della coppia di chiavi dall'organizzazione da cui verrà effettivamente apposta la firma.</span><span class="sxs-lookup"><span data-stu-id="e894a-109">Obtain the public key portion of the key pair from the organization that will do the eventual signing.</span></span> <span data-ttu-id="e894a-110">Tale chiave si presenta solitamente sotto forma di file con estensione snk. È possibile creare questo file tramite lo [strumento Nome sicuro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) disponibile in [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e894a-110">Typically this key is in the form of an .snk file, which can be created using the [Strong Name tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>  
  
2.  <span data-ttu-id="e894a-111">Apporre annotazioni al codice sorgente per l'assembly usando due attributi personalizzati da <xref:System.Reflection>:</span><span class="sxs-lookup"><span data-stu-id="e894a-111">Annotate the source code for the assembly with two custom attributes from <xref:System.Reflection>:</span></span>  
  
    -   <span data-ttu-id="e894a-112"><xref:System.Reflection.AssemblyKeyFileAttribute>, che consente di passare il nome del file contenente la chiave pubblica come parametro al costruttore.</span><span class="sxs-lookup"><span data-stu-id="e894a-112"><xref:System.Reflection.AssemblyKeyFileAttribute>, which passes the name of the file containing the public key as a parameter to its constructor.</span></span>  
  
    -   <span data-ttu-id="e894a-113"><xref:System.Reflection.AssemblyDelaySignAttribute>, che indica che si sta usando il ritardo della firma passando **true** come parametro al costruttore.</span><span class="sxs-lookup"><span data-stu-id="e894a-113"><xref:System.Reflection.AssemblyDelaySignAttribute>, which indicates that delay signing is being used by passing **true** as a parameter to its constructor.</span></span> <span data-ttu-id="e894a-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e894a-114">For example:</span></span>  
  
         [!code-cpp[AssemblyDelaySignAttribute#4](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cpp/source2.cpp#4)]
         [!code-csharp[AssemblyDelaySignAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyDelaySignAttribute/cs/source2.cs#4)]
         [!code-vb[AssemblyDelaySignAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyDelaySignAttribute/vb/source2.vb#4)]  
  
3.  <span data-ttu-id="e894a-115">Il compilatore inserisce la chiave pubblica nel manifesto dell'assembly e riserva nel file PE lo spazio necessario per la firma completa con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="e894a-115">The compiler inserts the public key into the assembly manifest and reserves space in the PE file for the full strong name signature.</span></span> <span data-ttu-id="e894a-116">La chiave pubblica reale deve essere memorizzata in fase di compilazione dell'assembly, in modo che gli altri assembly contenenti riferimenti a questo assembly siano in grado di ottenere la chiave da memorizzare nei relativi riferimenti di assembly.</span><span class="sxs-lookup"><span data-stu-id="e894a-116">The real public key must be stored while the assembly is built so that other assemblies that reference this assembly can obtain the key to store in their own assembly reference.</span></span>  
  
4.  <span data-ttu-id="e894a-117">Poiché l'assembly non dispone di una firma con nome sicuro valida, è necessario disattivare la verifica della firma di tale assembly.</span><span class="sxs-lookup"><span data-stu-id="e894a-117">Because the assembly does not have a valid strong name signature, the verification of that signature must be turned off.</span></span> <span data-ttu-id="e894a-118">A tale scopo, usare l'opzione **-Vr** dello strumento Nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="e894a-118">You can do this by using the **–Vr** option with the Strong Name tool.</span></span>  
  
     <span data-ttu-id="e894a-119">L'esempio seguente consente di disattivare la verifica per un assembly denominato `myAssembly.dll`.</span><span class="sxs-lookup"><span data-stu-id="e894a-119">The following example turns off verification for an assembly called `myAssembly.dll`.</span></span>  
  
    ```  
    sn –Vr myAssembly.dll  
    ```  
  
     <span data-ttu-id="e894a-120">Per disattivare la verifica delle piattaforme in cui non è possibile eseguire lo strumento Nome sicuro, come microprocessori avanzati del computer RISC (ARM), usare l'opzione **-Vk** per creare un file del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="e894a-120">To turn off verification on platforms where you can’t run the Strong Name tool, such as Advanced RISC Machine (ARM) microprocessors, use the **–Vk** option to create a registry file.</span></span> <span data-ttu-id="e894a-121">Importare il file del Registro di sistema nel Registro di sistema del computer in cui si vuole disattivare la verifica.</span><span class="sxs-lookup"><span data-stu-id="e894a-121">Import the registry file into the registry on the computer where you want to turn off verification.</span></span> <span data-ttu-id="e894a-122">L'esempio seguente consente di creare un file del Registro di sistema per `myAssembly.dll`.</span><span class="sxs-lookup"><span data-stu-id="e894a-122">The following example creates a registry file for `myAssembly.dll`.</span></span>  
  
    ```  
    sn –Vk myRegFile.reg myAssembly.dll  
    ```  
  
     <span data-ttu-id="e894a-123">Con l'opzione **-Vr** o **-Vk** è possibile includere un file con estensione snk per la firma con una chiave di test.</span><span class="sxs-lookup"><span data-stu-id="e894a-123">With either the **–Vr** or **–Vk** option, you can optionally include an .snk file for test key signing.</span></span>  
  
    > [!WARNING]
    > <span data-ttu-id="e894a-124">Non usare i nomi sicuri per la sicurezza,</span><span class="sxs-lookup"><span data-stu-id="e894a-124">Do not rely on strong names for security.</span></span> <span data-ttu-id="e894a-125">poiché forniscono solo un'identità univoca.</span><span class="sxs-lookup"><span data-stu-id="e894a-125">They provide a unique identity only.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="e894a-126">Se si usa il ritardo della firma durante lo sviluppo con Visual Studio in un computer a 64 bit e si compila un assembly per **Qualsiasi CPU**, potrebbe essere necessario applicare due volte l'opzione **-Vr**.</span><span class="sxs-lookup"><span data-stu-id="e894a-126">If you use delay signing during development with Visual Studio on a 64-bit computer, and you compile an assembly for **Any CPU**, you might have to apply the **-Vr** option twice.</span></span> <span data-ttu-id="e894a-127">In Visual Studio **Qualsiasi CPU** è un valore della proprietà di compilazione **Piattaforma di destinazione**. Quando si esegue la compilazione dalla riga di comando, è l'impostazione predefinita. Per eseguire l'applicazione dalla riga di comando o da Esplora risorse, usare la versione a 64 bit di [Sn.exe (strumento Nome sicuro)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) per applicare l'opzione **-Vr** all'assembly.</span><span class="sxs-lookup"><span data-stu-id="e894a-127">(In Visual Studio, **Any CPU** is a value of the **Platform Target** build property; when you compile from the command line, it is the default.) To run your application from the command line or from File Explorer, use the 64-bit version of the [Sn.exe (Strong Name Tool)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) to apply the **-Vr** option to the assembly.</span></span> <span data-ttu-id="e894a-128">Per caricare l'assembly in Visual Studio in fase di progettazione, ad esempio se l'assembly contiene componenti usati da altri assembly nell'applicazione, usare la versione a 32 bit dello strumento Nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="e894a-128">To load the assembly into Visual Studio at design time (for example, if the assembly contains components that are used by other assemblies in your application), use the 32-bit version of the strong-name tool.</span></span> <span data-ttu-id="e894a-129">Questo perché il compilatore JIT compila l'assembly nel codice nativo a 64 bit quando l'assembly viene eseguito dalla riga di comando e nel codice nativo a 32 bit quando l'assembly viene caricato nell'ambiente di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e894a-129">This is because the just-in-time (JIT) compiler compiles the assembly to 64-bit native code when the assembly is run from the command line, and to 32-bit native code when the assembly is loaded into the design-time environment.</span></span>  
  
5.  <span data-ttu-id="e894a-130">Successivamente, di solito prima della consegna, sottoporre l'assembly all'autorità di firma dell'organizzazione per la firma con nome sicuro effettiva tramite l'opzione **-R** dello strumento Nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="e894a-130">Later, usually just before shipping, you submit the assembly to your organization's signing authority for the actual strong name signing using the **–R** option with the Strong Name tool.</span></span>  
  
     <span data-ttu-id="e894a-131">L'esempio seguente consente di firmare un assembly denominato `myAssembly.dll` con un nome sicuro usando la coppia di chiavi `sgKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="e894a-131">The following example signs an assembly called `myAssembly.dll` with a strong name using the `sgKey.snk` key pair.</span></span>  
  
    ```  
    sn -R myAssembly.dll sgKey.snk  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e894a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e894a-132">See Also</span></span>  
 [<span data-ttu-id="e894a-133">Creazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="e894a-133">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="e894a-134">Procedura: Creare una coppia di chiavi pubblica/privata</span><span class="sxs-lookup"><span data-stu-id="e894a-134">How to: Create a Public-Private Key Pair</span></span>](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [<span data-ttu-id="e894a-135">Sn.exe (strumento Nome sicuro)</span><span class="sxs-lookup"><span data-stu-id="e894a-135">Sn.exe (Strong Name Tool)</span></span>](../../../docs/framework/tools/sn-exe-strong-name-tool.md)  
 [<span data-ttu-id="e894a-136">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="e894a-136">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
