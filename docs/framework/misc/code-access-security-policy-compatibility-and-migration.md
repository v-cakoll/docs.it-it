---
title: Migrazione e compatibilità dei criteri di sicurezza dall'accesso di codice
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR poliicy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 219b511662a2e59fb6e0e55b6630bd54015fcc79
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620097"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="2389e-102">Migrazione e compatibilità dei criteri di sicurezza dall'accesso di codice</span><span class="sxs-lookup"><span data-stu-id="2389e-102">Code Access Security Policy Compatibility and Migration</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="2389e-103">Gli aspetti relativi ai criteri di sicurezza dall'accesso di codice sono diventati obsoleti a partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2389e-103">The policy portion of code access security (CAS) has been made obsolete in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="2389e-104">Di conseguenza, potrebbero verificarsi avvisi di compilazione ed eccezioni di runtime se si chiamano i membri e tipi dei criteri obsoleti [in modo esplicito](#explicit_use) oppure [implicitamente](#implicit_use) (tramite altri tipi e membri).</span><span class="sxs-lookup"><span data-stu-id="2389e-104">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>  
  
 <span data-ttu-id="2389e-105">È possibile evitare gli avvisi e gli errori nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2389e-105">You can avoid the warnings and errors by either:</span></span>  
  
-   <span data-ttu-id="2389e-106">[Eseguire la migrazione](#migration) per il [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] sostituzioni per le chiamate obsolete.</span><span class="sxs-lookup"><span data-stu-id="2389e-106">[Migrating](#migration) to the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] replacements for the obsolete calls.</span></span>  
  
     <span data-ttu-id="2389e-107">\- oppure -</span><span class="sxs-lookup"><span data-stu-id="2389e-107">\- or -</span></span>  
  
-   <span data-ttu-id="2389e-108">Usando il [elemento di configurazione < NetFx40_LegacySecurityPolicy >](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) per acconsentire esplicitamente il comportamento dei criteri di criteri.</span><span class="sxs-lookup"><span data-stu-id="2389e-108">Using the [<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>  
  
 <span data-ttu-id="2389e-109">Di seguito sono elencate le diverse sezioni di questo argomento:</span><span class="sxs-lookup"><span data-stu-id="2389e-109">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="2389e-110">Uso esplicito</span><span class="sxs-lookup"><span data-stu-id="2389e-110">Explicit Use</span></span>](#explicit_use)  
  
-   [<span data-ttu-id="2389e-111">Uso implicito</span><span class="sxs-lookup"><span data-stu-id="2389e-111">Implicit Use</span></span>](#implicit_use)  
  
-   [<span data-ttu-id="2389e-112">Errori e avvisi</span><span class="sxs-lookup"><span data-stu-id="2389e-112">Errors and Warnings</span></span>](#errors_and_warnings)  
  
-   [<span data-ttu-id="2389e-113">Migrazione: Sostituzione delle chiamate Obsolete</span><span class="sxs-lookup"><span data-stu-id="2389e-113">Migration: Replacement for Obsolete Calls</span></span>](#migration)  
  
-   [<span data-ttu-id="2389e-114">Compatibilità: Usando l'opzione Legacy relativa ai criteri CAS</span><span class="sxs-lookup"><span data-stu-id="2389e-114">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)  
  
<a name="explicit_use"></a>   
## <a name="explicit-use"></a><span data-ttu-id="2389e-115">Uso esplicito</span><span class="sxs-lookup"><span data-stu-id="2389e-115">Explicit Use</span></span>  
 <span data-ttu-id="2389e-116">I membri che modificano direttamente i criteri di sicurezza o richiedono criteri di sicurezza dall'accesso di codice per il sandboxing sono obsoleti e comportano la generazione di errori per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2389e-116">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>  
  
 <span data-ttu-id="2389e-117">Di seguito vengono forniti alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="2389e-117">Examples of these are:</span></span>  
  
-   <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>  
  
<a name="implicit_use"></a>   
## <a name="implicit-use"></a><span data-ttu-id="2389e-118">Uso implicito</span><span class="sxs-lookup"><span data-stu-id="2389e-118">Implicit Use</span></span>  
 <span data-ttu-id="2389e-119">Numerosi assembly che caricano overload producono errori a causa dell'uso implicito di criteri di sicurezza dall'accesso di codice.</span><span class="sxs-lookup"><span data-stu-id="2389e-119">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="2389e-120">Questi overload accettano un parametro <xref:System.Security.Policy.Evidence> usato per risolvere i criteri di sicurezza dall'accesso di codice e forniscono un set di autorizzazioni per un assembly.</span><span class="sxs-lookup"><span data-stu-id="2389e-120">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>  
  
 <span data-ttu-id="2389e-121">Ecco alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="2389e-121">Here are some examples.</span></span> <span data-ttu-id="2389e-122">Gli overload obsoleti sono quelli che accettano <xref:System.Security.Policy.Evidence> come parametro:</span><span class="sxs-lookup"><span data-stu-id="2389e-122">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>  
  
-   <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
<a name="errors_and_warnings"></a>   
## <a name="errors-and-warnings"></a><span data-ttu-id="2389e-123">Errori e avvisi</span><span class="sxs-lookup"><span data-stu-id="2389e-123">Errors and Warnings</span></span>  
 <span data-ttu-id="2389e-124">Quando vengono usati, i tipi e i membri obsoleti producono i messaggi di errore seguenti.</span><span class="sxs-lookup"><span data-stu-id="2389e-124">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="2389e-125">Si noti che il tipo <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> non è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="2389e-125">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>  
  
 <span data-ttu-id="2389e-126">Avviso in fase di compilazione:</span><span class="sxs-lookup"><span data-stu-id="2389e-126">Compile-time warning:</span></span>  
  
 `warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`  
  
 <span data-ttu-id="2389e-127">Eccezioni di runtime:</span><span class="sxs-lookup"><span data-stu-id="2389e-127">Run-time exception:</span></span>  
  
 <span data-ttu-id="2389e-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="2389e-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>  
  
<a name="migration"></a>   
## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="2389e-129">Migrazione: Sostituzione delle chiamate Obsolete</span><span class="sxs-lookup"><span data-stu-id="2389e-129">Migration: Replacement for Obsolete Calls</span></span>  
  
### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="2389e-130">Determinazione del livello di attendibilità di un assembly</span><span class="sxs-lookup"><span data-stu-id="2389e-130">Determining an Assembly’s Trust Level</span></span>  
 <span data-ttu-id="2389e-131">I criteri di sicurezza dall'accesso di codice vengono spesso usati per determinare il livello di attendibilità o il set di autorizzazioni di un assembly o di un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2389e-131">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="2389e-132">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] espone le utili proprietà seguenti, che non richiedono la risoluzione dei criteri di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="2389e-132">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] exposes the following useful properties that do not need to resolve security policy:</span></span>  
  
-   <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
### <a name="application-domain-sandboxing"></a><span data-ttu-id="2389e-133">Sandboxing di un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="2389e-133">Application Domain Sandboxing</span></span>  
 <span data-ttu-id="2389e-134">Il metodo <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> viene in genere usato per il sandboxing degli assembly in un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2389e-134">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="2389e-135">Il [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] espone membri che non sono necessario usare <xref:System.Security.Policy.PolicyLevel> per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="2389e-135">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="2389e-136">Per altre informazioni, vedere [Procedura: Eseguire codice parzialmente attendibile in un ambiente Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).</span><span class="sxs-lookup"><span data-stu-id="2389e-136">For more information, see [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>  
  
### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="2389e-137">Determinazione di un set di autorizzazioni ragionevoli o sicure per codice parzialmente attendibile</span><span class="sxs-lookup"><span data-stu-id="2389e-137">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>  
 <span data-ttu-id="2389e-138">Gli host devono spesso determinare le autorizzazioni appropriate per il sandboxing del codice ospitato.</span><span class="sxs-lookup"><span data-stu-id="2389e-138">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="2389e-139">Prima la [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], il criterio CAS fornito un modo per eseguire questa operazione con il <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="2389e-139">Before the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2389e-140">Rappresenta un sostituto [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] fornisce il <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> metodo, che restituisce un'autorizzazione provvisoria, standard, impostato per l'evidenza fornita.</span><span class="sxs-lookup"><span data-stu-id="2389e-140">As a replacement, [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>  
  
### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="2389e-141">Scenari senza Sandboxing: Overload per caricamenti di Assembly</span><span class="sxs-lookup"><span data-stu-id="2389e-141">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>  
 <span data-ttu-id="2389e-142">Il motivo per usare un overload per il caricamento di un assembly potrebbe essere l'uso di parametri che non sono altrimenti disponibili, anziché l'esecuzione del sandboxing dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2389e-142">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="2389e-143">Inizia con la [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], gli overload di caricamento di assembly che non richiedono una <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> oggetto come parametro, ad esempio, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, abilitare questo scenario.</span><span class="sxs-lookup"><span data-stu-id="2389e-143">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>  
  
 <span data-ttu-id="2389e-144">Per eseguire il sandboxing di un assembly, usare l'overload <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2389e-144">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>  
  
<a name="compatibility"></a>   
## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="2389e-145">Compatibilità: Usando l'opzione Legacy relativa ai criteri CAS</span><span class="sxs-lookup"><span data-stu-id="2389e-145">Compatibility: Using the CAS Policy Legacy Option</span></span>  
 <span data-ttu-id="2389e-146">Il [elemento di configurazione < NetFx40_LegacySecurityPolicy >](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) consente di specificare che un processo o la libreria Usa criteri CAS legacy.</span><span class="sxs-lookup"><span data-stu-id="2389e-146">The [<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="2389e-147">Quando si abilita questo elemento, gli overload relativi ai criteri e all'evidenza funzionano in modo analogo a quanto avveniva nelle versioni precedenti del framework.</span><span class="sxs-lookup"><span data-stu-id="2389e-147">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2389e-148">Il comportamento dei criteri di sicurezza dall'accesso di codice viene specificato per ogni versione runtime, pertanto la modifica di questi criteri per una versione runtime non influisce sui criteri di sicurezza dall'accesso di codice di un'altra versione.</span><span class="sxs-lookup"><span data-stu-id="2389e-148">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2389e-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2389e-149">See also</span></span>
- [<span data-ttu-id="2389e-150">Procedura: Eseguire codice parzialmente attendibile in un oggetto Sandbox</span><span class="sxs-lookup"><span data-stu-id="2389e-150">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="2389e-151">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="2389e-151">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
