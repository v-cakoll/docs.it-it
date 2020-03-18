---
title: Firma ritardata di un assembly
ms.date: 08/19/2019
helpviewer_keywords:
- deferring assembly signing
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, delaying assembly signing
- partial assembly signing
ms.assetid: 9d300e17-5bf1-4360-97da-2aa55efd9070
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 113df1ad3fc3ac1e27ebfef572494c1f15a3dbb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73733171"
---
# <a name="delay-sign-an-assembly"></a><span data-ttu-id="de398-102">Firma ritardata di un assembly</span><span class="sxs-lookup"><span data-stu-id="de398-102">Delay-sign an assembly</span></span>

<span data-ttu-id="de398-103">Un'organizzazione può avere una coppia di chiavi strettamente sorvegliata a cui gli sviluppatori non possono accedere quotidianamente.</span><span class="sxs-lookup"><span data-stu-id="de398-103">An organization can have a closely guarded key pair that developers can't access on a daily basis.</span></span> <span data-ttu-id="de398-104">La chiave pubblica è spesso disponibile, ma l'accesso alla chiave privata è consentito solo ad alcune persone.</span><span class="sxs-lookup"><span data-stu-id="de398-104">The public key is often available, but access to the private key is restricted to only a few individuals.</span></span> <span data-ttu-id="de398-105">Quando si sviluppano assembly con nome sicuro, in ogni assembly che fa riferimento all'assembly con nome sicuro di destinazione è contenuto un token della chiave pubblica usata per assegnare un nome sicuro all'assembly di destinazione.</span><span class="sxs-lookup"><span data-stu-id="de398-105">When developing assemblies with strong names, each assembly that references the strong-named target assembly contains the token of the public key used to give the target assembly a strong name.</span></span> <span data-ttu-id="de398-106">È quindi necessario che la chiave pubblica risulti disponibile durante il processo di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="de398-106">This requires that the public key be available during the development process.</span></span>

<span data-ttu-id="de398-107">È possibile utilizzare la firma ritardata o parziale in fase di compilazione per riservare spazio nel file eseguibile portabile (PE) per la firma con nome sicuro, ma rinviare la firma effettiva fino a una fase successiva, in genere appena prima della spedizione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="de398-107">You can use delayed or partial signing at build time to reserve space in the portable executable (PE) file for the strong name signature, but defer the actual signing until some later stage, usually just before shipping the assembly.</span></span>

<span data-ttu-id="de398-108">Per ritardare la firma di un assieme:</span><span class="sxs-lookup"><span data-stu-id="de398-108">To delay-sign an assembly:</span></span>

1. <span data-ttu-id="de398-109">Ottenere la parte di chiave pubblica della coppia di chiavi dall'organizzazione che eseguirà la firma finale.</span><span class="sxs-lookup"><span data-stu-id="de398-109">Get the public key portion of the key pair from the organization that will do the eventual signing.</span></span> <span data-ttu-id="de398-110">In genere questa chiave è sotto forma di un file *con estensione snk,* che può essere creato utilizzando [lo strumento nome sicuro (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) fornito da Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="de398-110">Typically this key is in the form of an *.snk* file, which can be created using the [Strong Name tool (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) provided by the Windows SDK.</span></span>

2. <span data-ttu-id="de398-111">Apporre annotazioni al codice sorgente per l'assembly usando due attributi personalizzati da <xref:System.Reflection>:</span><span class="sxs-lookup"><span data-stu-id="de398-111">Annotate the source code for the assembly with two custom attributes from <xref:System.Reflection>:</span></span>

   - <span data-ttu-id="de398-112"><xref:System.Reflection.AssemblyKeyFileAttribute>, che consente di passare il nome del file contenente la chiave pubblica come parametro al costruttore.</span><span class="sxs-lookup"><span data-stu-id="de398-112"><xref:System.Reflection.AssemblyKeyFileAttribute>, which passes the name of the file containing the public key as a parameter to its constructor.</span></span>

   - <span data-ttu-id="de398-113"><xref:System.Reflection.AssemblyDelaySignAttribute>, che indica che la firma ritardata viene utilizzata passando **true** come parametro al relativo costruttore.</span><span class="sxs-lookup"><span data-stu-id="de398-113"><xref:System.Reflection.AssemblyDelaySignAttribute>, which indicates that delay signing is being used by passing **true** as a parameter to its constructor.</span></span>

   <span data-ttu-id="de398-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="de398-114">For example:</span></span>

   ```cpp
   [assembly:AssemblyKeyFileAttribute("myKey.snk")];
   [assembly:AssemblyDelaySignAttribute(true)];
   ```

   ```csharp
   [assembly:AssemblyKeyFileAttribute("myKey.snk")]
   [assembly:AssemblyDelaySignAttribute(true)]
   ```

   ```vb
   <Assembly:AssemblyKeyFileAttribute("myKey.snk")>
   <Assembly:AssemblyDelaySignAttribute(True)>
   ```

