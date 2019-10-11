---
ms.openlocfilehash: 8a92a426ac2c5eee6fba40bfc46281420466d648
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237385"
---
### <a name="jsonelement-api-changes"></a>Modifiche all'API jsonelement

A partire da .NET Core 3,0 Preview 7, alcune API <xref:System.Text.Json.JsonElement> sono state modificate per consentire un'individuazione più semplice e una maggiore usabilità.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core 3,0 Preview 7, le API <xref:System.Text.Json.JsonElement> sono cambiate come indicato di seguito per facilitare l'individuazione e una maggiore usabilità.

1. Tutti gli overload del metodo @no__t 0 sono stati rimossi da <xref:System.Text.Json.JsonElement>. Questa operazione influisca sul codice come il seguente:

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

1. `WriteValue` è stato rinominato come <xref:System.Text.Json.JsonElement.WriteTo%2A>. Questa operazione influisca sul codice come il seguente:

   ```csharp
    using (JsonDocument doc = JsonDocument.Parse(jsonString))
    {
        JsonElement root = doc.RootElement;
        root.WriteValue(writer);
    }
    ```

1. <xref:System.Text.Json.JsonElement.WriteTo%2A> genera ora un <xref:System.ArgumentNullException> quando il relativo parametro del metodo è `null`.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Anteprima 7

#### <a name="recommended-action"></a>Azione consigliata

Se il codice è interessato da queste modifiche, è possibile eseguire le operazioni seguenti:

- Non è disponibile alcuna API sostitutiva per gli overload `WriteProperty` in <xref:System.Text.Json.JsonElement>. È invece possibile chiamare uno degli overload <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> insieme al metodo <xref:System.Text.Json.JsonElement.WriteTo%2A> per acquisire lo stesso risultato. Esempio:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- Rinominare il metodo `WriteValue` per <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>. Il parametro del metodo rimane invariato. Il codice precedente, ad esempio, deve essere modificato nel modo seguente:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- Gestire il <xref:System.ArgumentNullException> nelle chiamate al metodo <xref:System.Text.Json.JsonElement.WriteTo%2A>.

#### <a name="affected-apis"></a>API interessate

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
