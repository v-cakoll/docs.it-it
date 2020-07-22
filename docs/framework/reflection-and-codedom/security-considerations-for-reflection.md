---
title: Considerazioni sulla sicurezza in relazione alla reflection
description: Informazioni sulle considerazioni relative alla sicurezza per la reflection in .NET. Il recupero di informazioni su tipi e membri è consentito, ma l'accesso ai membri presenta restrizioni.
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], reflection
- MethodInfo parameters
- reflection, security
- partial trust,reflection
- nonpublic members
- reflection,partial trust
- link demands
ms.assetid: 42d9dc2a-8fcc-4ff3-b002-4ff260ef3dc5
ms.openlocfilehash: 0465cbd5ceb7d4f44bb6d10865fcbd17b8ed7af6
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865255"
---
# <a name="security-considerations-for-reflection"></a>Considerazioni sulla sicurezza in relazione alla reflection

La reflection consente di ottenere informazioni su tipi e membri e di accedere ai membri, vale a dire chiamare metodi e costruttori, ottenere e impostare valori di proprietà, aggiungere e rimuovere gestori eventi e così via. L'uso della reflection per ottenere informazioni su tipi e membri non presenta limitazioni. L'intero codice può usare la reflection per eseguire le attività seguenti:

- Enumerare tipi e membri ed esaminare i rispettivi metadati.

- Enumerare ed esaminare assembly e moduli.

L'uso della reflection per accedere ai membri, per contro, è soggetto a limitazioni. A partire da .NET Framework 4, è possibile usare la reflection per accedere ai membri critici per la sicurezza solo tramite il codice attendibile. Inoltre, solo un codice affidabile può usare la reflection per accedere a membri non pubblici che non sarebbero altrimenti accessibili direttamente dal codice compilato. Infine, al codice in cui viene usata la reflection per accedere a un membro critico per la sicurezza devono essere associate le autorizzazioni richieste dal membro critico per la sicurezza, come nel codice compilato.

Fatte salve le autorizzazioni necessarie, il codice può usare la reflection per eseguire i tipi di accesso seguenti:

- Accesso a membri pubblici non critici per la sicurezza.

- Accesso a membri non pubblici ai quali il codice compilato potrebbe accedere, se non critici per la sicurezza. Gli esempi di tali membri non pubblici includono:

  - Membri protetti delle classi base del codice chiamante. Nella reflection viene fatto riferimento a questa operazione con il termine accesso a livello di famiglia.

  - Membri `internal` (membri `Friend` in Visual Basic) nell'assembly del codice chiamante. Nella reflection viene fatto riferimento a questa operazione con il termine accesso a livello di assembly.

  - Membri privati di altre istanze della classe che contiene il codice chiamante.

Ad esempio, il codice eseguito in un dominio applicazione in modalità sandbox è limitato all'accesso descritto in questo elenco, a meno che il dominio dell'applicazione non conceda altre autorizzazioni.

A partire da .NET Framework 2.0 Service Pack 1, il tentativo di accedere a membri generalmente non accessibili genera una richiesta del set di concessioni dell'oggetto di destinazione più <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>. Il codice eseguito con attendibilità totale (ad esempio il codice in un'applicazione avviata dalla riga di comando) è sempre in grado di soddisfare queste autorizzazioni. Tale codice è soggetto a limitazioni per quanto concerne l'accesso a membri critici per la sicurezza, come descritto più avanti in questo articolo.

