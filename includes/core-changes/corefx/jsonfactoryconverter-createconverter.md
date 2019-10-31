---
ms.openlocfilehash: 9052f509ec6df4e4b911e2f33b5c8197adb9a2c3
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198460"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a>Firma di JsonFactoryConverter. CreateConverter modificata

Per semplificare la composizione delle classi <xref:System.Text.Json.Serialization.JsonConverterFactory>, il metodo <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> è stato reso pubblico e dato un secondo argomento di tipo <xref:System.Text.Json.JsonSerializerOptions>.

#### <a name="change-description"></a>Descrizione della modifica

La firma del metodo `CreateConverter` in .NET Core prima della versione 3,0 Preview 8 era:

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

Prima di questa modifica, era difficile comporre convertitori di fabbrica Sealed, dal momento che non esisteva un modo semplice per ottenere il <xref:System.Text.Json.Serialization.JsonConverter%601>. Rendere pubblico il metodo factory e passare anche il <xref:System.Text.Json.JsonSerializerOptions> corrente consente una composizione molto più flessibile.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Anteprima 8

#### <a name="recommended-action"></a>Azione consigliata

È necessario aggiornare e ricompilare le classi derivate.

#### <a name="affected-apis"></a>API interessate

<xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