3. <span data-ttu-id="de398-115">Il compilatore inserisce la chiave pubblica nel manifesto dell'assembly e riserva nel file PE lo spazio necessario per la firma completa con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="de398-115">The compiler inserts the public key into the assembly manifest and reserves space in the PE file for the full strong name signature.</span></span> <span data-ttu-id="de398-116">La chiave pubblica reale deve essere memorizzata in fase di compilazione dell'assembly, in modo che gli altri assembly contenenti riferimenti a questo assembly siano in grado di ottenere la chiave da memorizzare nei relativi riferimenti di assembly.</span><span class="sxs-lookup"><span data-stu-id="de398-116">The real public key must be stored while the assembly is built so that other assemblies that reference this assembly can obtain the key to store in their own assembly reference.</span></span>

4. <span data-ttu-id="de398-117">Poiché l'assembly non dispone di una firma con nome sicuro valida, è necessario disattivare la verifica della firma di tale assembly.</span><span class="sxs-lookup"><span data-stu-id="de398-117">Because the assembly does not have a valid strong name signature, the verification of that signature must be turned off.</span></span> <span data-ttu-id="de398-118">A tale scopo, usare l'opzione **-Vr** dello strumento Nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="de398-118">You can do this by using the **–Vr** option with the Strong Name tool.</span></span>

     <span data-ttu-id="de398-119">Nell'esempio riportato di seguito viene disattivata la verifica per un assembly denominato *myAssembly.dll*.</span><span class="sxs-lookup"><span data-stu-id="de398-119">The following example turns off verification for an assembly called *myAssembly.dll*.</span></span>

   ```console
   sn –Vr myAssembly.dll
   ```

   <span data-ttu-id="de398-120">Per disattivare la verifica delle piattaforme in cui non è possibile eseguire lo strumento Nome sicuro, come microprocessori avanzati del computer RISC (ARM), usare l'opzione **-Vk** per creare un file del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="de398-120">To turn off verification on platforms where you can’t run the Strong Name tool, such as Advanced RISC Machine (ARM) microprocessors, use the **–Vk** option to create a registry file.</span></span> <span data-ttu-id="de398-121">Importare il file del Registro di sistema nel Registro di sistema del computer in cui si vuole disattivare la verifica.</span><span class="sxs-lookup"><span data-stu-id="de398-121">Import the registry file into the registry on the computer where you want to turn off verification.</span></span> <span data-ttu-id="de398-122">L'esempio seguente consente di creare un file del Registro di sistema per `myAssembly.dll`.</span><span class="sxs-lookup"><span data-stu-id="de398-122">The following example creates a registry file for `myAssembly.dll`.</span></span>

   ```console
   sn –Vk myRegFile.reg myAssembly.dll
   ```

   <span data-ttu-id="de398-123">Con l'opzione **–Vr** o **–Vk,** è possibile includere facoltativamente un file *con estensione snk* per la firma della chiave di test.</span><span class="sxs-lookup"><span data-stu-id="de398-123">With either the **–Vr** or **–Vk** option, you can optionally include an *.snk* file for test key signing.</span></span>

   > [!WARNING]
   > <span data-ttu-id="de398-124">Non usare i nomi sicuri per la sicurezza,</span><span class="sxs-lookup"><span data-stu-id="de398-124">Do not rely on strong names for security.</span></span> <span data-ttu-id="de398-125">poiché forniscono solo un'identità univoca.</span><span class="sxs-lookup"><span data-stu-id="de398-125">They provide a unique identity only.</span></span>

   > [!NOTE]
   > <span data-ttu-id="de398-126">Se si usa il ritardo della firma durante lo sviluppo con Visual Studio in un computer a 64 bit e si compila un assembly per **Qualsiasi CPU**, potrebbe essere necessario applicare due volte l'opzione **-Vr**.</span><span class="sxs-lookup"><span data-stu-id="de398-126">If you use delay signing during development with Visual Studio on a 64-bit computer, and you compile an assembly for **Any CPU**, you might have to apply the **-Vr** option twice.</span></span> <span data-ttu-id="de398-127">(In Visual Studio, **qualsiasi CPU** è un valore della proprietà di compilazione destinazione della **piattaforma;** quando si esegue la compilazione dalla riga di comando, è l'impostazione predefinita.) Per eseguire l'applicazione dalla riga di comando o da Esplora file, utilizzare la versione a 64 bit di [Sn.exe (strumento Nome sicuro)](../../framework/tools/sn-exe-strong-name-tool.md) per applicare l'opzione **-Vr** all'assembly.</span><span class="sxs-lookup"><span data-stu-id="de398-127">(In Visual Studio, **Any CPU** is a value of the **Platform Target** build property; when you compile from the command line, it is the default.) To run your application from the command line or from File Explorer, use the 64-bit version of the [Sn.exe (Strong Name tool)](../../framework/tools/sn-exe-strong-name-tool.md) to apply the **-Vr** option to the assembly.</span></span> <span data-ttu-id="de398-128">Per caricare l'assembly in Visual Studio in fase di progettazione, ad esempio se l'assembly contiene componenti usati da altri assembly nell'applicazione, usare la versione a 32 bit dello strumento Nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="de398-128">To load the assembly into Visual Studio at design time (for example, if the assembly contains components that are used by other assemblies in your application), use the 32-bit version of the strong-name tool.</span></span> <span data-ttu-id="de398-129">Questo perché il compilatore JIT compila l'assembly nel codice nativo a 64 bit quando l'assembly viene eseguito dalla riga di comando e nel codice nativo a 32 bit quando l'assembly viene caricato nell'ambiente di progettazione.</span><span class="sxs-lookup"><span data-stu-id="de398-129">This is because the just-in-time (JIT) compiler compiles the assembly to 64-bit native code when the assembly is run from the command line, and to 32-bit native code when the assembly is loaded into the design-time environment.</span></span>

