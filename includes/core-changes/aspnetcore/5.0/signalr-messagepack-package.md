---
ms.openlocfilehash: ca0792a3fd05d28cecceac1d644e3e4bf64722bc
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345233"
---
### <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a><span data-ttu-id="d2730-101">SignalR: protocollo Hub MessagePack spostato nel pacchetto MessagePack 2.x</span><span class="sxs-lookup"><span data-stu-id="d2730-101">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>

<span data-ttu-id="d2730-102">Il ASP.NET Core SignalR [MessagePack Protocollo hub](/aspnet/core/signalr/messagepackhubprotocol) utilizza il [pacchetto MessagePack NuGet](https://www.nuget.org/packages/MessagePack) per la serializzazione MessagePack.</span><span class="sxs-lookup"><span data-stu-id="d2730-102">The ASP.NET Core SignalR [MessagePack Hub Protocol](/aspnet/core/signalr/messagepackhubprotocol) uses the [MessagePack NuGet package](https://www.nuget.org/packages/MessagePack) for MessagePack serialization.</span></span> <span data-ttu-id="d2730-103">ASP.NET Core 5.0 aggiorna il pacchetto dalla versione 1.x alla versione più recente del pacchetto 2.x.</span><span class="sxs-lookup"><span data-stu-id="d2730-103">ASP.NET Core 5.0 upgrades the package from 1.x to the latest 2.x package version.</span></span>

<span data-ttu-id="d2730-104">Per una discussione su questo problema, vedere [dotnet/aspnetcore-18692](https://github.com/dotnet/aspnetcore/issues/18692).</span><span class="sxs-lookup"><span data-stu-id="d2730-104">For discussion on this issue, see [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d2730-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="d2730-105">Version introduced</span></span>

<span data-ttu-id="d2730-106">5.0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="d2730-106">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d2730-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="d2730-107">Old behavior</span></span>

<span data-ttu-id="d2730-108">ASP.NET Core SignalR ha usato il pacchetto MessagePack 1.x per serializzare e deserializzare i messaggi MessagePack.</span><span class="sxs-lookup"><span data-stu-id="d2730-108">ASP.NET Core SignalR used the MessagePack 1.x package to serialize and deserialize MessagePack messages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d2730-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="d2730-109">New behavior</span></span>

<span data-ttu-id="d2730-110">ASP.NET Core SignalR utilizza il pacchetto MessagePack 2.x per serializzare e deserializzare i messaggi MessagePack.</span><span class="sxs-lookup"><span data-stu-id="d2730-110">ASP.NET Core SignalR uses the MessagePack 2.x package to serialize and deserialize MessagePack messages.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d2730-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="d2730-111">Reason for change</span></span>

<span data-ttu-id="d2730-112">I miglioramenti più recenti nel pacchetto MessagePack 2.x aggiungono funzionalità utili.</span><span class="sxs-lookup"><span data-stu-id="d2730-112">The latest improvements in the MessagePack 2.x package add useful functionality.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d2730-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="d2730-113">Recommended action</span></span>

<span data-ttu-id="d2730-114">Questa modifica di rilievo si applica quando:</span><span class="sxs-lookup"><span data-stu-id="d2730-114">This breaking change applies when:</span></span>

* <span data-ttu-id="d2730-115">Impostazione o configurazione <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>di valori su .</span><span class="sxs-lookup"><span data-stu-id="d2730-115">Setting or configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span>
* <span data-ttu-id="d2730-116">Utilizzando le API MessagePack direttamente e utilizzando il ASP.NET Core SignalR MessagePack Protocollo hub nello stesso progetto.</span><span class="sxs-lookup"><span data-stu-id="d2730-116">Using the MessagePack APIs directly and using the ASP.NET Core SignalR MessagePack Hub Protocol in the same project.</span></span> <span data-ttu-id="d2730-117">Verrà caricata la versione più recente anziché la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="d2730-117">The newer version will be loaded instead of the previous version.</span></span>

<span data-ttu-id="d2730-118">Per indicazioni sulla migrazione dagli autori del pacchetto, vedere [Migrazione da MessagePack v1.x a MessagePack v2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span><span class="sxs-lookup"><span data-stu-id="d2730-118">For migration guidance from the package authors, see [Migrating from MessagePack v1.x to MessagePack v2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span></span> <span data-ttu-id="d2730-119">Alcuni aspetti della serializzazione e deserializzazione dei messaggi sono interessati.</span><span class="sxs-lookup"><span data-stu-id="d2730-119">Some aspects of message serialization and deserialization are affected.</span></span> <span data-ttu-id="d2730-120">In particolare, sono state [apportate modifiche comportamentali alla modalità](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes)di serializzazione dei valori DateTime .</span><span class="sxs-lookup"><span data-stu-id="d2730-120">Specifically, there are [behavioral changes to how DateTime values are serialized](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span></span>

#### <a name="category"></a><span data-ttu-id="d2730-121">Category</span><span class="sxs-lookup"><span data-stu-id="d2730-121">Category</span></span>

<span data-ttu-id="d2730-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d2730-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d2730-123">API interessate</span><span class="sxs-lookup"><span data-stu-id="d2730-123">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
