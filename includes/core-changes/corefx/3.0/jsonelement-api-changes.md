---
ms.openlocfilehash: 79901d0b57816915ca7ea73cfe7fa3d40820434e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568216"
---
### <a name="jsonelement-api-changes"></a>Modifiche all'API JsonElement

A partire da .NET Core 3.0 Preview 7, alcune <xref:System.Text.Json.JsonElement> API sono state modificate per consentire un'individuazione più semplice e una maggiore usabilità.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 3.0 <xref:System.Text.Json.JsonElement> Preview 7, le API sono state modificate come segue per consentire un'individuazione più semplice e una maggiore usabilità.

1. Tutti `WriteProperty` gli overload del <xref:System.Text.Json.JsonElement>metodo sono stati rimossi da . Ciò influisce sul codice come il seguente:

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

1. `WriteValue`è stato <xref:System.Text.Json.JsonElement.WriteTo%2A>rinominato come . Ciò influisce sul codice come il seguente:

   ```csharp
    using (JsonDocument doc = JsonDocument.Parse(jsonString))
    {
        JsonElement root = doc.RootElement;
        root.WriteValue(writer);
    }
    ```

1. <xref:System.Text.Json.JsonElement.WriteTo%2A>ora genera <xref:System.ArgumentNullException> un quando il `null`relativo parametro del metodo è .

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 7

#### <a name="recommended-action"></a>Azione consigliata

Se il codice è interessato da queste modifiche, è possibile eseguire le operazioni seguenti:If your code is affected by these changes, you can do the following:

- Non esiste alcuna `WriteProperty` API di <xref:System.Text.Json.JsonElement>sostituzione per gli overload in . Al contrario, è <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> possibile chiamare uno <xref:System.Text.Json.JsonElement.WriteTo%2A> degli overload insieme al metodo per ottenere lo stesso risultato. Ad esempio:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- Rinominare `WriteValue` il <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>metodo in . Il parametro del metodo rimane invariato. Ad esempio, il codice precedente deve essere modificato nel modo seguente:For example, the previous code should be changed to the following:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- Gestire <xref:System.ArgumentNullException> le chiamate <xref:System.Text.Json.JsonElement.WriteTo%2A> in al metodo .

#### <a name="affected-apis"></a>API interessate

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
