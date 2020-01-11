---
ms.openlocfilehash: 1d8bcaf68d44f27642048c1c207b52c55b604690
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902016"
---
### <a name="signalr-handshakeprotocolsuccesshandshakedata-replaced"></a>SignalR: HandshakeProtocol. SuccessHandshakeData sostituito

Il campo [HandshakeProtocol. SuccessHandshakeData](https://github.com/dotnet/aspnetcore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) è stato rimosso e sostituito con un metodo helper che genera una risposta di handshake riuscita data una `IHubProtocol`specifica.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

`HandshakeProtocol.SuccessHandshakeData` è un campo di `public static ReadOnlyMemory<byte>`.

#### <a name="new-behavior"></a>Nuovo comportamento

`HandshakeProtocol.SuccessHandshakeData` è stato sostituito da un `static` `GetSuccessfulHandshake(IHubProtocol protocol)` metodo che restituisce un `ReadOnlyMemory<byte>` basato sul protocollo specificato.

#### <a name="reason-for-change"></a>Motivo della modifica

Sono stati aggiunti ulteriori campi alla _risposta_ di handshake che non sono costanti e cambiano a seconda del protocollo selezionato.

#### <a name="recommended-action"></a>Azione consigliata

nessuna. Questo tipo non è progettato per essere usato dal codice utente. È `public`, quindi può essere condiviso tra il server SignalR e il client. Può anche essere usato dai client SignalR scritti in .NET. **Gli utenti** di SignalR non devono essere interessati da questa modifica.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData?displayProperty=namewithType>

<!--

#### Affected APIs

`F:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData`

-->
