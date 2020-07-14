---
title: Migrazione e compatibilità dei criteri di sicurezza dall'accesso di codice
description: Leggere un riepilogo e vedere i collegamenti relativi a migrazione e compatibilità dei criteri di sicurezza dall'accesso di codice in .NET 4.
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR policy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
ms.openlocfilehash: e5affd9d16635fa28342b5b7390a083185975f2b
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281732"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="bd4f4-103">Migrazione e compatibilità dei criteri di sicurezza dall'accesso di codice</span><span class="sxs-lookup"><span data-stu-id="bd4f4-103">Code Access Security Policy Compatibility and Migration</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="bd4f4-104">La parte relativa ai criteri di sicurezza dall'accesso di codice (CAS) è stata resa obsoleta nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-104">The policy portion of code access security (CAS) has been made obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="bd4f4-105">Di conseguenza, è possibile che si verifichino avvisi di compilazione ed eccezioni di runtime se si chiamano i tipi di criteri e i membri obsoleti in [modo esplicito](#explicit_use) o [implicito](#implicit_use) (tramite altri tipi e membri).</span><span class="sxs-lookup"><span data-stu-id="bd4f4-105">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>

<span data-ttu-id="bd4f4-106">È possibile evitare gli avvisi e gli errori nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd4f4-106">You can avoid the warnings and errors by either:</span></span>

- <span data-ttu-id="bd4f4-107">[Migrazione](#migration) alle .NET Framework 4 sostituzioni per le chiamate obsolete.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-107">[Migrating](#migration) to the .NET Framework 4 replacements for the obsolete calls.</span></span>

   <span data-ttu-id="bd4f4-108">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="bd4f4-108">\- or -</span></span>

- <span data-ttu-id="bd4f4-109">Utilizzo dell' [ \<NetFx40_LegacySecurityPolicy> elemento Configuration](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) per acconsentire esplicitamente al comportamento del criterio CAS legacy.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-109">Using the [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>

<span data-ttu-id="bd4f4-110">In questo argomento sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd4f4-110">This topic contains the following sections:</span></span>

- [<span data-ttu-id="bd4f4-111">Uso esplicito</span><span class="sxs-lookup"><span data-stu-id="bd4f4-111">Explicit Use</span></span>](#explicit_use)

- [<span data-ttu-id="bd4f4-112">Uso implicito</span><span class="sxs-lookup"><span data-stu-id="bd4f4-112">Implicit Use</span></span>](#implicit_use)

- [<span data-ttu-id="bd4f4-113">Errori e avvisi</span><span class="sxs-lookup"><span data-stu-id="bd4f4-113">Errors and Warnings</span></span>](#errors_and_warnings)

- [<span data-ttu-id="bd4f4-114">Migrazione: sostituzione delle chiamate obsolete</span><span class="sxs-lookup"><span data-stu-id="bd4f4-114">Migration: Replacement for Obsolete Calls</span></span>](#migration)

- [<span data-ttu-id="bd4f4-115">Compatibilità: uso dell'opzione legacy relativa ai criteri di sicurezza dall'accesso di codice</span><span class="sxs-lookup"><span data-stu-id="bd4f4-115">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)

<a name="explicit_use"></a>

## <a name="explicit-use"></a><span data-ttu-id="bd4f4-116">Uso esplicito</span><span class="sxs-lookup"><span data-stu-id="bd4f4-116">Explicit Use</span></span>

<span data-ttu-id="bd4f4-117">I membri che modificano direttamente i criteri di sicurezza o richiedono criteri di sicurezza dall'accesso di codice per il sandboxing sono obsoleti e comportano la generazione di errori per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-117">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>

<span data-ttu-id="bd4f4-118">Sono esempi di eventi:</span><span class="sxs-lookup"><span data-stu-id="bd4f4-118">Examples of these are:</span></span>

- <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>

- <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>

<a name="implicit_use"></a>

## <a name="implicit-use"></a><span data-ttu-id="bd4f4-119">Uso implicito</span><span class="sxs-lookup"><span data-stu-id="bd4f4-119">Implicit Use</span></span>

<span data-ttu-id="bd4f4-120">Numerosi assembly che caricano overload producono errori a causa dell'uso implicito di criteri di sicurezza dall'accesso di codice.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-120">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="bd4f4-121">Questi overload accettano un parametro <xref:System.Security.Policy.Evidence> usato per risolvere i criteri di sicurezza dall'accesso di codice e forniscono un set di autorizzazioni per un assembly.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-121">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>

<span data-ttu-id="bd4f4-122">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-122">Here are some examples.</span></span> <span data-ttu-id="bd4f4-123">Gli overload obsoleti sono quelli che accettano <xref:System.Security.Policy.Evidence> come parametro:</span><span class="sxs-lookup"><span data-stu-id="bd4f4-123">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>

- <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

<a name="errors_and_warnings"></a>

## <a name="errors-and-warnings"></a><span data-ttu-id="bd4f4-124">Errori e avvisi</span><span class="sxs-lookup"><span data-stu-id="bd4f4-124">Errors and Warnings</span></span>

<span data-ttu-id="bd4f4-125">Quando vengono usati, i tipi e i membri obsoleti producono i messaggi di errore seguenti.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-125">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="bd4f4-126">Si noti che il tipo <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> non è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-126">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>

<span data-ttu-id="bd4f4-127">Avviso in fase di compilazione:</span><span class="sxs-lookup"><span data-stu-id="bd4f4-127">Compile-time warning:</span></span>

`warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`

<span data-ttu-id="bd4f4-128">Eccezioni di runtime:</span><span class="sxs-lookup"><span data-stu-id="bd4f4-128">Run-time exception:</span></span>

<span data-ttu-id="bd4f4-129"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="bd4f4-129"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>

<a name="migration"></a>

## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="bd4f4-130">Migrazione: sostituzione delle chiamate obsolete</span><span class="sxs-lookup"><span data-stu-id="bd4f4-130">Migration: Replacement for Obsolete Calls</span></span>

### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="bd4f4-131">Determinazione del livello di attendibilità di un assembly</span><span class="sxs-lookup"><span data-stu-id="bd4f4-131">Determining an Assembly’s Trust Level</span></span>

<span data-ttu-id="bd4f4-132">I criteri di sicurezza dall'accesso di codice vengono spesso usati per determinare il livello di attendibilità o il set di autorizzazioni di un assembly o di un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-132">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="bd4f4-133">Il .NET Framework 4 espone le seguenti proprietà utili che non richiedono la risoluzione dei criteri di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="bd4f4-133">The .NET Framework 4 exposes the following useful properties that do not need to resolve security policy:</span></span>

- <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>

### <a name="application-domain-sandboxing"></a><span data-ttu-id="bd4f4-134">Sandboxing di un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="bd4f4-134">Application Domain Sandboxing</span></span>

<span data-ttu-id="bd4f4-135">Il metodo <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> viene in genere usato per il sandboxing degli assembly in un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-135">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="bd4f4-136">Il .NET Framework 4 espone i membri che non devono utilizzare a <xref:System.Security.Policy.PolicyLevel> questo scopo.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-136">The .NET Framework 4 exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="bd4f4-137">Per altre informazioni, vedere [procedura: eseguire codice parzialmente attendibile in un ambiente sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md).</span><span class="sxs-lookup"><span data-stu-id="bd4f4-137">For more information, see [How to: Run Partially Trusted Code in a Sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>

### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="bd4f4-138">Determinazione di un set di autorizzazioni ragionevoli o sicure per codice parzialmente attendibile</span><span class="sxs-lookup"><span data-stu-id="bd4f4-138">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>

<span data-ttu-id="bd4f4-139">Gli host devono spesso determinare le autorizzazioni appropriate per il sandboxing del codice ospitato.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-139">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="bd4f4-140">Prima del .NET Framework 4, i criteri CAS fornivano un modo per eseguire questa operazione con il <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-140">Before the .NET Framework 4, CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="bd4f4-141">In sostituzione, .NET Framework 4 fornisce il <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> metodo, che restituisce un set di autorizzazioni standard Safe per l'evidenza fornita.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-141">As a replacement, .NET Framework 4 provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>

### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="bd4f4-142">Scenari senza sandboxing: overload per i caricamenti di assembly</span><span class="sxs-lookup"><span data-stu-id="bd4f4-142">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>

<span data-ttu-id="bd4f4-143">Il motivo per usare un overload per il caricamento di un assembly potrebbe essere l'uso di parametri che non sono altrimenti disponibili, anziché l'esecuzione del sandboxing dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-143">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="bd4f4-144">A partire da .NET Framework 4, gli overload di caricamento degli assembly che non richiedono un <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> oggetto come parametro, ad esempio, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType> abilitano questo scenario.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-144">Starting with the .NET Framework 4, assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>

<span data-ttu-id="bd4f4-145">Per eseguire il sandboxing di un assembly, usare l'overload <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-145">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

<a name="compatibility"></a>

## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="bd4f4-146">Compatibilità: uso dell'opzione legacy relativa ai criteri di sicurezza dall'accesso di codice</span><span class="sxs-lookup"><span data-stu-id="bd4f4-146">Compatibility: Using the CAS Policy Legacy Option</span></span>

<span data-ttu-id="bd4f4-147">L' [ \<NetFx40_LegacySecurityPolicy> elemento di configurazione](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) consente di specificare che un processo o una raccolta usa i criteri CAS legacy.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-147">The [\<NetFx40_LegacySecurityPolicy> configuration element](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="bd4f4-148">Quando si abilita questo elemento, gli overload relativi ai criteri e all'evidenza funzionano in modo analogo a quanto avveniva nelle versioni precedenti del framework.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-148">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>

> [!NOTE]
> <span data-ttu-id="bd4f4-149">Il comportamento dei criteri di sicurezza dall'accesso di codice viene specificato per ogni versione runtime, pertanto la modifica di questi criteri per una versione runtime non influisce sui criteri di sicurezza dall'accesso di codice di un'altra versione.</span><span class="sxs-lookup"><span data-stu-id="bd4f4-149">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="bd4f4-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd4f4-150">See also</span></span>

- [<span data-ttu-id="bd4f4-151">Procedura: eseguire codice parzialmente attendibile in un oggetto sandbox</span><span class="sxs-lookup"><span data-stu-id="bd4f4-151">How to: Run Partially Trusted Code in a Sandbox</span></span>](how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="bd4f4-152">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="bd4f4-152">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
