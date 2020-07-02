---
ms.openlocfilehash: dd7d3e445772e4b5ec148576ccd1374d56e251bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614528"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a>Possibile deadlock quando si usano servizi rientranti

#### <a name="details"></a>Dettagli

Può verificarsi un deadlock in un servizio rientrante, che limita le istanze del servizio a un solo thread di esecuzione alla volta. Sono soggetti a questo problema i servizi che includono l'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute> seguente nel codice:

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a>Suggerimento

Per risolvere questo problema, è possibile eseguire le operazioni seguenti:

- Impostare la modalità di concorrenza del servizio su <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> oppure &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;. Ad esempio:

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- Installare l'aggiornamento più recente di .NET Framework 4.6.2 oppure eseguire l'aggiornamento a una versione successiva di .NET Framework. Viene così disabilitato il flusso di <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>. Questo comportamento è configurabile ed è equivalente all'aggiunta dell'impostazione dell'app seguente nel file di configurazione:

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

Il valore di `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` non deve mai essere impostato su `false` per i servizi Reentrant.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.6.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