Facoltativamente, un dominio di applicazioni sandbox può concedere <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>, come descritto nella sezione [Accesso a membri generalmente non accessibili](#accessingNormallyInaccessible) più avanti in questo articolo.

<a name="accessingSecurityCritical"></a>

## <a name="accessing-security-critical-members"></a>Accesso ai membri critici per la sicurezza

Un membro è critico per la sicurezza se possiede l'attributo <xref:System.Security.SecurityCriticalAttribute>, se appartiene a un tipo che possiede l'attributo <xref:System.Security.SecurityCriticalAttribute> o se è contenuto in un assembly critico per la sicurezza. A partire da .NET Framework 4, per l'accesso ai membri critici per la sicurezza valgono le regole seguenti:

- Il codice Transparent non può usare la reflection per accedere a membri critici per la sicurezza, sebbene sia completamente attendibile. Viene generata un'eccezione <xref:System.MethodAccessException>, <xref:System.FieldAccessException> o <xref:System.TypeAccessException>.

- Il codice eseguito con attendibilità parziale è considerato Transparent.

Queste regole valgono sempre, indipendentemente dal fatto che l'accesso al membro critico per la sicurezza venga eseguito direttamente dal codice compilato o tramite reflection.

Il codice dell'applicazione eseguito dalla riga di comando viene eseguito con attendibilità totale. A condizione che non sia contrassegnato come Transparent, può usare la reflection per accedere a membri critici per la sicurezza. Quando lo stesso codice viene eseguito con attendibilità parziale, ad esempio in un dominio applicazione in modalità sandbox, il livello di attendibilità dell'assembly determina se può accedere o meno a codice critico per la sicurezza: se l'assembly è dotato di un nome sicuro ed è installato nella Global Assembly Cache, si tratta di un assembly attendibile e può chiamare membri critici per la sicurezza. Nel caso non sia attendibile, diventa Transparent anche se non è stato contrassegnato come tale e non può accedere a membri critici per la sicurezza.

Per altre informazioni sul modello di sicurezza in .NET Framework 4.5, vedere [Modifiche della sicurezza](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).

## <a name="reflection-and-transparency"></a>Reflection e trasparenza

A partire da .NET Framework 4, Common Language Runtime determina il livello di trasparenza di un tipo o di un membro sulla base di diversi fattori, tra cui i livelli di attendibilità dell'assembly e del dominio dell'applicazione. La reflection fornisce le proprietà <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Type.IsSecuritySafeCritical%2A> e <xref:System.Type.IsSecurityTransparent%2A>, che consentono di individuare il livello di trasparenza di un tipo. La tabella seguente illustra le combinazioni valide di queste proprietà.

|Livello di sicurezza|IsSecurityCritical|IsSecuritySafeCritical|IsSecurityTransparent|
|--------------------|------------------------|----------------------------|---------------------------|
|Critico|`true`|`false`|`false`|
|Critico per la sicurezza|`true`|`true`|`false`|
|Modalità trasparente|`false`|`false`|`true`|

Usare queste proprietà è molto più semplice che non esaminare le annotazioni di sicurezza di un assembly e dei suoi tipi, controllare il livello di attendibilità corrente e tentare di duplicare le regole del runtime. Lo stesso tipo, ad esempio, può essere critico per la sicurezza quando viene eseguito dalla riga di comando, oppure trasparente per la sicurezza quando viene eseguito in un dominio applicazione in modalità sandbox.

Proprietà simili sono presenti nelle classi <xref:System.Reflection.MethodBase>, <xref:System.Reflection.FieldInfo>, <xref:System.Reflection.Emit.TypeBuilder>, <xref:System.Reflection.Emit.MethodBuilder> e <xref:System.Reflection.Emit.DynamicMethod>. Per le altre astrazioni di reflection e reflection emit, gli attributi di sicurezza vengono applicati ai metodi associati; nel caso delle proprietà, ad esempio, vengono applicati alle relative funzioni di accesso.

<a name="accessingNormallyInaccessible"></a>

## <a name="accessing-members-that-are-normally-inaccessible"></a>Accesso a membri generalmente non accessibili

Per usare la reflection per richiamare membri non accessibili secondo le regole di accessibilità di Common Language Runtime, è necessario concedere al codice una delle due autorizzazioni seguenti:

- Per consentire al codice di richiamare qualsiasi membro non pubblico, è necessario concedere al codice l'autorizzazione <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType>.

  > [!NOTE]
  > Per impostazione predefinita, i criteri di sicurezza negano questa autorizzazione al codice proveniente da Internet. L'autorizzazione, infatti, non dovrebbe mai essere concessa a codice proveniente da Internet.

- Per consentire al codice di richiamare qualsiasi membro non pubblico, a condizione che il set di concessioni dell'assembly contenente il membro richiamato sia uguale o sia un sottoinsieme del set di concessioni dell'assembly contenente il codice chiamante: è necessario concedere al codice l'autorizzazione <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>.

Ad esempio, si supponga di concedere a un dominio applicazione autorizzazioni Internet più <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>, quindi di eseguire un'applicazione Internet con due assembly, A e B.

- L''assembly A può usare la reflection per accedere ai membri privati dell'assembly B, in quanto il set di concessioni dell'assembly B non include autorizzazioni che non siano state concesse anche ad A.

- L'assembly A non può usare la reflection per accedere ai membri privati degli assembly di .NET Framework, ad esempio mscorlib.dll, poiché mscorlib.dll è completamente attendibile e pertanto ha autorizzazioni che non sono state concesse all'assembly A. Viene generata una <xref:System.MemberAccessException> quando la sicurezza dall'accesso di codice esamina lo stack in fase di esecuzione.

## <a name="serialization"></a>Serializzazione

Per la serializzazione, <xref:System.Security.Permissions.SecurityPermission> con il flag <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A?displayProperty=nameWithType> consente di ottenere e impostare membri di tipi serializzabili, indipendentemente dall'accessibilità. Questa autorizzazione consente di individuare e modificare lo stato privato di un'istanza tramite codice. Oltre a disporre delle autorizzazioni appropriate, il tipo deve essere [contrassegnato](../../standard/attributes/applying-attributes.md) come serializzabile nei metadati.

## <a name="parameters-of-type-methodinfo"></a>Parametri di tipo MethodInfo

È consigliabile evitare di scrivere membri pubblici che accettano parametri <xref:System.Reflection.MethodInfo>, specialmente per codice attendibile. Tali membri potrebbero risultare più vulnerabili al codice dannoso. Si consideri ad esempio un membro pubblico in codice a elevata attendibilità che accetta un parametro <xref:System.Reflection.MethodInfo>. Si supponga che il membro pubblico chiami indirettamente il metodo <xref:System.Reflection.MethodBase.Invoke%2A> sul parametro specificato. Se il membro pubblico non esegue i controlli di autorizzazione necessari, la chiamata al metodo <xref:System.Reflection.MethodBase.Invoke%2A> riuscirà sempre, poiché il sistema di sicurezza determina l'elevata attendibilità del chiamante. Anche se il codice dannoso non dispone dell'autorizzazione per richiamare direttamente il metodo, potrà chiamarlo indirettamente tramite una chiamata al membro pubblico.

## <a name="version-information"></a>Informazioni sulla versione

- A partire da .NET Framework 4, il codice Transparent non può usare la reflection per accedere ai membri critici per la sicurezza.

- Il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> è stato introdotto in .NET Framework 2.0 Service Pack 1. Le versioni precedenti di .NET Framework richiedono il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.MemberAccess?displayProperty=nameWithType> per il codice che usa la reflection per accedere ai membri non pubblici. Questa autorizzazione non dovrebbe mai essere concessa al codice parzialmente attendibile.

- A partire da .NET Framework 2.0, l'uso della reflection per ottenere informazioni su tipi e membri non pubblici non richiede alcuna autorizzazione. Nelle versioni precedenti è necessario usare <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.TypeInformation?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedi anche

- <xref:System.Security.Permissions.ReflectionPermissionFlag>
- <xref:System.Security.Permissions.ReflectionPermission>
- <xref:System.Security.Permissions.SecurityPermission>
- [Modifiche della sicurezza](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)
- [Sicurezza dall'accesso di codice](../misc/code-access-security.md)
- [Problemi di sicurezza nella reflection emit](security-issues-in-reflection-emit.md)
- [Visualizzazione delle informazioni sul tipo](viewing-type-information.md)
- [Applicazione di attributi](../../standard/attributes/applying-attributes.md)
- [Accesso ad attributi personalizzati](accessing-custom-attributes.md)
