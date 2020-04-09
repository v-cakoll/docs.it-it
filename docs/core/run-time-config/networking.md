---
title: Impostazioni di configurazione di rete
description: Informazioni sulle impostazioni di runtime che configurano la rete per le app .NET Core.Learn about run-time settings that configure networking for .NET Core apps.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 8d02087ad7260cc78c096090bf3b06a716d34678
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989103"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="a3dd3-103">Opzioni di configurazione in fase di esecuzione per la rete</span><span class="sxs-lookup"><span data-stu-id="a3dd3-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="a3dd3-104">Protocollo HTTP/2</span><span class="sxs-lookup"><span data-stu-id="a3dd3-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="a3dd3-105">Configura se il supporto per il protocollo HTTP/2 è abilitato.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="a3dd3-106">Impostazione predefinita: Disabilitato (`false`).</span><span class="sxs-lookup"><span data-stu-id="a3dd3-106">Default: Disabled (`false`).</span></span>

- <span data-ttu-id="a3dd3-107">Introdotto in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="a3dd3-108">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a3dd3-108">Setting name</span></span> | <span data-ttu-id="a3dd3-109">Valori</span><span class="sxs-lookup"><span data-stu-id="a3dd3-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a3dd3-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a3dd3-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="a3dd3-111">`false`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="a3dd3-111">`false` - disabled</span></span><br/><span data-ttu-id="a3dd3-112">`true`- abilitato</span><span class="sxs-lookup"><span data-stu-id="a3dd3-112">`true` - enabled</span></span> |
| <span data-ttu-id="a3dd3-113">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a3dd3-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="a3dd3-114">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="a3dd3-114">`0` - disabled</span></span><br/><span data-ttu-id="a3dd3-115">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="a3dd3-115">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="a3dd3-116">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="a3dd3-116">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="a3dd3-117">Configura se <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> utilizza o precedenti stack<xref:System.Net.Http.WinHttpHandler> di `CurlHandler`protocollo HTTP (in Windows e , una classe interna implementata su [libcurl](https://curl.haxx.se/libcurl/), su Linux).</span><span class="sxs-lookup"><span data-stu-id="a3dd3-117">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a3dd3-118">È possibile che si utilizzino API di rete di <xref:System.Net.Http.HttpClientHandler> alto livello anziché creare direttamente un'istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-118">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="a3dd3-119">Questa impostazione influisce anche sullo stack di protocollo HTTP utilizzato <xref:System.Net.Http.HttpClient> dalle API di rete di alto livello, tra cui e [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span><span class="sxs-lookup"><span data-stu-id="a3dd3-119">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span></span>

- <span data-ttu-id="a3dd3-120">Impostazione <xref:System.Net.Http.SocketsHttpHandler> predefinita: utilizzo ( ).`true`</span><span class="sxs-lookup"><span data-stu-id="a3dd3-120">Default: Use <xref:System.Net.Http.SocketsHttpHandler> (`true`).</span></span>

- <span data-ttu-id="a3dd3-121">È possibile configurare questa impostazione a livello di codice chiamando il <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodo .</span><span class="sxs-lookup"><span data-stu-id="a3dd3-121">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="a3dd3-122">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a3dd3-122">Setting name</span></span> | <span data-ttu-id="a3dd3-123">Valori</span><span class="sxs-lookup"><span data-stu-id="a3dd3-123">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a3dd3-124">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a3dd3-124">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="a3dd3-125">`true`- consente l'uso di<xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="a3dd3-125">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="a3dd3-126">`false`- consente l'uso di <xref:System.Net.Http.WinHttpHandler> su Windows o [libcurl](https://curl.haxx.se/libcurl/) su Linux</span><span class="sxs-lookup"><span data-stu-id="a3dd3-126">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="a3dd3-127">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a3dd3-127">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="a3dd3-128">`1`- consente l'uso di<xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="a3dd3-128">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="a3dd3-129">`0`- consente l'uso di <xref:System.Net.Http.WinHttpHandler> su Windows o [libcurl](https://curl.haxx.se/libcurl/) su Linux</span><span class="sxs-lookup"><span data-stu-id="a3dd3-129">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="a3dd3-130">A partire da .NET 5, l'impostazione `System.Net.Http.UseSocketsHttpHandler` non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="a3dd3-130">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
