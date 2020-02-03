---
title: Creazione di nomi sicuri e librerie .NET
description: Procedure consigliate per la creazione di nomi sicuri per le librerie .NET.
ms.date: 10/16/2018
ms.openlocfilehash: db268093b07a2ece7cdb8329fd789b52da9c5c32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744526"
---
# <a name="strong-naming"></a><span data-ttu-id="4d337-103">Denominazione sicura</span><span class="sxs-lookup"><span data-stu-id="4d337-103">Strong naming</span></span>

<span data-ttu-id="4d337-104">La creazione di nomi sicuri si riferisce alla firma di un assembly con una chiave, per produrre un [assembly con nome sicuro](../assembly/strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="4d337-104">Strong naming refers to signing an assembly with a key, producing a [strong-named assembly](../assembly/strong-named.md).</span></span> <span data-ttu-id="4d337-105">Quando un assembly ha un nome sicuro, viene creata un'identità univoca basata sul nome e sul numero di versione dell'assembly e ciò può aiutare a evitare i conflitti di assembly.</span><span class="sxs-lookup"><span data-stu-id="4d337-105">When an assembly is strong-named, it creates a unique identity based on the name and assembly version number, and it can help prevent assembly conflicts.</span></span>

<span data-ttu-id="4d337-106">Lo svantaggio dei nomi sicuri è che .NET Framework in Windows abilita il caricamento in modalità strict per gli assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="4d337-106">The downside to strong naming is that the .NET Framework on Windows enables strict loading of assemblies once an assembly is strong named.</span></span> <span data-ttu-id="4d337-107">Un riferimento a un assembly con nome sicuro deve corrispondere esattamente alla versione a cui viene fatto riferimento da un assembly, quindi gli sviluppatori devono [configurare reindirizzamenti di binding](../../framework/configure-apps/redirect-assembly-versions.md) quando l'assembly viene usato:</span><span class="sxs-lookup"><span data-stu-id="4d337-107">A strong-named assembly reference must exactly match the version referenced by an assembly, forcing developers to [configure binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) when using the assembly:</span></span>

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

<span data-ttu-id="4d337-108">Quando gli sviluppatori .NET si lamentano dei nomi sicuri, in realtà ciò che non apprezzano è il caricamento degli assembly in modalità strict.</span><span class="sxs-lookup"><span data-stu-id="4d337-108">When .NET developers complain about strong naming, what they're usually complaining about is strict assembly loading.</span></span> <span data-ttu-id="4d337-109">Fortunatamente, questo problema riguarda solo .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d337-109">Fortunately, this issue is isolated to the .NET Framework.</span></span> <span data-ttu-id="4d337-110">.NET Core, Xamarin, la piattaforma UWP e la maggior parte delle altre implementazioni .NET non prevedono il caricamento degli assembly in modalità strict, ovviando così al principale svantaggio dei nomi sicuri.</span><span class="sxs-lookup"><span data-stu-id="4d337-110">.NET Core, Xamarin, UWP, and most other .NET implementations don't have strict assembly loading and removes the main downside of strong naming.</span></span>

<span data-ttu-id="4d337-111">Un aspetto importante dei nomi sicuri è che sono virali: un assembly con nome sicuro può fare riferimento solo ad altri assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="4d337-111">One important aspect of strong naming is that it's viral: a strong named assembly can only reference other strong named assemblies.</span></span> <span data-ttu-id="4d337-112">Se la libreria non ha un nome sicuro, gli sviluppatori che stanno progettando un'applicazione o una libreria che richiede nomi sicuri non la potranno usare.</span><span class="sxs-lookup"><span data-stu-id="4d337-112">If your library isn't strong named, then you have excluded developers who are building an application or library that needs strong naming from using it.</span></span>

<span data-ttu-id="4d337-113">I vantaggi dei nomi sicuri sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d337-113">The benefits of strong naming are:</span></span>

1. <span data-ttu-id="4d337-114">Altri assembly con nome sicuro possono fare riferimento all'assembly e usarlo.</span><span class="sxs-lookup"><span data-stu-id="4d337-114">The assembly can be referenced and used by other strong-named assemblies.</span></span>
2. <span data-ttu-id="4d337-115">L'assembly può essere archiviato nella Global Assembly Cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="4d337-115">The assembly can be stored in the Global Assembly Cache (GAC).</span></span>
3. <span data-ttu-id="4d337-116">L'assembly può essere caricato affiancato ad altre versioni dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4d337-116">The assembly can be loaded side by side with other versions of the assembly.</span></span> <span data-ttu-id="4d337-117">Il caricamento dell'assembly affiancato è comunemente richiesto dalle applicazioni con architetture plug-in.</span><span class="sxs-lookup"><span data-stu-id="4d337-117">Side-by-side assembly loading is commonly required by applications with plug-in architectures.</span></span>

## <a name="create-strong-named-net-libraries"></a><span data-ttu-id="4d337-118">Creare librerie .NET con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="4d337-118">Create strong named .NET libraries</span></span>

<span data-ttu-id="4d337-119">È consigliabile usare un nome sicuro per le librerie .NET open source.</span><span class="sxs-lookup"><span data-stu-id="4d337-119">You should strong name your open-source .NET libraries.</span></span> <span data-ttu-id="4d337-120">L'uso di un nome sicuro per un assembly garantisce che la maggior parte degli utenti possa usare l'assembly e il caricamento dell'assembly in modalità strict riguarda solo .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d337-120">Strong naming an assembly ensures the most people can use it, and strict assembly loading only affects the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="4d337-121">Queste linee guida sono specifiche per le librerie .NET distribuite pubblicamente, ad esempio le librerie .NET pubblicate in NuGet.org. Il nome sicuro non è richiesto dalla maggior parte delle applicazioni .NET e non deve essere eseguito per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4d337-121">This guidance is specific to publicly distributed .NET libraries, such as .NET libraries published on NuGet.org. Strong naming is not required by most .NET applications and should not be done by default.</span></span>

<span data-ttu-id="4d337-122">✔️ prendere in considerazione la denominazione sicura degli assembly della libreria.</span><span class="sxs-lookup"><span data-stu-id="4d337-122">✔️ CONSIDER strong naming your library's assemblies.</span></span>

<span data-ttu-id="4d337-123">✔️ CONSIGLIABILE aggiungere la chiave per la denominazione sicura al sistema di controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="4d337-123">✔️ CONSIDER adding the strong naming key to your source control system.</span></span>

> <span data-ttu-id="4d337-124">Una chiave disponibile pubblicamente consente agli sviluppatori di modificare e ricompilare il codice sorgente della libreria con la stessa chiave.</span><span class="sxs-lookup"><span data-stu-id="4d337-124">A publicly available key lets developers modify and recompile your library source code with the same key.</span></span>
>
> <span data-ttu-id="4d337-125">Non rendere pubblica la chiave per la creazione di nomi sicuri se è stata usata in precedenza per concedere autorizzazioni speciali in [scenari di attendibilità parziale](../../framework/misc/using-libraries-from-partially-trusted-code.md).</span><span class="sxs-lookup"><span data-stu-id="4d337-125">You shouldn't make the strong naming key public if it has been used in the past to give special permissions in [partial-trust scenarios](../../framework/misc/using-libraries-from-partially-trusted-code.md).</span></span> <span data-ttu-id="4d337-126">In caso contrario, si potrebbero compromettere gli ambienti esistenti.</span><span class="sxs-lookup"><span data-stu-id="4d337-126">Otherwise, you might compromise existing environments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d337-127">Quando si vuole indicare l'identità dell'editore del codice, usare [Authenticode](/windows-hardware/drivers/install/authenticode) e la [firma di pacchetti NuGet](/nuget/create-packages/sign-a-package).</span><span class="sxs-lookup"><span data-stu-id="4d337-127">When the identity of the publisher of the code is desired, [Authenticode](/windows-hardware/drivers/install/authenticode) and [NuGet Package Signing](/nuget/create-packages/sign-a-package) are recommended.</span></span> <span data-ttu-id="4d337-128">Non usare la sicurezza dall'accesso di codice come prevenzione per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4d337-128">Code Access Security (CAS) should not be used as a security mitigation.</span></span>

<span data-ttu-id="4d337-129">✔️ valutare la possibilità di incrementare la versione dell'assembly solo con modifiche di versione principali per consentire agli utenti di ridurre i reindirizzamenti di binding e la frequenza di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="4d337-129">✔️ CONSIDER incrementing the assembly version on only major version changes to help users reduce binding redirects, and how often they're updated.</span></span>

> <span data-ttu-id="4d337-130">Leggere altre informazioni su [controllo delle versioni e versione degli assembly](./versioning.md#assembly-version).</span><span class="sxs-lookup"><span data-stu-id="4d337-130">Read more about [versioning and the assembly version](./versioning.md#assembly-version).</span></span>

<span data-ttu-id="4d337-131">❌ non aggiungere, rimuovere o modificare la chiave di denominazione sicura.</span><span class="sxs-lookup"><span data-stu-id="4d337-131">❌ DO NOT add, remove, or change the strong naming key.</span></span>

> <span data-ttu-id="4d337-132">Se si modifica una chiave per la creazione di nomi sicuri di un assembly, viene modificata l'identità dell'assembly e il codice compilato che lo usa non funziona più.</span><span class="sxs-lookup"><span data-stu-id="4d337-132">Modifying an assembly's strong naming key changes the assembly's identity and breaks compiled code that uses it.</span></span> <span data-ttu-id="4d337-133">Per altre informazioni, vedere [Binary breaking change](./breaking-changes.md#binary-breaking-change) (Modifica che causa un'interruzione del codice binario).</span><span class="sxs-lookup"><span data-stu-id="4d337-133">For more information, see [binary breaking changes](./breaking-changes.md#binary-breaking-change).</span></span>

<span data-ttu-id="4d337-134">❌ non pubblicare versioni con nome sicuro e senza nome sicuro della libreria.</span><span class="sxs-lookup"><span data-stu-id="4d337-134">❌ DO NOT publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="4d337-135">Ad esempio, `Contoso.Api` e `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="4d337-135">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

> <span data-ttu-id="4d337-136">La pubblicazione di due pacchetti comporta la biforcazione dell'ecosistema di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="4d337-136">Publishing two packages forks your developer eco-system.</span></span> <span data-ttu-id="4d337-137">Se un'applicazione dipende da entrambi i pacchetti, inoltre, possono verificarsi conflitti di nomi di tipo.</span><span class="sxs-lookup"><span data-stu-id="4d337-137">Also, if an application ends up depending on both packages the developer can encounter type name conflicts.</span></span> <span data-ttu-id="4d337-138">Per quanto riguarda .NET, si tratta di tipi diversi in assembly diversi.</span><span class="sxs-lookup"><span data-stu-id="4d337-138">As far as .NET is concerned they are different types in different assemblies.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4d337-139">[Precedente](cross-platform-targeting.md)
>[Successivo](nuget.md)</span><span class="sxs-lookup"><span data-stu-id="4d337-139">[Previous](cross-platform-targeting.md)
[Next](nuget.md)</span></span>
