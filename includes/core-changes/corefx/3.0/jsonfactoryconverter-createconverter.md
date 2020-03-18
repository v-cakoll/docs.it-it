---
ms.openlocfilehash: 3bce796191e0ebe6dbe4650457abe5a20c383f02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147562"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a>Firma JsonFactoryConverter.CreateConverter modificata

Per facilitare <xref:System.Text.Json.Serialization.JsonConverterFactory> la composizione <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> delle classi, il metodo è <xref:System.Text.Json.JsonSerializerOptions>stato reso pubblico e fornito un secondo argomento di tipo .

#### <a name="change-description"></a>Descrizione modifica:

La firma `CreateConverter` del metodo in .NET Core prima della versione 3.0 Preview 8 era:

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

In .NET Core 3.0 Preview 8 e versioni successive, è:In .NET Core 3.0 Preview 8 and later versions, it is:

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

Prima di questo cambiamento, era difficile comporre convertitori di fabbrica sigillati, dal momento che non c'era un modo semplice per ottenere il <xref:System.Text.Json.Serialization.JsonConverter%601> da esso. Rendere pubblico il metodo factory <xref:System.Text.Json.JsonSerializerOptions> e anche il passaggio della corrente consentono una composizione molto più flessibile.

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 8

#### <a name="recommended-action"></a>Azione consigliata

Le classi derivate devono essere aggiornate e ricompilate.

#### <a name="affected-apis"></a>API interessate

- <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
