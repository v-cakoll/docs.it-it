---
title: Creazione degli assembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2168cbcd19437c1e275da7a01aa0c75ab47600eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="creating-assemblies"></a><span data-ttu-id="ecc0d-102">Creazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="ecc0d-102">Creating Assemblies</span></span>
<span data-ttu-id="ecc0d-103">È possibile creare assembly su uno o più file tramite un ambiente IDE, ad esempio [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], o tramite i compilatori e gli strumenti forniti da [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecc0d-103">You can create single-file or multifile assemblies using an IDE, such as [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], or the compilers and tools provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span> <span data-ttu-id="ecc0d-104">L'assembly più semplice è costituito da un unico file con un nome semplice, caricato in un unico dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-104">The simplest assembly is a single file that has a simple name and is loaded into a single application domain.</span></span> <span data-ttu-id="ecc0d-105">Altri assembly all'esterno della directory dell'applicazione non possono fare riferimento a questo assembly, che non può neanche essere sottoposto al controllo della versione.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-105">This assembly cannot be referenced by other assemblies outside the application directory and does not undergo version checking.</span></span> <span data-ttu-id="ecc0d-106">Per disinstallare l'applicazione costituita dall'assembly, è sufficiente eliminare la directory in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-106">To uninstall the application made up of the assembly, you simply delete the directory where it resides.</span></span> <span data-ttu-id="ecc0d-107">Per molti sviluppatori un assembly con queste funzionalità è tutto ciò che serve per distribuire un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-107">For many developers, an assembly with these features is all that is needed to deploy an application.</span></span>  
  
 <span data-ttu-id="ecc0d-108">È possibile creare un assembly su più file da diversi moduli di codice e file di risorse.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-108">You can create a multifile assembly from several code modules and resource files.</span></span> <span data-ttu-id="ecc0d-109">È anche possibile creare un assembly che può essere condiviso da più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-109">You can also create an assembly that can be shared by multiple applications.</span></span> <span data-ttu-id="ecc0d-110">Un assembly condiviso deve avere un nome sicuro e può essere distribuito nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-110">A shared assembly must have a strong name and can be deployed in the global assembly cache.</span></span>  
  
 <span data-ttu-id="ecc0d-111">Quando si raggruppano moduli di codice e risorse negli assembly, sono disponibili diverse opzioni in base ai fattori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ecc0d-111">You have several options when grouping code modules and resources into assemblies, depending on the following factors:</span></span>  
  
-   <span data-ttu-id="ecc0d-112">Controllo delle versioni</span><span class="sxs-lookup"><span data-stu-id="ecc0d-112">Versioning</span></span>  
  
     <span data-ttu-id="ecc0d-113">Raggruppare i moduli che devono avere le stesse informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-113">Group modules that should have the same version information.</span></span>  
  
-   <span data-ttu-id="ecc0d-114">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="ecc0d-114">Deployment</span></span>  
  
     <span data-ttu-id="ecc0d-115">Raggruppare i moduli di codice e le risorse che supportano il modello di distribuzione usato.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-115">Group code modules and resources that support your model of deployment.</span></span>  
  
-   <span data-ttu-id="ecc0d-116">Riuso</span><span class="sxs-lookup"><span data-stu-id="ecc0d-116">Reuse</span></span>  
  
     <span data-ttu-id="ecc0d-117">Raggruppare i moduli se possono essere usati insieme in modo logico per uno scopo.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-117">Group modules if they can be logically used together for some purpose.</span></span> <span data-ttu-id="ecc0d-118">Ad esempio, è possibile inserire nello stesso assembly un assembly costituito da tipi e classi usati raramente per la manutenzione di programmi.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-118">For example, an assembly consisting of types and classes used infrequently for program maintenance can be put in the same assembly.</span></span> <span data-ttu-id="ecc0d-119">In più, i tipi che si intende condividere più applicazioni devono essere raggruppati in un assembly, che deve essere firmato con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-119">In addition, types that you intend to share with multiple applications should be grouped into an assembly and the assembly should be signed with a strong name.</span></span>  
  
-   <span data-ttu-id="ecc0d-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ecc0d-120">Security</span></span>  
  
     <span data-ttu-id="ecc0d-121">Raggruppare moduli contenenti tipi che richiedono le stesse autorizzazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-121">Group modules containing types that require the same security permissions.</span></span>  
  
-   <span data-ttu-id="ecc0d-122">Ambito</span><span class="sxs-lookup"><span data-stu-id="ecc0d-122">Scoping</span></span>  
  
     <span data-ttu-id="ecc0d-123">Raggruppare moduli contenenti tipi la cui visibilità deve essere limitata allo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-123">Group modules containing types whose visibility should be restricted to the same assembly.</span></span>  
  
 <span data-ttu-id="ecc0d-124">Sono necessarie considerazioni speciali quando si rendono disponibili assembly Common Language Runtime ad applicazioni COM non gestite.</span><span class="sxs-lookup"><span data-stu-id="ecc0d-124">Special considerations must be made when making common language runtime assemblies available to unmanaged COM applications.</span></span> <span data-ttu-id="ecc0d-125">Per altre informazioni sull'uso di codice non gestito, vedere [Esposizione di componenti .NET Framework a COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="ecc0d-125">For more information about working with unmanaged code, see [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc0d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecc0d-126">See Also</span></span>  
 [<span data-ttu-id="ecc0d-127">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="ecc0d-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="ecc0d-128">Controllo delle versioni degli assembly</span><span class="sxs-lookup"><span data-stu-id="ecc0d-128">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)  
 [<span data-ttu-id="ecc0d-129">Procedura: Compilare un assembly su singolo file</span><span class="sxs-lookup"><span data-stu-id="ecc0d-129">How to: Build a Single-File Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 [<span data-ttu-id="ecc0d-130">Procedura: Compilare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="ecc0d-130">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="ecc0d-131">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="ecc0d-131">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="ecc0d-132">Assembly su più file</span><span class="sxs-lookup"><span data-stu-id="ecc0d-132">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)
