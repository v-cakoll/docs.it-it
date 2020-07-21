---
ms.openlocfilehash: 203d75f5858c8ff039cf579c0539efda0c5c9f02
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474378"
---
### <a name="kestrel-libuv-transport-marked-as-obsolete"></a><span data-ttu-id="65f8e-101">Gheppio: trasporto libuv contrassegnato come obsoleto</span><span class="sxs-lookup"><span data-stu-id="65f8e-101">Kestrel: Libuv transport marked as obsolete</span></span>

<span data-ttu-id="65f8e-102">Nelle versioni precedenti di ASP.NET Core veniva utilizzato libuv come dettaglio di implementazione di come è stato eseguito l'input e l'output asincroni.</span><span class="sxs-lookup"><span data-stu-id="65f8e-102">Earlier versions of ASP.NET Core used Libuv as an implementation detail of how asynchronous input and output was performed.</span></span> <span data-ttu-id="65f8e-103">In ASP.NET Core 2,0 <xref:System.Net.Sockets.Socket> è stato sviluppato un trasporto alternativo basato su.</span><span class="sxs-lookup"><span data-stu-id="65f8e-103">In ASP.NET Core 2.0, an alternative, <xref:System.Net.Sockets.Socket>-based transport was developed.</span></span> <span data-ttu-id="65f8e-104">In ASP.NET Core 2,1, gheppio passa a usando il `Socket` trasporto basato su per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="65f8e-104">In ASP.NET Core 2.1, Kestrel switched to using the `Socket`-based transport by default.</span></span> <span data-ttu-id="65f8e-105">Il supporto di Libuv è stato mantenuto per motivi di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="65f8e-105">Libuv support was maintained for compatibility reasons.</span></span>

<span data-ttu-id="65f8e-106">A questo punto, l'uso del `Socket` trasporto basato su è molto più comune del trasporto libuv.</span><span class="sxs-lookup"><span data-stu-id="65f8e-106">At this point, use of the `Socket`-based transport is far more common than the Libuv transport.</span></span> <span data-ttu-id="65f8e-107">Di conseguenza, il supporto per Libuv è contrassegnato come obsoleto in .NET 5,0 e verrà rimosso interamente in .NET 6,0.</span><span class="sxs-lookup"><span data-stu-id="65f8e-107">Consequently, Libuv support is marked as obsolete in .NET 5.0 and will be removed entirely in .NET 6.0.</span></span>

<span data-ttu-id="65f8e-108">Come parte di questa modifica, il supporto libuv per le nuove piattaforme del sistema operativo (ad esempio Windows ARM64) non verrà aggiunto nell'intervallo di tempo di .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="65f8e-108">As part of this change, Libuv support for new operating system platforms (like Windows ARM64) won't be added in the .NET 5.0 timeframe.</span></span>

<span data-ttu-id="65f8e-109">Per informazioni sul blocco di problemi che richiedono l'uso del trasporto libuv, vedere il problema GitHub in [DotNet/aspnetcore # 23409](https://github.com/dotnet/aspnetcore/issues/23409).</span><span class="sxs-lookup"><span data-stu-id="65f8e-109">For discussion on blocking issues that require the use of the Libuv transport, see the GitHub issue at [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="65f8e-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="65f8e-110">Version introduced</span></span>

<span data-ttu-id="65f8e-111">5,0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="65f8e-111">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="65f8e-112">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="65f8e-112">Old behavior</span></span>

<span data-ttu-id="65f8e-113">Le API libuv non sono contrassegnate come obsolete.</span><span class="sxs-lookup"><span data-stu-id="65f8e-113">The Libuv APIs aren't marked as obsolete.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="65f8e-114">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="65f8e-114">New behavior</span></span>

<span data-ttu-id="65f8e-115">Le API libuv sono contrassegnate come obsolete.</span><span class="sxs-lookup"><span data-stu-id="65f8e-115">The Libuv APIs are marked as obsolete.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="65f8e-116">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="65f8e-116">Reason for change</span></span>

<span data-ttu-id="65f8e-117">Il `Socket` trasporto basato su è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="65f8e-117">The `Socket`-based transport is the default.</span></span> <span data-ttu-id="65f8e-118">Non esistono motivi interessanti per continuare a usare il trasporto libuv.</span><span class="sxs-lookup"><span data-stu-id="65f8e-118">There aren't any compelling reasons to continue using the Libuv transport.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="65f8e-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="65f8e-119">Recommended action</span></span>

<span data-ttu-id="65f8e-120">Sospendere l'uso del [pacchetto libuv](https://www.nuget.org/packages/Libuv) e dei metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="65f8e-120">Discontinue use of the [Libuv package](https://www.nuget.org/packages/Libuv) and extension methods.</span></span>

#### <a name="category"></a><span data-ttu-id="65f8e-121">Category</span><span class="sxs-lookup"><span data-stu-id="65f8e-121">Category</span></span>

<span data-ttu-id="65f8e-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="65f8e-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="65f8e-123">API interessate</span><span class="sxs-lookup"><span data-stu-id="65f8e-123">Affected APIs</span></span>

- [<span data-ttu-id="65f8e-124">WebHostBuilderLibuvExtensions</span><span class="sxs-lookup"><span data-stu-id="65f8e-124">WebHostBuilderLibuvExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions?view=aspnetcore-3.0)
- [<span data-ttu-id="65f8e-125">WebHostBuilderLibuvExtensions.UseLibuv</span><span class="sxs-lookup"><span data-stu-id="65f8e-125">WebHostBuilderLibuvExtensions.UseLibuv</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions.uselibuv?view=aspnetcore-3.0)
- [<span data-ttu-id="65f8e-126">Microsoft. AspNetCore. Server. gheppio. Transport. libuv. LibuvTransportOptions</span><span class="sxs-lookup"><span data-stu-id="65f8e-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions?view=aspnetcore-3.0)
- [<span data-ttu-id="65f8e-127">Microsoft. AspNetCore. Server. gheppio. Transport. libuv. LibuvTransportOptions. ThreadCount</span><span class="sxs-lookup"><span data-stu-id="65f8e-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.threadcount?view=aspnetcore-3.0)
- [<span data-ttu-id="65f8e-128">Microsoft. AspNetCore. Server. gheppio. Transport. libuv. LibuvTransportOptions. NoDelay</span><span class="sxs-lookup"><span data-stu-id="65f8e-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.nodelay?view=aspnetcore-3.0)
- [<span data-ttu-id="65f8e-129">Microsoft. AspNetCore. Server. gheppio. Transport. libuv. LibuvTransportOptions. MaxWriteBufferSize</span><span class="sxs-lookup"><span data-stu-id="65f8e-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxwritebuffersize?view=aspnetcore-3.0)
- [<span data-ttu-id="65f8e-130">Microsoft. AspNetCore. Server. gheppio. Transport. libuv. LibuvTransportOptions. MaxReadBufferSize</span><span class="sxs-lookup"><span data-stu-id="65f8e-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxreadbuffersize?view=aspnetcore-3.0)
- `Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions`
- `Overload:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions.UseLibuv`
- `T:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

-->
