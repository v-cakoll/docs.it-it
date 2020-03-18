---
ms.openlocfilehash: 1d8bcaf68d44f27642048c1c207b52c55b604690
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75902016"
---
### <a name="signalr-handshakeprotocolsuccesshandshakedata-replaced"></a><span data-ttu-id="24a94-101">SignalR: HandshakeProtocol.SuccessHandshakeData sostituito</span><span class="sxs-lookup"><span data-stu-id="24a94-101">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>

<span data-ttu-id="24a94-102">Il campo [HandshakeProtocol.SuccessHandshakeData](https://github.com/dotnet/aspnetcore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) è stato rimosso e sostituito con un `IHubProtocol`metodo di supporto che genera una risposta di handshake corretta data un oggetto specifico .</span><span class="sxs-lookup"><span data-stu-id="24a94-102">The [HandshakeProtocol.SuccessHandshakeData](https://github.com/dotnet/aspnetcore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) field was removed and replaced with a helper method that generates a successful handshake response given a specific `IHubProtocol`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="24a94-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="24a94-103">Version introduced</span></span>

<span data-ttu-id="24a94-104">3.0</span><span class="sxs-lookup"><span data-stu-id="24a94-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="24a94-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="24a94-105">Old behavior</span></span>

<span data-ttu-id="24a94-106">`HandshakeProtocol.SuccessHandshakeData`era `public static ReadOnlyMemory<byte>` un campo.</span><span class="sxs-lookup"><span data-stu-id="24a94-106">`HandshakeProtocol.SuccessHandshakeData` was a `public static ReadOnlyMemory<byte>` field.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="24a94-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="24a94-107">New behavior</span></span>

<span data-ttu-id="24a94-108">`HandshakeProtocol.SuccessHandshakeData`è stato sostituito da un `static` `GetSuccessfulHandshake(IHubProtocol protocol)` metodo che restituisce un `ReadOnlyMemory<byte>` oggetto basato sul protocollo specificato.</span><span class="sxs-lookup"><span data-stu-id="24a94-108">`HandshakeProtocol.SuccessHandshakeData` has been replaced by a `static` `GetSuccessfulHandshake(IHubProtocol protocol)` method that returns a `ReadOnlyMemory<byte>` based on the specified protocol.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="24a94-109">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="24a94-109">Reason for change</span></span>

<span data-ttu-id="24a94-110">Sono stati aggiunti campi aggiuntivi alla _risposta_ di handshake che non sono costanti e cambiano a seconda del protocollo selezionato.</span><span class="sxs-lookup"><span data-stu-id="24a94-110">Additional fields were added to the handshake _response_ that are non-constant and change depending on the selected protocol.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="24a94-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="24a94-111">Recommended action</span></span>

<span data-ttu-id="24a94-112">No.</span><span class="sxs-lookup"><span data-stu-id="24a94-112">None.</span></span> <span data-ttu-id="24a94-113">Questo tipo non è progettato per l'utilizzo da codice utente.</span><span class="sxs-lookup"><span data-stu-id="24a94-113">This type isn't designed for use from user code.</span></span> <span data-ttu-id="24a94-114">È `public`, quindi può essere condiviso tra il server SignalR e il client.</span><span class="sxs-lookup"><span data-stu-id="24a94-114">It's `public`, so it can be shared between the SignalR server and client.</span></span> <span data-ttu-id="24a94-115">Può anche essere utilizzato dai client SignalR del cliente scritti in .NET.</span><span class="sxs-lookup"><span data-stu-id="24a94-115">It may also be used by customer SignalR clients written in .NET.</span></span> <span data-ttu-id="24a94-116">**Gli utenti** di SignalR non dovrebbero essere interessati da questa modifica.</span><span class="sxs-lookup"><span data-stu-id="24a94-116">**Users** of SignalR shouldn't be affected by this change.</span></span>

#### <a name="category"></a><span data-ttu-id="24a94-117">Category</span><span class="sxs-lookup"><span data-stu-id="24a94-117">Category</span></span>

<span data-ttu-id="24a94-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="24a94-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="24a94-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="24a94-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData?displayProperty=namewithType>

<!--

#### Affected APIs

`F:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData`

-->
