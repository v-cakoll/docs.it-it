---
ms.openlocfilehash: 92210f6becb5a5a43893ee0fd51ef51e2ddd7f8d
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325207"
---
### <a name="kestrel-http2-disabled-over-tls-on-incompatible-windows-versions"></a>Gheppio: HTTP/2 disabilitato su TLS in versioni incompatibili di Windows

Per abilitare HTTP/2 tramite Transport Layer Security (TLS) in Windows, è necessario soddisfare due requisiti:

- Supporto ALPN (Application-Layer Protocol negotiation), disponibile a partire da Windows 8.1 e Windows Server 2012 R2.
- Set di crittografie compatibili con HTTP/2, disponibile a partire da Windows 10 e Windows Server 2016.

Di conseguenza, il comportamento di Gheppio quando HTTP/2 su TLS è configurato è stato modificato in:

- Effettuare il downgrade a `Http1` e registrare un messaggio al `Information` livello quando [ListenOptions. HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols) è impostato su `Http1AndHttp2` . `Http1AndHttp2` è il valore predefinito di `ListenOptions.HttpProtocols`.
- Generare un `NotSupportedException` quando `ListenOptions.HttpProtocols` è impostato su `Http2` .

Per informazioni, vedere Issue [DotNet/aspnetcore # 23068](https://github.com/dotnet/aspnetcore/issues/23068).

#### <a name="version-introduced"></a>Versione introdotta

ASP.NET Core 5,0 Preview 7

#### <a name="old-behavior"></a>Comportamento precedente

La tabella seguente illustra il comportamento quando viene configurato HTTP/2 su TLS.

| Protocolli | Windows 7,<br />Windows Server 2008 R2,<br />o versioni precedenti | Windows 8,<br />Windows Server 2012 | Windows 8.1<br />Windows Server 2012 R2 | Windows 10,<br />Windows Server 2016,<br />o versione successiva |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | Generare`NotSupportedException`                   | Errore durante l'handshake TLS     | Errore durante l'handshake TLS&ast;     | Nessun errore |
| `Http1AndHttp2` | Esegui il downgrade a`Http1`                    | Esegui il downgrade a`Http1`     | Errore durante l'handshake TLS&ast;     | Nessun errore |

&ast;Configurare i pacchetti di crittografia compatibili per abilitare questi scenari.

#### <a name="new-behavior"></a>Nuovo comportamento

La tabella seguente illustra il comportamento quando viene configurato HTTP/2 su TLS.

| Protocolli | Windows 7,<br />Windows Server 2008 R2,<br />o versioni precedenti | Windows 8,<br />Windows Server 2012 | Windows 8.1<br />Windows Server 2012 R2 | Windows 10,<br />Windows Server 2016,<br />o versione successiva |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | Generare`NotSupportedException`                   | Generare`NotSupportedException`     | Genera `NotSupportedException`&ast;&ast;     | Nessun errore |
| `Http1AndHttp2` | Esegui il downgrade a`Http1`                    | Esegui il downgrade a`Http1`     | Esegui il downgrade a `Http1`&ast;&ast;     | Nessun errore |

&ast;&ast;Configurare i pacchetti di crittografia compatibili e impostare l'opzione di contesto dell'app `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` su `true` per abilitare questi scenari.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica garantisce che gli errori di compatibilità per HTTP/2 su TLS nelle versioni precedenti di Windows vengano esposti il prima e il più chiaramente possibile.

#### <a name="recommended-action"></a>Azione consigliata

Verificare che HTTP/2 su TLS sia disabilitato nelle versioni di Windows incompatibili. Windows 8.1 e Windows Server 2012 R2 sono incompatibili perché non dispongono delle crittografie necessarie per impostazione predefinita. Tuttavia, è possibile aggiornare le impostazioni di configurazione del computer per usare le crittografie compatibili con HTTP/2. Per ulteriori informazioni, vedere la pagina relativa ai pacchetti [di crittografia TLS in Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1). Dopo la configurazione, è necessario abilitare HTTP/2 su TLS in gheppio impostando il cambio di contesto dell'app `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` . Ad esempio:

```csharp
AppContext.SetSwitch("Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2", true);
```

Nessun supporto sottostante modificato. Ad esempio, HTTP/2 su TLS non ha mai funzionato in Windows 8 o Windows Server 2012. Questa modifica modifica la modalità di presentazione degli errori in questi scenari non supportati.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!--

#### Affected APIs

Not detectable via API analysis

-->
