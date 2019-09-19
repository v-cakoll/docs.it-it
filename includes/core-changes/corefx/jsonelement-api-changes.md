---
ms.openlocfilehash: 98893470b64de4abf7f04817871e3053bf25b86d
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119303"
---
### <a name="jsonelement-api-changes"></a>Modifiche all'API jsonelement

A partire da .NET Core 3,0 Preview 7, <xref:System.Text.Json.JsonElement> alcune API sono state modificate per consentire un'individuazione più semplice e una maggiore usabilità.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core 3,0 Preview 7 <xref:System.Text.Json.JsonElement> le API sono cambiate come indicato di seguito per facilitare l'individuazione e una maggiore usabilità.

1. Tutti `WriteProperty` gli overload del metodo sono stati rimossi <xref:System.Text.Json.JsonElement>da. Questa operazione influisca sul codice come il seguente:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
      JsonElement root = doc.RootElement;
      root.WriteProperty(propertyNameString, writer);
      // ..
      root.WriteProperty(propertyNameSpan, writer);
      // ..
      root.WriteProperty(propertyNameJsonEncoded, writer);
      // ..
      root.WriteProperty(utf8PropertyName, writer);
      //..
   }
   ```

1. `WriteValue`è stato rinominato come <xref:System.Text.Json.JsonElement.WriteTo%2A>. Questa operazione influisca sul codice come il seguente:

```csharp
using (JsonDocument doc = JsonDocument.Parse(jsonString))
{
    JsonElement root = doc.RootElement;
    root.WriteValue(writer);
}

```

1. <xref:System.Text.Json.JsonElement.WriteTo%2A>ora genera un' <xref:System.ArgumentNullException> eccezione quando il relativo parametro `null`del metodo è.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Anteprima 7

#### <a name="recommended-action"></a>Azione consigliata

Se il codice è interessato da queste modifiche, è possibile eseguire le operazioni seguenti:

- Non è disponibile alcuna API sostitutiva `WriteProperty` per gli overload in <xref:System.Text.Json.JsonElement>. In alternativa, è possibile chiamare uno degli <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> Overload insieme <xref:System.Text.Json.JsonElement.WriteTo%2A> al metodo per acquisire lo stesso risultato. Ad esempio:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- Rinominare il `WriteValue` metodo in <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>. Il parametro del metodo rimane invariato. Il codice precedente, ad esempio, deve essere modificato nel modo seguente:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- Gestire le <xref:System.ArgumentNullException> chiamate <xref:System.Text.Json.JsonElement.WriteTo%2A> al metodo.

#### <a name="affected-apis"></a>API interessate

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
