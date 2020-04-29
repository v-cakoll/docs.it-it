---
ms.openlocfilehash: 7a05f60cf1c04d3d73dadb54541254a83b4ea855
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507084"
---
### <a name="signalr-messagepack-hub-protocol-options-type-changed"></a>SignalR: tipo di opzioni del protocollo dell'hub MessagePack modificato

Il tipo di opzioni del protocollo dell'hub MessagePack di ASP.NET Core SignalR è stato modificato `IList<MessagePack.IFormatterResolver>` da `MessagePackSerializerOptions` al tipo della libreria [MessagePack](https://www.nuget.org/packages/MessagePack) .

Per informazioni su questa modifica, vedere [DotNet/aspnetcore # 20506](https://github.com/dotnet/aspnetcore/issues/20506).

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 4

#### <a name="old-behavior"></a>Comportamento precedente

È possibile aggiungere alle opzioni come illustrato nell'esempio seguente:

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.FormatterResolvers.Add(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

E sostituire le opzioni come segue:

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

#### <a name="new-behavior"></a>Nuovo comportamento

È possibile aggiungere alle opzioni come illustrato nell'esempio seguente:

```csharp
services.AddSignalR()
    .AddMessagePackProtocol(options =>
    {
        options.SerializerOptions =
            options.SerializeOptions.WithResolver(MessagePack.Resolvers.StandardResolver.Instance);
    });
```

E sostituire le opzioni come segue:

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

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica fa parte del passaggio a MessagePack V2. x, annunciato in [ASPNET/annunciations # 404](https://github.com/aspnet/Announcements/issues/404). La libreria V2. x ha aggiunto un'API opzioni più semplice da usare e offre più funzionalità rispetto all'elenco `MessagePack.IFormatterResolver` esposto in precedenza.

#### <a name="recommended-action"></a>Azione consigliata

Questa modifica di rilievo influiscono su <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>tutti gli utenti che configurano i valori. Se si usa il protocollo dell'hub MessagePack di ASP.NET Core SignalR e si modificano le opzioni, aggiornare l'utilizzo per usare la nuova API options, come illustrato in precedenza.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
