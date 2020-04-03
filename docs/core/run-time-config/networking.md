---
title: Impostazioni di configurazione di rete
description: Informazioni sulle impostazioni di runtime che configurano la rete per le app .NET Core.Learn about run-time settings that configure networking for .NET Core apps.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: f5ea47f0444a911dc2347a66817cabf585fd8e70
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635419"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="306f2-103">Opzioni di configurazione in fase di esecuzione per la rete</span><span class="sxs-lookup"><span data-stu-id="306f2-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="306f2-104">Protocollo HTTP/2</span><span class="sxs-lookup"><span data-stu-id="306f2-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="306f2-105">Configura se il supporto per il protocollo HTTP/2 è abilitato.</span><span class="sxs-lookup"><span data-stu-id="306f2-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>
- <span data-ttu-id="306f2-106">Impostazione predefinita: Disabilitato (`false`).</span><span class="sxs-lookup"><span data-stu-id="306f2-106">Default: Disabled (`false`).</span></span>
- <span data-ttu-id="306f2-107">Introdotto in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="306f2-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="306f2-108">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="306f2-108">Setting name</span></span> | <span data-ttu-id="306f2-109">Valori</span><span class="sxs-lookup"><span data-stu-id="306f2-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="306f2-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="306f2-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="306f2-111">`false`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="306f2-111">`false` - disabled</span></span><br/><span data-ttu-id="306f2-112">`true`- abilitato</span><span class="sxs-lookup"><span data-stu-id="306f2-112">`true` - enabled</span></span> |
| <span data-ttu-id="306f2-113">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="306f2-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="306f2-114">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="306f2-114">`0` - disabled</span></span><br/><span data-ttu-id="306f2-115">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="306f2-115">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="306f2-116">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="306f2-116">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="306f2-117">Configura se le API di rete di <xref:System.Net.Http.HttpClient>alto <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> livello, <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> ad esempio , utilizzano o l'implementazione di tale è basata su [libcurl](https://curl.haxx.se/libcurl/).</span><span class="sxs-lookup"><span data-stu-id="306f2-117">Configures whether high-level networking APIs, such as <xref:System.Net.Http.HttpClient>, use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or the implementation of <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> that's based on [libcurl](https://curl.haxx.se/libcurl/).</span></span>
- <span data-ttu-id="306f2-118">Impostazione <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> predefinita: utilizzo ( ).`true`</span><span class="sxs-lookup"><span data-stu-id="306f2-118">Default: Use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span></span>
- <span data-ttu-id="306f2-119">È possibile configurare questa impostazione a livello di codice chiamando il <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodo .</span><span class="sxs-lookup"><span data-stu-id="306f2-119">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="306f2-120">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="306f2-120">Setting name</span></span> | <span data-ttu-id="306f2-121">Valori</span><span class="sxs-lookup"><span data-stu-id="306f2-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="306f2-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="306f2-122">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="306f2-123">`true`- consente l'uso di<xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="306f2-123">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="306f2-124">`false`- consente l'uso di<xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="306f2-124">`false` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
| <span data-ttu-id="306f2-125">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="306f2-125">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="306f2-126">`1`- consente l'uso di<xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="306f2-126">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="306f2-127">`0`- consente l'uso di<xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="306f2-127">`0` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |

> [!NOTE]
> <span data-ttu-id="306f2-128">A partire da .NET 5, l'impostazione `System.Net.Http.UseSocketsHttpHandler` non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="306f2-128">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
