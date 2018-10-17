---
title: Denominazione sicura e le librerie .NET
description: Le procedure consigliate per sicuro delle librerie .NET di denominazione.
author: jamesnk
ms.author: mairaw
ms.date: 10/16/2018
ms.openlocfilehash: e3f7d443eb9acc84c800ea2611b803733085391c
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372806"
---
# <a name="strong-naming"></a><span data-ttu-id="992b7-103">Denominazione sicura</span><span class="sxs-lookup"><span data-stu-id="992b7-103">Strong naming</span></span>

<span data-ttu-id="992b7-104">Denominazione sicura fa riferimento a firmare un assembly con una chiave, producendo un [assembly con nome sicuro](../../framework/app-domains/strong-named-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="992b7-104">Strong naming refers to signing an assembly with a key, producing a [strong-named assembly](../../framework/app-domains/strong-named-assemblies.md).</span></span> <span data-ttu-id="992b7-105">Quando un assembly è sicuro, crea un'identità univoca in base al numero di versione nome e l'assembly e può aiutare a evitare i conflitti di assembly.</span><span class="sxs-lookup"><span data-stu-id="992b7-105">When an assembly is strong-named, it creates a unique identity based on the name and assembly version number, and it can help prevent assembly conflicts.</span></span>

<span data-ttu-id="992b7-106">Lo svantaggio di nome sicuro è che .NET Framework su Windows consente strict durante il caricamento degli assembly dopo che un assembly ha un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="992b7-106">The downside to strong naming is that the .NET Framework on Windows enables strict loading of assemblies once an assembly is strong named.</span></span> <span data-ttu-id="992b7-107">Un riferimento di assembly con nome sicuro debba corrispondere esattamente alla versione fa riferimento un assembly, imporre agli sviluppatori [configurare i reindirizzamenti di associazione](../../framework/configure-apps/redirect-assembly-versions.md) quando si usa l'assembly:</span><span class="sxs-lookup"><span data-stu-id="992b7-107">A strong-named assembly reference must exactly match the version referenced by an assembly, forcing developers to [configure binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) when using the assembly:</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly" publicKeyToken="32ab4ba45e0a69a1" culture="neutral" />
            <bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

<span data-ttu-id="992b7-108">Quando gli sviluppatori .NET si lamentano nome sicuro, cosa è in genere reclamo è il caricamento dell'assembly strict.</span><span class="sxs-lookup"><span data-stu-id="992b7-108">When .NET developers complain about strong naming, what they're usually complaining about is strict assembly loading.</span></span> <span data-ttu-id="992b7-109">Fortunatamente, questo problema è isolata e prevede di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="992b7-109">Fortunately, this issue is isolated to the .NET Framework.</span></span> <span data-ttu-id="992b7-110">La maggior parte delle altre implementazioni di .NET, Xamarin, UWP e .NET core non è il caricamento dell'assembly strict e rimuove lo svantaggio principale di nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="992b7-110">.NET Core, Xamarin, UWP, and most other .NET implementations don't have strict assembly loading and removes the main downside of strong naming.</span></span>

<span data-ttu-id="992b7-111">Un aspetto importante del nome sicuro è costituito da virale: un nome sicuro assembly possono fare riferimento solo altri sicuro degli assembly con nome.</span><span class="sxs-lookup"><span data-stu-id="992b7-111">One important aspect of strong naming is that it's viral: a strong named assembly can only reference other strong named assemblies.</span></span> <span data-ttu-id="992b7-112">Se la libreria non è sicura denominato, è stato escluso gli sviluppatori che stanno progettando un'applicazione o una raccolta che è necessario un nome sicuro dal loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="992b7-112">If your library isn't strong named, then you have excluded developers who are building an application or library that needs strong naming from using it.</span></span>

<span data-ttu-id="992b7-113">Sono i vantaggi del nome sicuro:</span><span class="sxs-lookup"><span data-stu-id="992b7-113">The benefits of strong naming are:</span></span>

1. <span data-ttu-id="992b7-114">L'assembly può essere fatto riferimento e usato da altri assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="992b7-114">The assembly can be referenced and used by other strong-named assemblies.</span></span>
2. <span data-ttu-id="992b7-115">L'assembly può essere archiviato nella Global Assembly Cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="992b7-115">The assembly can be stored in the Global Assembly Cache (GAC).</span></span>
3. <span data-ttu-id="992b7-116">L'assembly può essere caricato affiancato con altre versioni dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="992b7-116">The assembly can be loaded side by side with other versions of the assembly.</span></span> <span data-ttu-id="992b7-117">Il caricamento dell'assembly side-by-side è comunemente richieste dalle applicazioni con architetture di plug-in.</span><span class="sxs-lookup"><span data-stu-id="992b7-117">Side-by-side assembly loading is commonly required by applications with plug-in architectures.</span></span>

## <a name="create-strong-named-net-libraries"></a><span data-ttu-id="992b7-118">Creare sicuro denominato librerie .NET</span><span class="sxs-lookup"><span data-stu-id="992b7-118">Create strong named .NET libraries</span></span>

<span data-ttu-id="992b7-119">È necessario un nome sicuro le librerie .NET open source.</span><span class="sxs-lookup"><span data-stu-id="992b7-119">You should strong name your open-source .NET libraries.</span></span> <span data-ttu-id="992b7-120">Un assembly di denominazione sicura garantisce la maggior parte degli utenti può usarla e solo il caricamento dell'assembly strict influisce su .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="992b7-120">Strong naming an assembly ensures the most people can use it, and strict assembly loading only affects the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="992b7-121">Questo materiale sussidiario è specifico di librerie .NET distribuite pubblicamente, ad esempio le librerie .NET pubblicati su NuGet.org. Nome sicuro non richiesti dalla maggior parte delle applicazioni .NET e non deve essere eseguita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="992b7-121">This guidance is specific to publicly distributed .NET libraries, such as .NET libraries published on NuGet.org. Strong naming is not required by most .NET applications and should not be done by default.</span></span>

<span data-ttu-id="992b7-122">**Provare a ✔️** sicuro gli assembly della libreria.</span><span class="sxs-lookup"><span data-stu-id="992b7-122">**✔️ CONSIDER** strong naming your library's assemblies.</span></span>

<span data-ttu-id="992b7-123">**Provare a ✔️** archiviare la chiave utilizzata per nome sicuro nel sistema di controllo di origine.</span><span class="sxs-lookup"><span data-stu-id="992b7-123">**✔️ CONSIDER** checking in the key used to strong name into your source control system.</span></span>

> <span data-ttu-id="992b7-124">Una chiave disponibile pubblicamente consente agli sviluppatori di modificare e ricompilare il codice sorgente della libreria con la stessa chiave.</span><span class="sxs-lookup"><span data-stu-id="992b7-124">A publicly available key lets developers modify and recompile your library source code with the same key.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="992b7-125">Quando un'identità del servizio di crittografia, è possibile definire [Authenticode](/windows-hardware/drivers/install/authenticode) e [firmare il pacchetto NuGet](/nuget/create-packages/sign-a-package) sono consigliati.</span><span class="sxs-lookup"><span data-stu-id="992b7-125">When a cryptographic identity is desired, [Authenticode](/windows-hardware/drivers/install/authenticode) and [NuGet Package Signing](/nuget/create-packages/sign-a-package) are recommended.</span></span> <span data-ttu-id="992b7-126">Nome sicuro di non usare per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="992b7-126">Strong naming should not be used for security considerations.</span></span>

<span data-ttu-id="992b7-127">**Provare a ✔️** incrementare la versione dell'assembly sulle modifiche di versione principale solo per consentire agli utenti di ridurre i reindirizzamenti di associazione e con quale frequenza vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="992b7-127">**✔️ CONSIDER** incrementing the assembly version on only major version changes to help users reduce binding redirects, and how often they're updated.</span></span>

> <span data-ttu-id="992b7-128">Altre informazioni, vedere [controllo delle versioni e la versione dell'assembly](./versioning.md#assembly-version).</span><span class="sxs-lookup"><span data-stu-id="992b7-128">Read more about [versioning and the assembly version](./versioning.md#assembly-version).</span></span>

<span data-ttu-id="992b7-129">**NON ❌** aggiungere, rimuovere o modificare la chiave di denominazione intenso.</span><span class="sxs-lookup"><span data-stu-id="992b7-129">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

> <span data-ttu-id="992b7-130">Modifica della chiave di denominazione sicuro di un assembly viene modificato l'identità dell'assembly e interrompe il codice compilato che lo utilizza.</span><span class="sxs-lookup"><span data-stu-id="992b7-130">Modifying an assembly's strong naming key changes the assembly's identity and breaks compiled code that uses it.</span></span> <span data-ttu-id="992b7-131">Per altre informazioni, vedere [binario modifiche di rilievo](./breaking-changes.md#binary-breaking-change).</span><span class="sxs-lookup"><span data-stu-id="992b7-131">For more information, see [binary breaking changes](./breaking-changes.md#binary-breaking-change).</span></span>

<span data-ttu-id="992b7-132">**NON ❌** pubblicare versioni sicuro e non nome sicuro della libreria.</span><span class="sxs-lookup"><span data-stu-id="992b7-132">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="992b7-133">Ad esempio, `Contoso.Api` e `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="992b7-133">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

> <span data-ttu-id="992b7-134">Pubblicazione due fork di pacchetti per gli sviluppatori eco-sistema.</span><span class="sxs-lookup"><span data-stu-id="992b7-134">Publishing two packages forks your developer eco-system.</span></span> <span data-ttu-id="992b7-135">Inoltre, se un'applicazione finisce in entrambi i pacchetti base lo sviluppatore può verificarsi conflitti di nomi di tipo.</span><span class="sxs-lookup"><span data-stu-id="992b7-135">Also, if an application ends up depending on both packages the developer can encounter type name conflicts.</span></span> <span data-ttu-id="992b7-136">Per quanto riguarda .NET sono diversi tipi in assembly diversi.</span><span class="sxs-lookup"><span data-stu-id="992b7-136">As far as .NET is concerned they are different types in different assemblies.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="992b7-137">[Precedente](./cross-platform-targeting.md)
[Successivo](./nuget.md)</span><span class="sxs-lookup"><span data-stu-id="992b7-137">[Previous](./cross-platform-targeting.md)
[Next](./nuget.md)</span></span>
