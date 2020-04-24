---
title: <supportedRuntime>elemento Configuration-.NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: e16eb098db4bce115a5f1e043829eb272c952860
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153698"
---
# <a name="supportedruntime-element"></a>\<elemento> supportedRuntime

Specifica la versione di Common Language Runtime e, facoltativamente, la versione di .NET Framework supportata dall'applicazione.  

[\<>di configurazione](../configuration-element.md)  
&nbsp;&nbsp;[\<>di avvio](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<>supportedRuntime**  

## <a name="syntax"></a>Sintassi

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a>Attributes

|Attributo|Description|
|---------------|-----------------|
|**version**|Attributo facoltativo.<br /><br /> Valore stringa mediante il quale viene specificata la versione di Common Language Runtime (CLR) supportata da questa applicazione. Per i valori validi dell' `version` attributo, vedere la sezione relativa ai [valori di "versione runtime"](#version) . **Nota:**  Tramite il .NET Framework 3,5, il valore "*versione runtime*" assume il formato *principale*. *minore*. *compilazione*. A partire da .NET Framework 4, sono necessari solo i numeri di versione principale e secondaria (ovvero "v 4.0" invece di "v 4.0.30319"). È consigliabile la stringa più corta.|
|**SKU**|Attributo facoltativo.<br /><br /> Valore stringa che specifica il codice di riferimento del prodotto (SKU), che a sua volta specifica la versione di .NET Framework supportata dall'applicazione.<br /><br /> A partire da .NET Framework 4.0, si consiglia l'uso dell'attributo `sku`.  Quando è presente, indica la versione di .NET Framework di destinazione dell'app.<br /><br /> Per i valori validi dell'attributo SKU, vedere la sezione relativa ai [valori "SKU ID"](#sku) .|

## <a name="remarks"></a>Osservazioni

Se l' ** \<elemento>supportedRuntime** non è presente nel file di configurazione dell'applicazione, viene utilizzata la versione del runtime utilizzata per compilare l'applicazione.

L' ** \<elemento>supportedRuntime** deve essere usato da tutte le applicazioni compilate con la versione 1,1 o successive del runtime. Le applicazioni compilate per supportare solo la versione 1,0 del runtime devono usare l' [ \<elemento requiredRuntime>](../startup/requiredruntime-element.md) .

> [!NOTE]
> Se si usa la funzione [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) per specificare il file di configurazione, è necessario usare `<requiredRuntime>` l'elemento per tutte le versioni del runtime. L' `<supportedRuntime>` elemento viene ignorato quando si utilizza [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
Per le app che supportano le versioni di runtime da .NET Framework 1.1 a 3.5, quando sono supportate più versioni, il primo elemento deve indicare la versione preferita, mentre l'ultimo elemento quella meno desiderata. Per le app che supportano il .NET Framework 4,0 o versioni successive, `version` l'attributo indica la versione CLR, che è comune a .NET Framework 4 e versioni successive, e l' `sku` attributo indica la versione .NET Framework singola a cui è destinata l'app.

Se il ** \<>elemento supportedRuntime** con l' `sku` attributo è presente nel file di configurazione e la versione .NET Framework installata è inferiore alla versione supportata specificata, l'esecuzione dell'applicazione non riesce e viene visualizzato un messaggio che richiede di installare la versione supportata. In caso contrario, l'applicazione tenterà di eseguire su qualsiasi versione installata, ma potrebbe comportarsi in modo imprevisto se non è completamente compatibile con tale versione. Per le differenze di compatibilità tra le versioni di .NET Framework, vedere [compatibilità delle applicazioni nella .NET Framework](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility). È pertanto consigliabile includere questo elemento nel file di configurazione dell'applicazione per semplificare la diagnostica degli errori. Il file di configurazione generato automaticamente da Visual Studio quando si crea un nuovo progetto lo contiene già.
  
> [!NOTE]
> Se l'applicazione utilizza percorsi di attivazione legacy, ad esempio la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), e si desidera che tali percorsi attivino la versione 4 di CLR anziché una versione precedente o se l'applicazione viene compilata con il .NET Framework 4 ma ha una dipendenza da un assembly in modalità mista compilato con una versione precedente del .NET Framework, non è sufficiente specificare il .NET Framework 4 nell'elenco dei runtime supportati. Inoltre, nell' [ \<elemento> di avvio](../startup/startup-element.md) nel file di configurazione, è necessario impostare l' `useLegacyV2RuntimeActivationPolicy` attributo su `true`. Tuttavia, l'impostazione di questo `true` attributo su significa che tutti i componenti compilati con le versioni precedenti del .NET Framework vengono eseguiti usando il .NET Framework 4 invece dei runtime con cui sono stati compilati.

È inoltre consigliabile testare l'applicazione con tutte le versioni di .NET Framework in cui possono essere eseguite.

<a name="version"></a>
## <a name="runtime-version-values"></a>Valori di "runtime version"
L' `runtime` attributo specifica la versione di Common Language Runtime (CLR) richiesta per una determinata applicazione. Si noti che tutte le `v4.0` versioni .NET Framework V4. x specificano CLR. Nella tabella seguente sono elencati i valori validi per il valore della *versione runtime* dell' `version` attributo.

|Versione di .NET Framework|Attributo `version`|
|----------------------------|-------------------------|
|1.0|"v1.0.3705"|
|1.1|"v1.1.4322"|
|2.0|"v2.0.50727"|
|3.0|"v2.0.50727"|
|3,5|"v2.0.50727"|
|4.0-4.8|"v4.0"|

## <a name="sku-id-values"></a><a name="sku"></a>valori "SKU ID"

L' `sku` attributo usa un moniker del Framework di destinazione (TFM) per indicare la versione del .NET Framework cui l'app è destinata e richiede l'esecuzione. Nella tabella seguente sono elencati i valori validi supportati dall' `sku` attributo, a partire da .NET Framework 4.

|Versione di .NET Framework|Attributo `sku`|
|----------------------------|---------------------|
|4.0|".NETFramework,Version=v4.0"|
|4.0, Client Profile|".NETFramework,Version=v4.0,Profile=Client"|
|4.0, aggiornamento piattaforma 1|". NETFramework, Version = v 4.0.1 "|
|4.0, Client Profile, aggiornamento 1|". NETFramework, Version = v 4.0.1, profile = client "|
|4.0, aggiornamento piattaforma 2|". NETFramework, Version = v 4.0.2 "|
|4.0, Client Profile, aggiornamento 2|". NETFramework, Version = v 4.0.2, profile = client "|
|4.0, aggiornamento piattaforma 3|". NETFramework, Version = v 4.0.3 "|
|4.0, Client Profile, aggiornamento 3|". NETFramework, Version = v 4.0.3, profile = client "|
|4.5|".NETFramework,Version=v4.5"|
|4.5.1|".NETFramework,Version=v4.5.1"|
|4.5.2|".NETFramework,Version=v4.5.2"|
|4.6|".NETFramework,Version=v4.6"|
|4.6.1|".NETFramework,Version=v4.6.1"|
|4.6.2|". NETFramework, Version = v 4.6.2 "|
|4.7|". NETFramework, Version = v 4.7 "|
|4.7.1|". NETFramework, Version = v 4.7.1 "|
|4.7.2|". NETFramework, Version = v 4.7.2 "|
|4.8|". NETFramework, Version = v 4.8 "|

## <a name="example"></a>Esempio

L'esempio seguente illustra come specificare la versione di runtime in un file di configurazione. Il file di configurazione indica che l'app è destinata al .NET Framework 4,7.

```xml
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />
   </startup>
</configuration>
```

## <a name="configuration-file"></a>File di configurazione

L'elemento può essere utilizzato nel file di configurazione dell'applicazione.

## <a name="see-also"></a>Vedi anche

- [Schema delle impostazioni di avvio](../startup/index.md)
- [Schema del file di configurazione](../index.md)
- [In-Process Side-by-Side Execution](../../../deployment/in-process-side-by-side-execution.md) (Esecuzione side-by-side In-Process)
