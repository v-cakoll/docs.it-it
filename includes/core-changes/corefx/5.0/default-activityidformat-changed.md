---
ms.openlocfilehash: d75dc2caa3a002b9d34ac74f2c5c5e192281c0df
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281302"
---
### <a name="default-activityidformat-is-w3c"></a><span data-ttu-id="59218-101">Il valore predefinito di ActivityIdFormat è W3C</span><span class="sxs-lookup"><span data-stu-id="59218-101">Default ActivityIdFormat is W3C</span></span>

<span data-ttu-id="59218-102">Il formato dell'identificatore predefinito per Activity ( <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> ) è Now <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="59218-102">The default identifier format for activity (<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>) is now <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="59218-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="59218-103">Change description</span></span>

<span data-ttu-id="59218-104">Il formato dell'ID attività W3C è stato introdotto in .NET Core 3,0 come alternativa al formato ID gerarchico.</span><span class="sxs-lookup"><span data-stu-id="59218-104">The W3C activity ID format was introduced in .NET Core 3.0 as an alternative to the hierarchical ID format.</span></span> <span data-ttu-id="59218-105">Tuttavia, per mantenere la compatibilità, il formato W3C non è stato impostato come predefinito fino a .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="59218-105">However, to preserve compatibility, the W3C format wasn't made the default until .NET 5.0.</span></span> <span data-ttu-id="59218-106">Il valore predefinito è stato modificato in .NET 5,0 perché il [formato W3C è stato ratificato ed è stata](https://www.w3.org/TR/trace-context/) acquisita la trazione tra più implementazioni del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="59218-106">The default was changed in .NET 5.0 because the [W3C format has been ratified](https://www.w3.org/TR/trace-context/) and gained traction across multiple language implementations.</span></span>

<span data-ttu-id="59218-107">Se l'app è destinata a una piattaforma diversa da .NET 5,0 o versione successiva, si verificherà il comportamento precedente, dove <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> è il formato predefinito.</span><span class="sxs-lookup"><span data-stu-id="59218-107">If your app targets a platform other than .NET 5.0 or later, it will experience the old behavior, where <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> is the default format.</span></span> <span data-ttu-id="59218-108">Questa impostazione predefinita si applica alle piattaforme Net45 +, netstandard 1.1 + e netcoreapp (1. x, 2. x e 3. x).</span><span class="sxs-lookup"><span data-stu-id="59218-108">This default applies to platforms net45+, netstandard1.1+, and netcoreapp (1.x, 2.x, and 3.x).</span></span> <span data-ttu-id="59218-109">In .NET 5,0 e versioni successive, <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> è impostato su <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="59218-109">In .NET 5.0 and later, <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> is set to <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="59218-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="59218-110">Version introduced</span></span>

<span data-ttu-id="59218-111">5,0 Anteprima 7</span><span class="sxs-lookup"><span data-stu-id="59218-111">5.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="59218-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="59218-112">Recommended action</span></span>

<span data-ttu-id="59218-113">Se l'applicazione è indipendente dall'identificatore utilizzato per la traccia distribuita, non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="59218-113">If your application is agnostic to the identifier that's used for distributed tracing, no action is needed.</span></span> <span data-ttu-id="59218-114">Le librerie come ASP.NET Core e <xref:System.Net.Http.HttpClient> possono utilizzare o propagare entrambe le versioni di <xref:System.Diagnostics.ActivityIdFormat> .</span><span class="sxs-lookup"><span data-stu-id="59218-114">Libraries such as ASP.NET Core and <xref:System.Net.Http.HttpClient> can consume or propagate both versions of the <xref:System.Diagnostics.ActivityIdFormat>.</span></span>

<span data-ttu-id="59218-115">Se è necessaria l'interoperabilità con i sistemi esistenti o se i sistemi correnti si basano sul formato dell'identificatore, è possibile mantenere il comportamento precedente impostando <xref:System.Diagnostics.Activity.DefaultIdFormat> su <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="59218-115">If you require interoperability with existing systems, or current systems rely on the format of the identifier, you can preserve the old behavior by setting <xref:System.Diagnostics.Activity.DefaultIdFormat> to <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>.</span></span> <span data-ttu-id="59218-116">In alternativa, è possibile impostare un'opzione AppContext in uno dei tre modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="59218-116">Alternatively, you can set an AppContext switch in one of three ways:</span></span>

- <span data-ttu-id="59218-117">Nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="59218-117">In the project file.</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Diagnostics.DefaultActivityIdFormatIsHierarchial" Value="true" />
  </ItemGroup>
  ```

- <span data-ttu-id="59218-118">Nel *runtimeconfig.jssu* file.</span><span class="sxs-lookup"><span data-stu-id="59218-118">In the *runtimeconfig.json* file.</span></span>

  ```json
  {
      "runtimeOptions": {
          "configProperties": {
              "System.Diagnostics.DefaultActivityIdFormatIsHierarchial": true
          }
      }
  }
  ```

- <span data-ttu-id="59218-119">Tramite una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="59218-119">Through an environment variable.</span></span>

  <span data-ttu-id="59218-120">Impostare `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` su `true` o 1.</span><span class="sxs-lookup"><span data-stu-id="59218-120">Set `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` to `true` or 1.</span></span>

#### <a name="category"></a><span data-ttu-id="59218-121">Categoria</span><span class="sxs-lookup"><span data-stu-id="59218-121">Category</span></span>

<span data-ttu-id="59218-122">Principali librerie .NET</span><span class="sxs-lookup"><span data-stu-id="59218-122">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="59218-123">API interessate</span><span class="sxs-lookup"><span data-stu-id="59218-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->
