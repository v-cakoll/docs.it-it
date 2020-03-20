---
title: elemento <startup>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153731"
---
# <a name="startup-element"></a>\<elemento> all'avvio

Specifica le informazioni di avvio di Common Language Runtime.

[**\<>di configurazione**](../configuration-element.md)  
&nbsp;&nbsp;**\<>di avvio**  

## <a name="syntax"></a>Sintassi

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributes

|Attributo|Descrizione|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|Attributo facoltativo.<br /><br /> Specifica se abilitare i criteri di attivazione runtime di .NET Framework 2.0 o utilizzare i criteri di attivazione di .NET Framework 4.|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>useLegacyV2RuntimeActivationPolicy (attributo)

|valore|Descrizione|
|-----------|-----------------|
|`true`|Abilitare i criteri di attivazione runtime di .NET Framework 2.0 per il runtime scelto, ovvero associare le tecniche di attivazione runtime legacy (ad esempio la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) al runtime scelto dal file di configurazione anziché il limite in CLR versione 2.0. Pertanto, se CLR versione 4 o successiva viene scelto dal file di configurazione, gli assembly in modalità mista creati con versioni precedenti di .NET Framework vengono caricati con la versione CLR scelta. L'impostazione di questo valore impedisce il caricamento di CLR versione 1.1 o 2.0 in uno stesso processo, disabilitando in modo efficace la funzionalità side-by-side in-process.|
|`false`|Utilizzare i criteri di attivazione predefiniti per .NET Framework 4 e versioni successive, che consente alle tecniche di attivazione runtime legacy di caricare CLR versione 1.1 o 2.0 nel processo. L'impostazione di questo valore impedisce il caricamento di assembly in modalità mista in .NET Framework 4 o versioni successive, a meno che non siano compilati con .NET Framework 4 o versione successiva. Questo è il valore predefinito.|

### <a name="child-elements"></a>Elementi figlio

|Elemento|Descrizione|
|-------------|-----------------|
|[\<>runtime obbligatorio](requiredruntime-element.md)|Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime. Le applicazioni compilate con la versione di runtime 1.1 o successiva devono usare l'elemento ** \<>supportedRuntime.Applications** built with runtime version 1.1 or later should use the supportedRuntime>element.|
|[\<>supportedRuntime](supportedruntime-element.md)|Specifica le versioni di Common Language Runtime supportate dall'applicazione.|

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|

## <a name="remarks"></a>Osservazioni

 L'elemento ** \<>supportedRuntime** deve essere utilizzato da tutte le applicazioni compilate utilizzando la versione 1.1 o successiva del runtime. Le applicazioni compilate per supportare solo la versione 1.0 del runtime devono utilizzare l'elemento ** \<>requiredRuntime.**

 Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora l'elemento ** \<>di avvio** e i relativi elementi figlio.

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>Attributo useLegacyV2RuntimeActivationPolicy

 Questo attributo è utile se l'applicazione utilizza percorsi di attivazione legacy, ad esempio la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), e si desidera che tali percorsi attivino la versione 4 di CLR anziché una versione precedente oppure se l'applicazione viene compilata con .NET Framework 4 ma ha una dipendenza da un assembly in modalità mista compilato con una versione precedente di .NET Framework. In questi scenari, impostare l'attributo su `true`.

> [!NOTE]
> L'impostazione `true` dell'attributo su impedisce il caricamento di CLR versione 1.1 o 2.0 in uno stesso processo, disabilitando in modo efficace la funzionalità side-by-side in-process (vedere [Esecuzione side-by-side per interoperabilità COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).

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
- [Schema del file di configurazione](../index.md)
- [Procedura: configurare un'app per il supporto di .NET Framework 4 o versioni successiveHow to: Configure an app to support .NET Framework 4 or versioni successive](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Esecuzione side-by-side per l'interoperabilità COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))
- [In-Process Side-by-Side Execution](../../../deployment/in-process-side-by-side-execution.md) (Esecuzione side-by-side In-Process)
