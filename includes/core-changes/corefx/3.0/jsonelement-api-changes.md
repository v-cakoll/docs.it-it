---
ms.openlocfilehash: 79901d0b57816915ca7ea73cfe7fa3d40820434e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568216"
---
### <a name="jsonelement-api-changes"></a><span data-ttu-id="a7319-101">Modifiche all'API JsonElement</span><span class="sxs-lookup"><span data-stu-id="a7319-101">JsonElement API changes</span></span>

<span data-ttu-id="a7319-102">A partire da .NET Core 3.0 Preview 7, alcune <xref:System.Text.Json.JsonElement> API sono state modificate per consentire un'individuazione più semplice e una maggiore usabilità.</span><span class="sxs-lookup"><span data-stu-id="a7319-102">Starting with .NET Core 3.0 Preview 7, some <xref:System.Text.Json.JsonElement> APIs have changed to allow for easier discovery and greater usability.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a7319-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="a7319-103">Change description</span></span>

<span data-ttu-id="a7319-104">In .NET Core 3.0 <xref:System.Text.Json.JsonElement> Preview 7, le API sono state modificate come segue per consentire un'individuazione più semplice e una maggiore usabilità.</span><span class="sxs-lookup"><span data-stu-id="a7319-104">In .NET Core 3.0 Preview 7, <xref:System.Text.Json.JsonElement> APIs have changed as follows to allow for easier discovery and greater usability.</span></span>

1. <span data-ttu-id="a7319-105">Tutti `WriteProperty` gli overload del <xref:System.Text.Json.JsonElement>metodo sono stati rimossi da .</span><span class="sxs-lookup"><span data-stu-id="a7319-105">All `WriteProperty` method overloads were removed from <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="a7319-106">Ciò influisce sul codice come il seguente:</span><span class="sxs-lookup"><span data-stu-id="a7319-106">This affects code such as the following:</span></span>

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

1. <span data-ttu-id="a7319-107">`WriteValue`è stato <xref:System.Text.Json.JsonElement.WriteTo%2A>rinominato come .</span><span class="sxs-lookup"><span data-stu-id="a7319-107">`WriteValue` was renamed as <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span></span> <span data-ttu-id="a7319-108">Ciò influisce sul codice come il seguente:</span><span class="sxs-lookup"><span data-stu-id="a7319-108">This affects code such as the following:</span></span>

   ```csharp
    using (JsonDocument doc = JsonDocument.Parse(jsonString))
    {
        JsonElement root = doc.RootElement;
        root.WriteValue(writer);
    }
    ```

1. <span data-ttu-id="a7319-109"><xref:System.Text.Json.JsonElement.WriteTo%2A>ora genera <xref:System.ArgumentNullException> un quando il `null`relativo parametro del metodo è .</span><span class="sxs-lookup"><span data-stu-id="a7319-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> now throws an <xref:System.ArgumentNullException> when its method parameter is `null`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a7319-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="a7319-110">Version introduced</span></span>

<span data-ttu-id="a7319-111">3.0 Anteprima 7</span><span class="sxs-lookup"><span data-stu-id="a7319-111">3.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a7319-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="a7319-112">Recommended action</span></span>

<span data-ttu-id="a7319-113">Se il codice è interessato da queste modifiche, è possibile eseguire le operazioni seguenti:If your code is affected by these changes, you can do the following:</span><span class="sxs-lookup"><span data-stu-id="a7319-113">If your code is affected by these changes, you can do the following:</span></span>

- <span data-ttu-id="a7319-114">Non esiste alcuna `WriteProperty` API di <xref:System.Text.Json.JsonElement>sostituzione per gli overload in .</span><span class="sxs-lookup"><span data-stu-id="a7319-114">There is no replacement API for the `WriteProperty` overloads in <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="a7319-115">Al contrario, è <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> possibile chiamare uno <xref:System.Text.Json.JsonElement.WriteTo%2A> degli overload insieme al metodo per ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="a7319-115">Instead, you can call one of the <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> overloads along with the <xref:System.Text.Json.JsonElement.WriteTo%2A> method to achieve the same result.</span></span> <span data-ttu-id="a7319-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a7319-116">For example:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="a7319-117">Rinominare `WriteValue` il <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>metodo in .</span><span class="sxs-lookup"><span data-stu-id="a7319-117">Rename the `WriteValue` method to <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>.</span></span> <span data-ttu-id="a7319-118">Il parametro del metodo rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="a7319-118">The method parameter remains unchanged.</span></span> <span data-ttu-id="a7319-119">Ad esempio, il codice precedente deve essere modificato nel modo seguente:For example, the previous code should be changed to the following:</span><span class="sxs-lookup"><span data-stu-id="a7319-119">For example, the previous code should be changed to the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="a7319-120">Gestire <xref:System.ArgumentNullException> le chiamate <xref:System.Text.Json.JsonElement.WriteTo%2A> in al metodo .</span><span class="sxs-lookup"><span data-stu-id="a7319-120">Handle the <xref:System.ArgumentNullException> in calls to the <xref:System.Text.Json.JsonElement.WriteTo%2A> method.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a7319-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="a7319-121">Affected APIs</span></span>

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
