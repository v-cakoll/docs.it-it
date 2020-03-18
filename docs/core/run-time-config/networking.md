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
# <a name="run-time-configuration-options-for-networking"></a>Opzioni di configurazione in fase di esecuzione per la rete

## <a name="http2-protocol"></a>Protocollo HTTP/2

- Configura se il supporto per il protocollo HTTP/2 è abilitato.
- Impostazione predefinita: Disabilitato (`false`).
- Introdotto in .NET Core 3.0.

| | Nome impostazione | Valori |
| - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false`- disabilitato<br/>`true`- abilitato |
| **Variabile di ambiente** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0`- disabilitato<br/>`1`- abilitato |

## <a name="sockets-http-handler"></a>Gestore HTTP Sockets

- Configura se le API di rete di <xref:System.Net.Http.HttpClient>alto <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> livello, <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> ad esempio , utilizzano o l'implementazione di tale è basata su [libcurl](https://curl.haxx.se/libcurl/).
- Impostazione <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> predefinita: utilizzo ( ).`true`
- È possibile configurare questa impostazione a livello di codice chiamando il <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodo .

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true`- consente l'uso di<xref:System.Net.Http.SocketsHttpHandler><br/>`false`- consente l'uso di<xref:System.Net.Http.HttpClientHandler> |
| **Variabile di ambiente** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1`- consente l'uso di<xref:System.Net.Http.SocketsHttpHandler><br/>`0`- consente l'uso di<xref:System.Net.Http.HttpClientHandler> |
