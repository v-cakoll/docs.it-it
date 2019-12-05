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
# <a name="run-time-configuration-options-for-networking"></a>Opzioni di configurazione della fase di esecuzione per la rete

## <a name="http2-protocol"></a>Protocollo HTTP/2

- Configura se è abilitato il supporto per il protocollo HTTP/2.
- Impostazione predefinita: disabilitato (`false`).
- Introdotta in .NET Core 3,0.

| | Nome impostazione | Valori |
| - | - |
| **runtimeconfig. JSON** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false` disabilitato<br/>Abilitazione di `true` |
| **Variabile di ambiente** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0` disabilitato<br/>Abilitazione di `1` |

## <a name="sockets-http-handler"></a>Gestore HTTP Sockets

- Configura se le API di rete di alto livello, ad esempio <xref:System.Net.Http.HttpClient>, usano <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> o l'implementazione di <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> basata su [libcurl](https://curl.haxx.se/libcurl/).
- Impostazione predefinita: usare <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).
- È possibile configurare questa impostazione a livello di codice chiamando il metodo <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `System.Net.Http.UseSocketsHttpHandler` | `true`-Abilita l'uso di <xref:System.Net.Http.SocketsHttpHandler><br/>`false`-Abilita l'uso di <xref:System.Net.Http.HttpClientHandler> |
| **Variabile di ambiente** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1`-Abilita l'uso di <xref:System.Net.Http.SocketsHttpHandler><br/>`0`-Abilita l'uso di <xref:System.Net.Http.HttpClientHandler> |
