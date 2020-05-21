---
title: Impostazioni di configurazione di rete
description: Informazioni sulle impostazioni della fase di esecuzione che configurano la rete per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6b5e03b127f95911b712b66c0be8a4f5a2929fc2
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761941"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="23e20-103">Opzioni di configurazione della fase di esecuzione per la rete</span><span class="sxs-lookup"><span data-stu-id="23e20-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="23e20-104">Protocollo HTTP/2</span><span class="sxs-lookup"><span data-stu-id="23e20-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="23e20-105">Configura se è abilitato il supporto per il protocollo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="23e20-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="23e20-106">Se si omette questa impostazione, il supporto per il protocollo HTTP/2 è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="23e20-106">If you omit this setting, support for the HTTP/2 protocol is disabled.</span></span> <span data-ttu-id="23e20-107">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="23e20-107">This is equivalent to setting the value to `false`.</span></span>

- <span data-ttu-id="23e20-108">Introdotta in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="23e20-108">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="23e20-109">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="23e20-109">Setting name</span></span> | <span data-ttu-id="23e20-110">Valori</span><span class="sxs-lookup"><span data-stu-id="23e20-110">Values</span></span> |
| - | - | - |
| <span data-ttu-id="23e20-111">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="23e20-111">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="23e20-112">`false`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="23e20-112">`false` - disabled</span></span><br/><span data-ttu-id="23e20-113">`true`-abilitato</span><span class="sxs-lookup"><span data-stu-id="23e20-113">`true` - enabled</span></span> |
| <span data-ttu-id="23e20-114">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="23e20-114">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="23e20-115">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="23e20-115">`0` - disabled</span></span><br/><span data-ttu-id="23e20-116">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="23e20-116">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="23e20-117">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="23e20-117">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="23e20-118">Configura se <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> Usa <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> o stack del protocollo http meno recenti ( <xref:System.Net.Http.WinHttpHandler> in Windows e `CurlHandler` , una classe interna implementata in [libcurl](https://curl.haxx.se/libcurl/)in Linux).</span><span class="sxs-lookup"><span data-stu-id="23e20-118">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="23e20-119">È possibile che si stiano usando API di rete di alto livello anziché creare direttamente un'istanza della <xref:System.Net.Http.HttpClientHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="23e20-119">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="23e20-120">Questa impostazione interessa anche lo stack di protocolli HTTP usato dalle API di rete di alto livello, tra cui <xref:System.Net.Http.HttpClient> e [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span><span class="sxs-lookup"><span data-stu-id="23e20-120">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span></span>

- <span data-ttu-id="23e20-121">Se si omette questa impostazione, <xref:System.Net.Http.HttpClientHandler> utilizza <xref:System.Net.Http.SocketsHttpHandler> .</span><span class="sxs-lookup"><span data-stu-id="23e20-121">If you omit this setting, <xref:System.Net.Http.HttpClientHandler> uses <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="23e20-122">Equivale a impostare il valore su `true` .</span><span class="sxs-lookup"><span data-stu-id="23e20-122">This is equivalent to setting the value to `true`.</span></span>

- <span data-ttu-id="23e20-123">È possibile configurare questa impostazione a livello di codice chiamando il <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="23e20-123">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="23e20-124">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="23e20-124">Setting name</span></span> | <span data-ttu-id="23e20-125">Valori</span><span class="sxs-lookup"><span data-stu-id="23e20-125">Values</span></span> |
| - | - | - |
| <span data-ttu-id="23e20-126">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="23e20-126">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="23e20-127">`true`-Abilita l'uso di<xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="23e20-127">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="23e20-128">`false`-Abilita l'uso di <xref:System.Net.Http.WinHttpHandler> in Windows o [libcurl](https://curl.haxx.se/libcurl/) in Linux</span><span class="sxs-lookup"><span data-stu-id="23e20-128">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="23e20-129">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="23e20-129">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="23e20-130">`1`-Abilita l'uso di<xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="23e20-130">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="23e20-131">`0`-Abilita l'uso di <xref:System.Net.Http.WinHttpHandler> in Windows o [libcurl](https://curl.haxx.se/libcurl/) in Linux</span><span class="sxs-lookup"><span data-stu-id="23e20-131">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="23e20-132">A partire da .NET 5, l' `System.Net.Http.UseSocketsHttpHandler` impostazione non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="23e20-132">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
