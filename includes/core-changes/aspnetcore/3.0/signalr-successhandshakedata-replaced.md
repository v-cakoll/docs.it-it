---
ms.openlocfilehash: 1d8bcaf68d44f27642048c1c207b52c55b604690
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902016"
---
### <a name="signalr-handshakeprotocolsuccesshandshakedata-replaced"></a><span data-ttu-id="274c3-101">SignalR: HandshakeProtocol. SuccessHandshakeData sostituito</span><span class="sxs-lookup"><span data-stu-id="274c3-101">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>

<span data-ttu-id="274c3-102">Il campo [HandshakeProtocol. SuccessHandshakeData](https://github.com/dotnet/aspnetcore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) è stato rimosso e sostituito con un metodo helper che genera una risposta di handshake riuscita data una `IHubProtocol`specifica.</span><span class="sxs-lookup"><span data-stu-id="274c3-102">The [HandshakeProtocol.SuccessHandshakeData](https://github.com/dotnet/aspnetcore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) field was removed and replaced with a helper method that generates a successful handshake response given a specific `IHubProtocol`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="274c3-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="274c3-103">Version introduced</span></span>

<span data-ttu-id="274c3-104">3.0</span><span class="sxs-lookup"><span data-stu-id="274c3-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="274c3-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="274c3-105">Old behavior</span></span>

<span data-ttu-id="274c3-106">`HandshakeProtocol.SuccessHandshakeData` è un campo di `public static ReadOnlyMemory<byte>`.</span><span class="sxs-lookup"><span data-stu-id="274c3-106">`HandshakeProtocol.SuccessHandshakeData` was a `public static ReadOnlyMemory<byte>` field.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="274c3-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="274c3-107">New behavior</span></span>

<span data-ttu-id="274c3-108">`HandshakeProtocol.SuccessHandshakeData` è stato sostituito da un `static` `GetSuccessfulHandshake(IHubProtocol protocol)` metodo che restituisce un `ReadOnlyMemory<byte>` basato sul protocollo specificato.</span><span class="sxs-lookup"><span data-stu-id="274c3-108">`HandshakeProtocol.SuccessHandshakeData` has been replaced by a `static` `GetSuccessfulHandshake(IHubProtocol protocol)` method that returns a `ReadOnlyMemory<byte>` based on the specified protocol.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="274c3-109">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="274c3-109">Reason for change</span></span>

<span data-ttu-id="274c3-110">Sono stati aggiunti ulteriori campi alla _risposta_ di handshake che non sono costanti e cambiano a seconda del protocollo selezionato.</span><span class="sxs-lookup"><span data-stu-id="274c3-110">Additional fields were added to the handshake _response_ that are non-constant and change depending on the selected protocol.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="274c3-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="274c3-111">Recommended action</span></span>

<span data-ttu-id="274c3-112">nessuna.</span><span class="sxs-lookup"><span data-stu-id="274c3-112">None.</span></span> <span data-ttu-id="274c3-113">Questo tipo non è progettato per essere usato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="274c3-113">This type isn't designed for use from user code.</span></span> <span data-ttu-id="274c3-114">È `public`, quindi può essere condiviso tra il server SignalR e il client.</span><span class="sxs-lookup"><span data-stu-id="274c3-114">It's `public`, so it can be shared between the SignalR server and client.</span></span> <span data-ttu-id="274c3-115">Può anche essere usato dai client SignalR scritti in .NET.</span><span class="sxs-lookup"><span data-stu-id="274c3-115">It may also be used by customer SignalR clients written in .NET.</span></span> <span data-ttu-id="274c3-116">**Gli utenti** di SignalR non devono essere interessati da questa modifica.</span><span class="sxs-lookup"><span data-stu-id="274c3-116">**Users** of SignalR shouldn't be affected by this change.</span></span>

#### <a name="category"></a><span data-ttu-id="274c3-117">Categoria</span><span class="sxs-lookup"><span data-stu-id="274c3-117">Category</span></span>

<span data-ttu-id="274c3-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="274c3-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="274c3-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="274c3-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData?displayProperty=namewithType>

<!--

#### Affected APIs

`F:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData`

-->
