---
title: <supportedRuntime> elemento di configurazione - .NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: 2b0bce015216c2eaf2c35aee2d9174f109dff16e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673927"
---
# <a name="supportedruntime-element"></a>\<supportedRuntime > elemento

Specifica quale versione di common language runtime e, facoltativamente, la versione dell'applicazione .NET Framework supporta.  

[\<configuration>](../configuration-element.md)  
&nbsp;&nbsp;[\<startup>](../startup/startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**  

## <a name="syntax"></a>Sintassi

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|**version**|Attributo facoltativo.<br /><br /> Valore stringa mediante il quale viene specificata la versione di Common Language Runtime (CLR) supportata da questa applicazione. Per i valori validi del `version` dell'attributo, vedere la [i valori di "runtime version"](#version) sezione. **Nota:**  Tramite .NET Framework 3.5, il "*versione runtime*" valore assume la forma *principali*. *minori*. *Compilare*. A partire da [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], sono necessari solo i numeri delle versioni principale e secondaria (vale a dire, "v4.0" anziché "v4.0.30319"). È consigliabile la stringa più corta.|
|**sku**|Attributo facoltativo.<br /><br /> Valore stringa che specifica il codice di riferimento del prodotto (SKU), che a sua volta specifica la versione di .NET Framework supportata dall'applicazione.<br /><br /> A partire da .NET Framework 4.0, si consiglia l'uso dell'attributo `sku`.  Quando è presente, indica la versione di .NET Framework di destinazione dell'app.<br /><br /> Per i valori validi dell'attributo sku, vedere la [i valori di "sku id"](#sku) sezione.|

## <a name="remarks"></a>Note

Se il  **\<supportedRuntime >** elemento non è presente nel file di configurazione dell'applicazione, viene utilizzata la versione del runtime usata per compilare l'applicazione.

Il  **\<supportedRuntime >** elemento deve essere utilizzato da tutte le applicazioni compilate con la versione 1.1 o versione successiva del runtime. Le applicazioni create per supportare solo la versione 1.0 del runtime è necessario usare il [ \<requiredRuntime >](../startup/requiredruntime-element.md) elemento.

> [!NOTE]
> Se si usa la [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) funzione per specificare il file di configurazione, è necessario usare il `<requiredRuntime>` (elemento) per tutte le versioni del runtime. Il `<supportedRuntime>` elemento viene ignorato quando si usa [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
Per le app che supportano le versioni di runtime da .NET Framework 1.1 a 3.5, quando sono supportate più versioni, il primo elemento deve indicare la versione preferita, mentre l'ultimo elemento quella meno desiderata. Per le app che supportano il .NET Framework 4.0 o versioni successive, il `version` attributo indica la versione CLR, che è comune a di .NET Framework 4 e versioni successive, e il `sku` attributo indica la singola versione di .NET Framework che la destinazioni di App. 

Se il  **\<supportedRuntime >** elemento con la `sku` attributo è presente nel file di configurazione e la versione di .NET Framework installata è inferiore alla versione supportata specificata, l'applicazione esecuzione non riesce e verrà visualizzato invece un messaggio che richiede di installare la versione supportata. In caso contrario, l'applicazione tenta di eseguire in qualsiasi versione installata, ma potrebbe comportarsi in modo imprevisto se non è completamente compatibile con tale versione. (Le differenze di compatibilità tra versioni di .NET Framework, vedere [compatibilità delle applicazioni in .NET Framework](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility).) Pertanto, è consigliabile che si include questo elemento nel file di configurazione dell'applicazione per la diagnostica degli errori più semplice. (Il file di configurazione generato automaticamente da Visual Studio quando si crea un nuovo progetto già lo contiene.)
  
> [!NOTE]
> Se l'applicazione usa i percorsi di attivazione legacy, ad esempio la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), e si desidera che questi percorsi per attivare la versione 4 di CLR anziché una versione precedente, o se l'applicazione viene compilata con la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]ma presenta una dipendenza su un assembly in modalità mista compilato con una versione precedente di .NET Framework, non è sufficiente specificare il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] nell'elenco dei runtime supportati. Inoltre, nelle [ \<avvio > elemento](../startup/startup-element.md) nel file di configurazione, è necessario impostare la `useLegacyV2RuntimeActivationPolicy` attributo `true`. Tuttavia, se questo attributo viene impostato su `true` tutti i componenti compilati con le versioni precedenti di .NET Framework vengono eseguiti utilizzando [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] invece dei runtime con cui sono stati compilati.

È inoltre consigliabile testare l'applicazione con tutte le versioni di .NET Framework in cui possono essere eseguite.

<a name="version"></a> 
## <a name="runtime-version-values"></a>Valori di "runtime version"
Il `runtime` attributo specifica la versione di Common Language Runtime (CLR) che è necessaria per una determinata applicazione. Si noti che tutte le versioni di .NET Framework v4.x specificare il `v4.0` CLR. Nella tabella seguente sono elencati i valori validi per il *versione runtime* pari al `version` attributo.

|Versione di .NET Framework|`version` Attributo|
|----------------------------|-------------------------|
|1.0|"v1.0.3705"|
|1.1|"v1.1.4322"|
|2.0|"v2.0.50727"|
|3.0|"v2.0.50727"|
|3.5|"v2.0.50727"|
|4.0-4.8|"v4.0"|

## <a name="sku"></a> valori di "sku id"

Il `sku` attributo Usa un moniker framework di destinazione (TFM) per indicare la versione di .NET Framework che l'app ha come destinazione e necessaria per l'esecuzione. Nella tabella seguente sono elencati i valori validi supportati dal `sku` attributo, a partire da .NET Framework 4.

|Versione di .NET Framework|`sku` Attributo|
|----------------------------|---------------------|
|4.0|".NETFramework,Version=v4.0"|
|4.0, Client Profile|".NETFramework,Version=v4.0,Profile=Client"|
|4.0, aggiornamento piattaforma 1|". NETFramework, versione = v4.0.1 "|
|4.0, Client Profile, aggiornamento 1|". NETFramework, versione = v4.0.1, profilo = Client "|
|4.0, aggiornamento piattaforma 2|". NETFramework, versione = v4.0.2 "|
|4.0, Client Profile, aggiornamento 2|". NETFramework, versione = v4.0.2, profilo = Client "|
|4.0, aggiornamento piattaforma 3|". NETFramework, versione = verze 4.0.3 "|
|4.0, Client Profile, aggiornamento 3|". NETFramework, versione = verze 4.0.3, profilo = Client "|
|4.5|".NETFramework,Version=v4.5"|
|4.5.1|".NETFramework,Version=v4.5.1"|
|4.5.2|".NETFramework,Version=v4.5.2"|
|4.6|".NETFramework,Version=v4.6"|
|4.6.1|".NETFramework,Version=v4.6.1"|
|4.6.2|".NETFramework,Version=v4.6.2"|
|4.7|". NETFramework, versione = v4.7 "|
|4.7.1|". NETFramework, versione = v4.7.1 "|
|4.7.2|". NETFramework, versione = v4.7.2 "|
|4.8|". NETFramework, Version = v 4.8 "|

## <a name="example"></a>Esempio

L'esempio seguente illustra come specificare la versione di runtime in un file di configurazione. Il file di configurazione indica che l'app è destinata a .NET Framework 4.7.

```xml
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />
   </startup>
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

L'elemento può essere utilizzato nel file di configurazione dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di avvio](../startup/index.md)
- [Schema dei file di configurazione](../index.md)
- [In-Process Side-by-Side Execution](../../../deployment/in-process-side-by-side-execution.md) (Esecuzione side-by-side In-Process)