5. <span data-ttu-id="de398-130">Successivamente, di solito prima della consegna, sottoporre l'assembly all'autorità di firma dell'organizzazione per la firma con nome sicuro effettiva tramite l'opzione **-R** dello strumento Nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="de398-130">Later, usually just before shipping, you submit the assembly to your organization's signing authority for the actual strong name signing using the **–R** option with the Strong Name tool.</span></span>

   <span data-ttu-id="de398-131">Nell'esempio riportato di seguito viene firmato un assembly denominato *myAssembly.dll* con un nome sicuro utilizzando la coppia di chiavi *sgKey.snk.*</span><span class="sxs-lookup"><span data-stu-id="de398-131">The following example signs an assembly called *myAssembly.dll* with a strong name using the *sgKey.snk* key pair.</span></span>

   ```console
   sn -R myAssembly.dll sgKey.snk
   ```

## <a name="see-also"></a><span data-ttu-id="de398-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de398-132">See also</span></span>

- [<span data-ttu-id="de398-133">Creare assembly</span><span class="sxs-lookup"><span data-stu-id="de398-133">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="de398-134">Procedura: Creare una coppia di chiavi pubblica/privata</span><span class="sxs-lookup"><span data-stu-id="de398-134">How to: Create a public-private key pair</span></span>](create-public-private-key-pair.md)
- [<span data-ttu-id="de398-135">Sn.exe (strumento Nome sicuro)</span><span class="sxs-lookup"><span data-stu-id="de398-135">Sn.exe (Strong Name tool)</span></span>](../../framework/tools/sn-exe-strong-name-tool.md)
