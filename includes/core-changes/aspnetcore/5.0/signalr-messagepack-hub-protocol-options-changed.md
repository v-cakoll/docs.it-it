---
ms.openlocfilehash: 7a05f60cf1c04d3d73dadb54541254a83b4ea855
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507084"
---
### <a name="signalr-messagepack-hub-protocol-options-type-changed"></a><span data-ttu-id="02983-101">SignalR: tipo di opzioni del protocollo dell'hub MessagePack modificato</span><span class="sxs-lookup"><span data-stu-id="02983-101">SignalR: MessagePack Hub Protocol options type changed</span></span>

<span data-ttu-id="02983-102">Il tipo di opzioni del protocollo dell'hub MessagePack di ASP.NET Core SignalR è stato modificato `IList<MessagePack.IFormatterResolver>` da `MessagePackSerializerOptions` al tipo della libreria [MessagePack](https://www.nuget.org/packages/MessagePack) .</span><span class="sxs-lookup"><span data-stu-id="02983-102">The ASP.NET Core SignalR MessagePack Hub Protocol options type has changed from `IList<MessagePack.IFormatterResolver>` to the [MessagePack](https://www.nuget.org/packages/MessagePack) library's `MessagePackSerializerOptions` type.</span></span>

<span data-ttu-id="02983-103">Per informazioni su questa modifica, vedere [DotNet/aspnetcore # 20506](https://github.com/dotnet/aspnetcore/issues/20506).</span><span class="sxs-lookup"><span data-stu-id="02983-103">For discussion on this change, see [dotnet/aspnetcore#20506](https://github.com/dotnet/aspnetcore/issues/20506).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="02983-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="02983-104">Version introduced</span></span>

<span data-ttu-id="02983-105">5,0 Anteprima 4</span><span class="sxs-lookup"><span data-stu-id="02983-105">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="02983-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="02983-106">Old behavior</span></span>

<span data-ttu-id="02983-107">È possibile aggiungere alle opzioni come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="02983-107">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="02983-108">E sostituire le opzioni come segue:</span><span class="sxs-lookup"><span data-stu-id="02983-108">And replace the options as follows:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers = new List<MessagePack.IFormatterResolver>()
        {
            MessagePack.Resolvers.StandardResolver.Instance
        };
    });
```

#### <a name="new-behavior"></a><span data-ttu-id="02983-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="02983-109">New behavior</span></span>

<span data-ttu-id="02983-110">È possibile aggiungere alle opzioni come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="02983-110">You can add to the options as shown in the following example:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

<span data-ttu-id="02983-111">E sostituire le opzioni come segue:</span><span class="sxs-lookup"><span data-stu-id="02983-111">And replace the options as follows:</span></span>

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions = MessagePackSerializerOptions
                .Standard
                .WithResolver(MessagePack.Resolvers.StandardResolver.Instance)
                .WithSecurity(MessagePackSecurity.UntrustedData);
    });
```

#### <a name="reason-for-change"></a><span data-ttu-id="02983-112">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="02983-112">Reason for change</span></span>

<span data-ttu-id="02983-113">Questa modifica fa parte del passaggio a MessagePack V2. x, annunciato in [ASPNET/annunciations # 404](https://github.com/aspnet/Announcements/issues/404).</span><span class="sxs-lookup"><span data-stu-id="02983-113">This change is part of moving to MessagePack v2.x, which was announced in [aspnet/Announcements#404](https://github.com/aspnet/Announcements/issues/404).</span></span> <span data-ttu-id="02983-114">La libreria V2. x ha aggiunto un'API opzioni più semplice da usare e offre più funzionalità rispetto all'elenco `MessagePack.IFormatterResolver` esposto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="02983-114">The v2.x library has added an options API that's easier to use and provides more features than the list of `MessagePack.IFormatterResolver` that was exposed before.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="02983-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="02983-115">Recommended action</span></span>

<span data-ttu-id="02983-116">Questa modifica di rilievo influiscono su <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>tutti gli utenti che configurano i valori.</span><span class="sxs-lookup"><span data-stu-id="02983-116">This breaking change affects anyone who is configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span> <span data-ttu-id="02983-117">Se si usa il protocollo dell'hub MessagePack di ASP.NET Core SignalR e si modificano le opzioni, aggiornare l'utilizzo per usare la nuova API options, come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="02983-117">If you're using the ASP.NET Core SignalR MessagePack Hub Protocol and modifying the options, update your usage to use the new options API as shown above.</span></span>

#### <a name="category"></a><span data-ttu-id="02983-118">Category</span><span class="sxs-lookup"><span data-stu-id="02983-118">Category</span></span>

<span data-ttu-id="02983-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="02983-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="02983-120">API interessate</span><span class="sxs-lookup"><span data-stu-id="02983-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
