---
ms.openlocfilehash: e9278320ee3fdf9e6b89698d187f047c309ea791
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198465"
---
### <a name="signalr-handshakeprotocolsuccesshandshakedata-replaced"></a>SignalR: HandshakeProtocol. SuccessHandshakeData sostituito

Il campo [HandshakeProtocol. SuccessHandshakeData](https://github.com/aspnet/AspNetCore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) è stato rimosso e sostituito con un metodo helper che genera una risposta di handshake riuscita data una specifica `IHubProtocol`.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

`HandshakeProtocol.SuccessHandshakeData` era un campo `public static ReadOnlyMemory<byte>`.

#### <a name="new-behavior"></a>Nuovo comportamento

`HandshakeProtocol.SuccessHandshakeData` è stato sostituito da un metodo `static` `GetSuccessfulHandshake(IHubProtocol protocol)` che restituisce un `ReadOnlyMemory<byte>` Basato sul protocollo specificato.

#### <a name="reason-for-change"></a>Motivo della modifica

Sono stati aggiunti ulteriori campi alla _risposta_ di handshake che non sono costanti e cambiano a seconda del protocollo selezionato.

#### <a name="recommended-action"></a>Azione consigliata

Nessuna. Questo tipo non è progettato per essere usato dal codice utente. È `public`, quindi può essere condiviso tra il server SignalR e il client. Può anche essere usato dai client SignalR scritti in .NET. **Gli utenti** di SignalR non devono essere interessati da questa modifica.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData?displayProperty=namewithType>

<!--

#### Affected APIs

`F:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData`

-->
