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
# <a name="code-access-security-policy-compatibility-and-migration"></a>Migrazione e compatibilità dei criteri di sicurezza dall'accesso di codice

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

La parte relativa ai criteri di sicurezza dall'accesso di codice (CAS) è stata resa obsoleta nel .NET Framework 4. Di conseguenza, è possibile che si verifichino avvisi di compilazione ed eccezioni di runtime se si chiamano i tipi di criteri e i membri obsoleti in [modo esplicito](#explicit_use) o [implicito](#implicit_use) (tramite altri tipi e membri).

È possibile evitare gli avvisi e gli errori nei modi seguenti:

- [Migrazione](#migration) alle .NET Framework 4 sostituzioni per le chiamate obsolete.

   \- - oppure -

- Utilizzo dell' [ \<NetFx40_LegacySecurityPolicy> elemento Configuration](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) per acconsentire esplicitamente al comportamento del criterio CAS legacy.

In questo argomento sono incluse le sezioni seguenti:

- [Uso esplicito](#explicit_use)

- [Uso implicito](#implicit_use)

- [Errori e avvisi](#errors_and_warnings)

- [Migrazione: sostituzione delle chiamate obsolete](#migration)

- [Compatibilità: uso dell'opzione legacy relativa ai criteri di sicurezza dall'accesso di codice](#compatibility)

<a name="explicit_use"></a>

## <a name="explicit-use"></a>Uso esplicito

I membri che modificano direttamente i criteri di sicurezza o richiedono criteri di sicurezza dall'accesso di codice per il sandboxing sono obsoleti e comportano la generazione di errori per impostazione predefinita.

Sono esempi di eventi:

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

## <a name="implicit-use"></a>Uso implicito

Numerosi assembly che caricano overload producono errori a causa dell'uso implicito di criteri di sicurezza dall'accesso di codice. Questi overload accettano un parametro <xref:System.Security.Policy.Evidence> usato per risolvere i criteri di sicurezza dall'accesso di codice e forniscono un set di autorizzazioni per un assembly.

Di seguito sono riportati alcuni esempi. Gli overload obsoleti sono quelli che accettano <xref:System.Security.Policy.Evidence> come parametro:

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

## <a name="errors-and-warnings"></a>Errori e avvisi

Quando vengono usati, i tipi e i membri obsoleti producono i messaggi di errore seguenti. Si noti che il tipo <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> non è obsoleto.

Avviso in fase di compilazione:

`warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`

Eccezioni di runtime:

<xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`

<a name="migration"></a>

## <a name="migration-replacement-for-obsolete-calls"></a>Migrazione: sostituzione delle chiamate obsolete

### <a name="determining-an-assemblys-trust-level"></a>Determinazione del livello di attendibilità di un assembly

I criteri di sicurezza dall'accesso di codice vengono spesso usati per determinare il livello di attendibilità o il set di autorizzazioni di un assembly o di un dominio dell'applicazione. Il .NET Framework 4 espone le seguenti proprietà utili che non richiedono la risoluzione dei criteri di sicurezza:

- <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>

- <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>

### <a name="application-domain-sandboxing"></a>Sandboxing di un dominio dell'applicazione

Il metodo <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> viene in genere usato per il sandboxing degli assembly in un dominio dell'applicazione. Il .NET Framework 4 espone i membri che non devono utilizzare a <xref:System.Security.Policy.PolicyLevel> questo scopo. Per altre informazioni, vedere [procedura: eseguire codice parzialmente attendibile in un ambiente sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md).

### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a>Determinazione di un set di autorizzazioni ragionevoli o sicure per codice parzialmente attendibile

Gli host devono spesso determinare le autorizzazioni appropriate per il sandboxing del codice ospitato. Prima del .NET Framework 4, i criteri CAS fornivano un modo per eseguire questa operazione con il <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> metodo. In sostituzione, .NET Framework 4 fornisce il <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> metodo, che restituisce un set di autorizzazioni standard Safe per l'evidenza fornita.

### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a>Scenari senza sandboxing: overload per i caricamenti di assembly

Il motivo per usare un overload per il caricamento di un assembly potrebbe essere l'uso di parametri che non sono altrimenti disponibili, anziché l'esecuzione del sandboxing dell'assembly. A partire da .NET Framework 4, gli overload di caricamento degli assembly che non richiedono un <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> oggetto come parametro, ad esempio, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType> abilitano questo scenario.

Per eseguire il sandboxing di un assembly, usare l'overload <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>.

<a name="compatibility"></a>

## <a name="compatibility-using-the-cas-policy-legacy-option"></a>Compatibilità: uso dell'opzione legacy relativa ai criteri di sicurezza dall'accesso di codice

L' [ \<NetFx40_LegacySecurityPolicy> elemento di configurazione](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) consente di specificare che un processo o una raccolta usa i criteri CAS legacy. Quando si abilita questo elemento, gli overload relativi ai criteri e all'evidenza funzionano in modo analogo a quanto avveniva nelle versioni precedenti del framework.

> [!NOTE]
> Il comportamento dei criteri di sicurezza dall'accesso di codice viene specificato per ogni versione runtime, pertanto la modifica di questi criteri per una versione runtime non influisce sui criteri di sicurezza dall'accesso di codice di un'altra versione.

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Procedura: eseguire codice parzialmente attendibile in un oggetto sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Linee guida per la generazione di codice sicuro](../../standard/security/secure-coding-guidelines.md)
