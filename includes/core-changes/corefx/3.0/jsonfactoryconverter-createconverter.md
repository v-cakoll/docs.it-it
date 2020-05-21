---
ms.openlocfilehash: 43da6233b70927e7320874772976b9e93a0bd69f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721726"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a>Firma di JsonFactoryConverter. CreateConverter modificata

Per facilitare la composizione delle <xref:System.Text.Json.Serialization.JsonConverterFactory> classi, il <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> metodo è stato reso pubblico e viene fornito un secondo argomento di tipo <xref:System.Text.Json.JsonSerializerOptions> .

#### <a name="change-description"></a>Descrizione modifica:

La firma del `CreateConverter` metodo in .NET Core precedente alla versione 3,0 Preview 8 era:

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

In .NET Core 3,0 Preview 8 e versioni successive, è:

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

Prima di questa modifica, era difficile comporre convertitori di fabbrica Sealed, dal momento che non esisteva un modo semplice per ottenere il <xref:System.Text.Json.Serialization.JsonConverter%601> . Rendendo pubblico il metodo factory e passando l'oggetto corrente, <xref:System.Text.Json.JsonSerializerOptions> è possibile creare una composizione molto più flessibile.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Anteprima 8

#### <a name="recommended-action"></a>Azione consigliata

È necessario aggiornare e ricompilare le classi derivate.

#### <a name="affected-apis"></a>API interessate

- <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>

<!-- For tool use only

#### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
