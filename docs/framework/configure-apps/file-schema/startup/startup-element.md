---
title: Elemento <startup>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: d98f8d672ed1de1a5065a0390dba29992bcc1b39
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634467"
---
# <a name="startup-element"></a>\<avvio > elemento

Specifica informazioni di avvio di common language runtime.

 \<configuration> \<startup>

## <a name="syntax"></a>Sintassi

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|Attributo facoltativo.<br /><br /> Specifica se abilitare la [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] criteri di attivazione di runtime o usare il [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] criteri di attivazione.|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>useLegacyV2RuntimeActivationPolicy attribute

|Value|Descrizione|
|-----------|-----------------|
|`true`|Abilitare [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] criteri di attivazione di runtime per il runtime scelto, ovvero per associare le tecniche di attivazione di runtime legacy (ad esempio il [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) al runtime scelto dal file di configurazione invece di limitazione di essi in CLR versione 2.0. Di conseguenza, se CLR 4 o versione successiva viene scelto dal file di configurazione, gli assembly in modalità mista creati con le versioni precedenti di .NET Framework vengono caricati con la versione di Common Language Runtime scelta. Impostazione di questo valore impedisce CLR versione 1.1 o CLR versione 2.0 di caricamento nello stesso processo, in modo efficace la disabilitazione di funzionalità side-by-side in-process.|
|`false`|Usare i criteri di attivazione predefinite per il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] e versioni successive, ovvero per consentire le tecniche di attivazione per caricare la versione 1.1 o 2.0 di CLR nel processo di runtime legacy. Impostando questo valore, gli assembly in modalità mista venga caricato in .NET Framework 4 o versioni successive, a meno che non sono state compilate con .NET Framework 4 o versione successiva. Questo valore è il valore predefinito.|

### <a name="child-elements"></a>Elementi figlio

|Elemento|Descrizione|
|-------------|-----------------|
|[\<requiredRuntime>](requiredruntime-element.md)|Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime. Le applicazioni compilate con la versione 1.1 o versioni successive devono utilizzare il  **\<supportedRuntime >** elemento.|
|[\<supportedRuntime>](supportedruntime-element.md)|Specifica le versioni di Common Language Runtime supportate dall'applicazione.|

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|

## <a name="remarks"></a>Note

 Il  **\<supportedRuntime >** elemento deve essere utilizzato da tutte le applicazioni compilate con la versione 1.1 o versione successiva del runtime. Le applicazioni create per supportare solo la versione 1.0 del runtime è necessario usare il  **\<requiredRuntime >** elemento.

 Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora le  **\<avvio >** elemento e i relativi elementi figlio.

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>L'attributo useLegacyV2RuntimeActivationPolicy

 Questo attributo è utile se l'applicazione usa i percorsi di attivazione legacy, ad esempio la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), e si desidera che questi percorsi per attivare la versione 4 di CLR anziché una versione precedente, o se l'applicazione compilato con la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] ma presenta una dipendenza da un assembly in modalità mista compilato con una versione precedente di .NET Framework. In questi scenari impostare l'attributo su `true`.

> [!NOTE]
> Impostare l'attributo su `true` impedisce il caricamento nello stesso processo, in modo efficace la disabilitazione di funzionalità side-by-side in-process CLR versione 1.1 o CLR versione 2.0 (vedere [esecuzione Side-by-Side per l'interoperabilità COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).

## <a name="example"></a>Esempio

 Nell'esempio seguente viene illustrato come specificare la versione del runtime in un file di configurazione.

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di avvio](index.md)
- [Schema dei file di configurazione](../index.md)
- [Procedura: Configurare un'app per supportare .NET Framework 4 o versioni successive](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Esecuzione side-by-Side per l'interoperabilità COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))
- [In-Process Side-by-Side Execution](../../../deployment/in-process-side-by-side-execution.md) (Esecuzione side-by-side In-Process)
