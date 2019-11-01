---
ms.openlocfilehash: e9278320ee3fdf9e6b89698d187f047c309ea791
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198465"
---
### <a name="signalr-handshakeprotocolsuccesshandshakedata-replaced"></a><span data-ttu-id="bf0af-101">SignalR: HandshakeProtocol. SuccessHandshakeData sostituito</span><span class="sxs-lookup"><span data-stu-id="bf0af-101">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>

<span data-ttu-id="bf0af-102">Il campo [HandshakeProtocol. SuccessHandshakeData](https://github.com/aspnet/AspNetCore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) è stato rimosso e sostituito con un metodo helper che genera una risposta di handshake riuscita data una specifica `IHubProtocol`.</span><span class="sxs-lookup"><span data-stu-id="bf0af-102">The [HandshakeProtocol.SuccessHandshakeData](https://github.com/aspnet/AspNetCore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) field was removed and replaced with a helper method that generates a successful handshake response given a specific `IHubProtocol`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bf0af-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bf0af-103">Version introduced</span></span>

<span data-ttu-id="bf0af-104">3.0</span><span class="sxs-lookup"><span data-stu-id="bf0af-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="bf0af-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="bf0af-105">Old behavior</span></span>

<span data-ttu-id="bf0af-106">`HandshakeProtocol.SuccessHandshakeData` era un campo `public static ReadOnlyMemory<byte>`.</span><span class="sxs-lookup"><span data-stu-id="bf0af-106">`HandshakeProtocol.SuccessHandshakeData` was a `public static ReadOnlyMemory<byte>` field.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="bf0af-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="bf0af-107">New behavior</span></span>

<span data-ttu-id="bf0af-108">`HandshakeProtocol.SuccessHandshakeData` è stato sostituito da un metodo `static` `GetSuccessfulHandshake(IHubProtocol protocol)` che restituisce un `ReadOnlyMemory<byte>` Basato sul protocollo specificato.</span><span class="sxs-lookup"><span data-stu-id="bf0af-108">`HandshakeProtocol.SuccessHandshakeData` has been replaced by a `static` `GetSuccessfulHandshake(IHubProtocol protocol)` method that returns a `ReadOnlyMemory<byte>` based on the specified protocol.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="bf0af-109">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="bf0af-109">Reason for change</span></span>

<span data-ttu-id="bf0af-110">Sono stati aggiunti ulteriori campi alla _risposta_ di handshake che non sono costanti e cambiano a seconda del protocollo selezionato.</span><span class="sxs-lookup"><span data-stu-id="bf0af-110">Additional fields were added to the handshake _response_ that are non-constant and change depending on the selected protocol.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bf0af-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="bf0af-111">Recommended action</span></span>

<span data-ttu-id="bf0af-112">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="bf0af-112">None.</span></span> <span data-ttu-id="bf0af-113">Questo tipo non è progettato per essere usato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="bf0af-113">This type isn't designed for use from user code.</span></span> <span data-ttu-id="bf0af-114">È `public`, quindi può essere condiviso tra il server SignalR e il client.</span><span class="sxs-lookup"><span data-stu-id="bf0af-114">It's `public`, so it can be shared between the SignalR server and client.</span></span> <span data-ttu-id="bf0af-115">Può anche essere usato dai client SignalR scritti in .NET.</span><span class="sxs-lookup"><span data-stu-id="bf0af-115">It may also be used by customer SignalR clients written in .NET.</span></span> <span data-ttu-id="bf0af-116">**Gli utenti** di SignalR non devono essere interessati da questa modifica.</span><span class="sxs-lookup"><span data-stu-id="bf0af-116">**Users** of SignalR shouldn't be affected by this change.</span></span>

#### <a name="category"></a><span data-ttu-id="bf0af-117">Category</span><span class="sxs-lookup"><span data-stu-id="bf0af-117">Category</span></span>

<span data-ttu-id="bf0af-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bf0af-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bf0af-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="bf0af-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData?displayProperty=namewithType>

<!--

#### Affected APIs

`F:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData`

-->
