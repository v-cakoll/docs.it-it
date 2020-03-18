---
title: Impostazioni di configurazione di rete
description: Informazioni sulle impostazioni di runtime che configurano la rete per le app .NET Core.Learn about run-time settings that configure networking for .NET Core apps.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 622c4afbd36d3d9004edbd9219145fa9e5d326ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74802771"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="a900e-103">Opzioni di configurazione in fase di esecuzione per la rete</span><span class="sxs-lookup"><span data-stu-id="a900e-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="a900e-104">Protocollo HTTP/2</span><span class="sxs-lookup"><span data-stu-id="a900e-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="a900e-105">Configura se il supporto per il protocollo HTTP/2 è abilitato.</span><span class="sxs-lookup"><span data-stu-id="a900e-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>
- <span data-ttu-id="a900e-106">Impostazione predefinita: Disabilitato (`false`).</span><span class="sxs-lookup"><span data-stu-id="a900e-106">Default: Disabled (`false`).</span></span>
- <span data-ttu-id="a900e-107">Introdotto in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a900e-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="a900e-108">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a900e-108">Setting name</span></span> | <span data-ttu-id="a900e-109">Valori</span><span class="sxs-lookup"><span data-stu-id="a900e-109">Values</span></span> |
| - | - |
| <span data-ttu-id="a900e-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a900e-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="a900e-111">`false`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="a900e-111">`false` - disabled</span></span><br/><span data-ttu-id="a900e-112">`true`- abilitato</span><span class="sxs-lookup"><span data-stu-id="a900e-112">`true` - enabled</span></span> |
| <span data-ttu-id="a900e-113">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a900e-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="a900e-114">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="a900e-114">`0` - disabled</span></span><br/><span data-ttu-id="a900e-115">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="a900e-115">`1` - enabled</span></span> |

## <a name="sockets-http-handler"></a><span data-ttu-id="a900e-116">Gestore HTTP Sockets</span><span class="sxs-lookup"><span data-stu-id="a900e-116">Sockets HTTP handler</span></span>

- <span data-ttu-id="a900e-117">Configura se le API di rete di <xref:System.Net.Http.HttpClient>alto <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> livello, <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> ad esempio , utilizzano o l'implementazione di tale è basata su [libcurl](https://curl.haxx.se/libcurl/).</span><span class="sxs-lookup"><span data-stu-id="a900e-117">Configures whether high-level networking APIs, such as <xref:System.Net.Http.HttpClient>, use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or the implementation of <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> that's based on [libcurl](https://curl.haxx.se/libcurl/).</span></span>
- <span data-ttu-id="a900e-118">Impostazione <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> predefinita: utilizzo ( ).`true`</span><span class="sxs-lookup"><span data-stu-id="a900e-118">Default: Use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span></span>
- <span data-ttu-id="a900e-119">È possibile configurare questa impostazione a livello di codice chiamando il <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodo .</span><span class="sxs-lookup"><span data-stu-id="a900e-119">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="a900e-120">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a900e-120">Setting name</span></span> | <span data-ttu-id="a900e-121">Valori</span><span class="sxs-lookup"><span data-stu-id="a900e-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a900e-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a900e-122">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="a900e-123">`true`- consente l'uso di<xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="a900e-123">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="a900e-124">`false`- consente l'uso di<xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="a900e-124">`false` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
| <span data-ttu-id="a900e-125">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a900e-125">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="a900e-126">`1`- consente l'uso di<xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="a900e-126">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="a900e-127">`0`- consente l'uso di<xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="a900e-127">`0` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
