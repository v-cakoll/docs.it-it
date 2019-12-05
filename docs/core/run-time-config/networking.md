---
title: Impostazioni di configurazione di rete
description: Informazioni sulle impostazioni della fase di esecuzione che configurano la rete per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 622c4afbd36d3d9004edbd9219145fa9e5d326ae
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802771"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="be4a1-103">Opzioni di configurazione della fase di esecuzione per la rete</span><span class="sxs-lookup"><span data-stu-id="be4a1-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="be4a1-104">Protocollo HTTP/2</span><span class="sxs-lookup"><span data-stu-id="be4a1-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="be4a1-105">Configura se è abilitato il supporto per il protocollo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="be4a1-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>
- <span data-ttu-id="be4a1-106">Impostazione predefinita: disabilitato (`false`).</span><span class="sxs-lookup"><span data-stu-id="be4a1-106">Default: Disabled (`false`).</span></span>
- <span data-ttu-id="be4a1-107">Introdotta in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="be4a1-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="be4a1-108">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="be4a1-108">Setting name</span></span> | <span data-ttu-id="be4a1-109">Valori</span><span class="sxs-lookup"><span data-stu-id="be4a1-109">Values</span></span> |
| - | - |
| <span data-ttu-id="be4a1-110">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="be4a1-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="be4a1-111">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="be4a1-111">`false` - disabled</span></span><br/><span data-ttu-id="be4a1-112">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="be4a1-112">`true` - enabled</span></span> |
| <span data-ttu-id="be4a1-113">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="be4a1-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="be4a1-114">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="be4a1-114">`0` - disabled</span></span><br/><span data-ttu-id="be4a1-115">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="be4a1-115">`1` - enabled</span></span> |

## <a name="sockets-http-handler"></a><span data-ttu-id="be4a1-116">Gestore HTTP Sockets</span><span class="sxs-lookup"><span data-stu-id="be4a1-116">Sockets HTTP handler</span></span>

- <span data-ttu-id="be4a1-117">Configura se le API di rete di alto livello, ad esempio <xref:System.Net.Http.HttpClient>, usano <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> o l'implementazione di <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> basata su [libcurl](https://curl.haxx.se/libcurl/).</span><span class="sxs-lookup"><span data-stu-id="be4a1-117">Configures whether high-level networking APIs, such as <xref:System.Net.Http.HttpClient>, use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or the implementation of <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> that's based on [libcurl](https://curl.haxx.se/libcurl/).</span></span>
- <span data-ttu-id="be4a1-118">Impostazione predefinita: usare <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span><span class="sxs-lookup"><span data-stu-id="be4a1-118">Default: Use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span></span>
- <span data-ttu-id="be4a1-119">È possibile configurare questa impostazione a livello di codice chiamando il metodo <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="be4a1-119">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="be4a1-120">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="be4a1-120">Setting name</span></span> | <span data-ttu-id="be4a1-121">Valori</span><span class="sxs-lookup"><span data-stu-id="be4a1-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="be4a1-122">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="be4a1-122">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="be4a1-123">`true`-Abilita l'uso di <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="be4a1-123">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="be4a1-124">`false`-Abilita l'uso di <xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="be4a1-124">`false` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
| <span data-ttu-id="be4a1-125">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="be4a1-125">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="be4a1-126">`1`-Abilita l'uso di <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="be4a1-126">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="be4a1-127">`0`-Abilita l'uso di <xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="be4a1-127">`0` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
