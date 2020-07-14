---
ms.openlocfilehash: d75dc2caa3a002b9d34ac74f2c5c5e192281c0df
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281302"
---
### <a name="default-activityidformat-is-w3c"></a>Il valore predefinito di ActivityIdFormat è W3C

Il formato dell'identificatore predefinito per Activity ( <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> ) è Now <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType> .

#### <a name="change-description"></a>Descrizione modifica:

Il formato dell'ID attività W3C è stato introdotto in .NET Core 3,0 come alternativa al formato ID gerarchico. Tuttavia, per mantenere la compatibilità, il formato W3C non è stato impostato come predefinito fino a .NET 5,0. Il valore predefinito è stato modificato in .NET 5,0 perché il [formato W3C è stato ratificato ed è stata](https://www.w3.org/TR/trace-context/) acquisita la trazione tra più implementazioni del linguaggio.

Se l'app è destinata a una piattaforma diversa da .NET 5,0 o versione successiva, si verificherà il comportamento precedente, dove <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> è il formato predefinito. Questa impostazione predefinita si applica alle piattaforme Net45 +, netstandard 1.1 + e netcoreapp (1. x, 2. x e 3. x). In .NET 5,0 e versioni successive, <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> è impostato su <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType> .

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 7

#### <a name="recommended-action"></a>Azione consigliata

Se l'applicazione è indipendente dall'identificatore utilizzato per la traccia distribuita, non è necessaria alcuna azione. Le librerie come ASP.NET Core e <xref:System.Net.Http.HttpClient> possono utilizzare o propagare entrambe le versioni di <xref:System.Diagnostics.ActivityIdFormat> .

Se è necessaria l'interoperabilità con i sistemi esistenti o se i sistemi correnti si basano sul formato dell'identificatore, è possibile mantenere il comportamento precedente impostando <xref:System.Diagnostics.Activity.DefaultIdFormat> su <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType> . In alternativa, è possibile impostare un'opzione AppContext in uno dei tre modi seguenti:

- Nel file di progetto.

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Diagnostics.DefaultActivityIdFormatIsHierarchial" Value="true" />
  </ItemGroup>
  ```

- Nel *runtimeconfig.jssu* file.

  ```json
  {
      "runtimeOptions": {
          "configProperties": {
              "System.Diagnostics.DefaultActivityIdFormatIsHierarchial": true
          }
      }
  }
  ```

- Tramite una variabile di ambiente.

  Impostare `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` su `true` o 1.

#### <a name="category"></a>Categoria

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->
