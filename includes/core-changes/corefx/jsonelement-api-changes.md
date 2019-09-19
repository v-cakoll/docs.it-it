---
ms.openlocfilehash: 98893470b64de4abf7f04817871e3053bf25b86d
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119303"
---
### <a name="jsonelement-api-changes"></a><span data-ttu-id="1f5b9-101">Modifiche all'API jsonelement</span><span class="sxs-lookup"><span data-stu-id="1f5b9-101">JsonElement API changes</span></span>

<span data-ttu-id="1f5b9-102">A partire da .NET Core 3,0 Preview 7, <xref:System.Text.Json.JsonElement> alcune API sono state modificate per consentire un'individuazione più semplice e una maggiore usabilità.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-102">Starting with .NET Core 3.0 Preview 7, some <xref:System.Text.Json.JsonElement> APIs have changed to allow for easier discovery and greater usability.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1f5b9-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="1f5b9-103">Change description</span></span>

<span data-ttu-id="1f5b9-104">In .NET Core 3,0 Preview 7 <xref:System.Text.Json.JsonElement> le API sono cambiate come indicato di seguito per facilitare l'individuazione e una maggiore usabilità.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-104">In .NET Core 3.0 Preview 7, <xref:System.Text.Json.JsonElement> APIs have changed as follows to allow for easier discovery and greater usability.</span></span>

1. <span data-ttu-id="1f5b9-105">Tutti `WriteProperty` gli overload del metodo sono stati rimossi <xref:System.Text.Json.JsonElement>da.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-105">All `WriteProperty` method overloads were removed from <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="1f5b9-106">Questa operazione influisca sul codice come il seguente:</span><span class="sxs-lookup"><span data-stu-id="1f5b9-106">This affects code such as the following:</span></span>

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

1. <span data-ttu-id="1f5b9-107">`WriteValue`è stato rinominato come <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-107">`WriteValue` was renamed as <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span></span> <span data-ttu-id="1f5b9-108">Questa operazione influisca sul codice come il seguente:</span><span class="sxs-lookup"><span data-stu-id="1f5b9-108">This affects code such as the following:</span></span>

```csharp
using (JsonDocument doc = JsonDocument.Parse(jsonString))
{
    JsonElement root = doc.RootElement;
    root.WriteValue(writer);
}

```

1. <span data-ttu-id="1f5b9-109"><xref:System.Text.Json.JsonElement.WriteTo%2A>ora genera un' <xref:System.ArgumentNullException> eccezione quando il relativo parametro `null`del metodo è.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> now throws an <xref:System.ArgumentNullException> when its method parameter is `null`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1f5b9-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="1f5b9-110">Version introduced</span></span>

<span data-ttu-id="1f5b9-111">3,0 Anteprima 7</span><span class="sxs-lookup"><span data-stu-id="1f5b9-111">3.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1f5b9-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="1f5b9-112">Recommended action</span></span>

<span data-ttu-id="1f5b9-113">Se il codice è interessato da queste modifiche, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f5b9-113">If your code is affected by these changes, you can do the following:</span></span>

- <span data-ttu-id="1f5b9-114">Non è disponibile alcuna API sostitutiva `WriteProperty` per gli overload in <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-114">There is no replacement API for the `WriteProperty` overloads in <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="1f5b9-115">In alternativa, è possibile chiamare uno degli <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> Overload insieme <xref:System.Text.Json.JsonElement.WriteTo%2A> al metodo per acquisire lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-115">Instead, you can call one of the <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> overloads along with the <xref:System.Text.Json.JsonElement.WriteTo%2A> method to achive the same result.</span></span> <span data-ttu-id="1f5b9-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1f5b9-116">For example:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="1f5b9-117">Rinominare il `WriteValue` metodo in <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-117">Rename the `WriteValue` method to <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>.</span></span> <span data-ttu-id="1f5b9-118">Il parametro del metodo rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-118">The method parameter remains unchanged.</span></span> <span data-ttu-id="1f5b9-119">Il codice precedente, ad esempio, deve essere modificato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1f5b9-119">For example, the previous code should be changed to the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="1f5b9-120">Gestire le <xref:System.ArgumentNullException> chiamate <xref:System.Text.Json.JsonElement.WriteTo%2A> al metodo.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-120">Handle the <xref:System.ArgumentNullException> in calls to the <xref:System.Text.Json.JsonElement.WriteTo%2A> method.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1f5b9-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="1f5b9-121">Affected APIs</span></span>

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
