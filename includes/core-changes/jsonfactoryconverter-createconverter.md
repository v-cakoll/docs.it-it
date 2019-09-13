---
ms.openlocfilehash: e16f0c8ede5e1a24d4fc4606c3c25225ea72e750
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70930061"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a>Firma di JsonFactoryConverter. CreateConverter modificata

Per facilitare la composizione delle <xref:System.Text.Json.Serialization.JsonConverterFactory> classi, il <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> metodo è stato reso pubblico e viene fornito un secondo argomento di <xref:System.Text.Json.JsonSerializerOptions>tipo.

#### <a name="details"></a>Dettagli

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

Prima di questa modifica, era difficile comporre convertitori di fabbrica Sealed, dal momento che non esisteva un modo <xref:System.Text.Json.Serialization.JsonConverter%601> semplice per ottenere il. Rendendo pubblico il metodo factory e passando l'oggetto corrente <xref:System.Text.Json.JsonSerializerOptions> , è possibile creare una composizione molto più flessibile.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Anteprima 8

#### <a name="recommended-action"></a>Azione consigliata

È necessario aggiornare e ricompilare le classi derivate.

#### <a name="affected-apis"></a>API interessate

[https://login.microsoftonline.com/consumers/](<xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>).

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
