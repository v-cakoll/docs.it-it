---
title: Creazione di assembly
ms.date: 08/19/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2dda45cca182d75bc77916cdf862ada9faead9ec
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70973306"
---
# <a name="create-assemblies"></a><span data-ttu-id="5cd72-102">Creazione di assembly</span><span class="sxs-lookup"><span data-stu-id="5cd72-102">Create assemblies</span></span>

<span data-ttu-id="5cd72-103">È possibile creare assembly con uno o più file usando un ambiente IDE, ad esempio Visual Studio, oppure con i compilatori e gli strumenti forniti da Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="5cd72-103">You can create single-file or multifile assemblies using an IDE, such as Visual Studio, or the compilers and tools provided by the Windows SDK.</span></span> <span data-ttu-id="5cd72-104">L'assembly più semplice è costituito da un unico file con un nome semplice, caricato in un unico dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5cd72-104">The simplest assembly is a single file that has a simple name and is loaded into a single application domain.</span></span> <span data-ttu-id="5cd72-105">Altri assembly all'esterno della directory dell'applicazione non possono fare riferimento a questo assembly, che non può neanche essere sottoposto al controllo della versione.</span><span class="sxs-lookup"><span data-stu-id="5cd72-105">This assembly cannot be referenced by other assemblies outside the application directory and does not undergo version checking.</span></span> <span data-ttu-id="5cd72-106">Per disinstallare l'applicazione costituita dall'assembly, è sufficiente eliminare la directory in cui si trova.</span><span class="sxs-lookup"><span data-stu-id="5cd72-106">To uninstall the application made up of the assembly, you simply delete the directory where it resides.</span></span> <span data-ttu-id="5cd72-107">Per molti sviluppatori un assembly con queste funzionalità è tutto ciò che serve per distribuire un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5cd72-107">For many developers, an assembly with these features is all that is needed to deploy an application.</span></span>

<span data-ttu-id="5cd72-108">È possibile creare un assembly su più file da diversi moduli di codice e file di risorse.</span><span class="sxs-lookup"><span data-stu-id="5cd72-108">You can create a multifile assembly from several code modules and resource files.</span></span> <span data-ttu-id="5cd72-109">È anche possibile creare un assembly che può essere condiviso da più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="5cd72-109">You can also create an assembly that can be shared by multiple applications.</span></span> <span data-ttu-id="5cd72-110">Un assembly condiviso deve avere un nome sicuro e può essere distribuito nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="5cd72-110">A shared assembly must have a strong name and can be deployed in the global assembly cache.</span></span>

<span data-ttu-id="5cd72-111">Quando si raggruppano moduli di codice e risorse negli assembly, sono disponibili diverse opzioni in base ai fattori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5cd72-111">You have several options when grouping code modules and resources into assemblies, depending on the following factors:</span></span>

- <span data-ttu-id="5cd72-112">Controllo delle versioni</span><span class="sxs-lookup"><span data-stu-id="5cd72-112">Versioning</span></span>

     <span data-ttu-id="5cd72-113">Raggruppare i moduli che devono avere le stesse informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="5cd72-113">Group modules that should have the same version information.</span></span>

- <span data-ttu-id="5cd72-114">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="5cd72-114">Deployment</span></span>

     <span data-ttu-id="5cd72-115">Raggruppare i moduli di codice e le risorse che supportano il modello di distribuzione usato.</span><span class="sxs-lookup"><span data-stu-id="5cd72-115">Group code modules and resources that support your model of deployment.</span></span>

- <span data-ttu-id="5cd72-116">Riuso</span><span class="sxs-lookup"><span data-stu-id="5cd72-116">Reuse</span></span>

     <span data-ttu-id="5cd72-117">Raggruppare i moduli se possono essere usati insieme in modo logico per uno scopo.</span><span class="sxs-lookup"><span data-stu-id="5cd72-117">Group modules if they can be logically used together for some purpose.</span></span> <span data-ttu-id="5cd72-118">Ad esempio, è possibile inserire nello stesso assembly un assembly costituito da tipi e classi usati raramente per la manutenzione di programmi.</span><span class="sxs-lookup"><span data-stu-id="5cd72-118">For example, an assembly consisting of types and classes used infrequently for program maintenance can be put in the same assembly.</span></span> <span data-ttu-id="5cd72-119">In più, i tipi che si intende condividere più applicazioni devono essere raggruppati in un assembly, che deve essere firmato con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="5cd72-119">In addition, types that you intend to share with multiple applications should be grouped into an assembly and the assembly should be signed with a strong name.</span></span>

- <span data-ttu-id="5cd72-120">Security</span><span class="sxs-lookup"><span data-stu-id="5cd72-120">Security</span></span>

     <span data-ttu-id="5cd72-121">Raggruppare moduli contenenti tipi che richiedono le stesse autorizzazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5cd72-121">Group modules containing types that require the same security permissions.</span></span>

- <span data-ttu-id="5cd72-122">Ambito</span><span class="sxs-lookup"><span data-stu-id="5cd72-122">Scoping</span></span>

     <span data-ttu-id="5cd72-123">Raggruppare moduli contenenti tipi la cui visibilità deve essere limitata allo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="5cd72-123">Group modules containing types whose visibility should be restricted to the same assembly.</span></span>

<span data-ttu-id="5cd72-124">Quando si rendono disponibili assembly Common Language Runtime alle applicazioni COM non gestite, è necessario tenere presenti alcune considerazioni speciali.</span><span class="sxs-lookup"><span data-stu-id="5cd72-124">There are special considerations when making common language runtime assemblies available to unmanaged COM applications.</span></span> <span data-ttu-id="5cd72-125">Per ulteriori informazioni sull'utilizzo di codice non gestito, vedere [esporre componenti .NET Framework a com](../../framework/interop/exposing-dotnet-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="5cd72-125">For more information about working with unmanaged code, see [Expose .NET Framework components to COM](../../framework/interop/exposing-dotnet-components-to-com.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5cd72-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cd72-126">See also</span></span>

- [<span data-ttu-id="5cd72-127">Programma con assembly</span><span class="sxs-lookup"><span data-stu-id="5cd72-127">Program with assemblies</span></span>](program.md)
- [<span data-ttu-id="5cd72-128">Controllo delle versioni degli assembly</span><span class="sxs-lookup"><span data-stu-id="5cd72-128">Assembly versioning</span></span>](versioning.md)
- [<span data-ttu-id="5cd72-129">Procedura: Compilare un assembly a file singolo</span><span class="sxs-lookup"><span data-stu-id="5cd72-129">How to: Build a single-file assembly</span></span>](../../framework/app-domains/build-single-file-assembly.md)
- [<span data-ttu-id="5cd72-130">Procedura: Compilare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="5cd72-130">How to: Build a multifile assembly</span></span>](../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="5cd72-131">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="5cd72-131">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="5cd72-132">Assembly su più file</span><span class="sxs-lookup"><span data-stu-id="5cd72-132">Multifile assemblies</span></span>](../../framework/app-domains/multifile-assemblies.md)
