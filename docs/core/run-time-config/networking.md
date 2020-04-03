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
# <a name="run-time-configuration-options-for-networking"></a>Opzioni di configurazione in fase di esecuzione per la rete

## <a name="http2-protocol"></a>Protocollo HTTP/2

- Configura se il supporto per il protocollo HTTP/2 è abilitato.
- Impostazione predefinita: Disabilitato (`false`).
- Introdotto in .NET Core 3.0.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false`- disabilitato<br/>`true`- abilitato |
| **Variabile di ambiente** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0`- disabilitato<br/>`1`- abilitato |

## <a name="usesocketshttphandler"></a>UseSocketsHttpHandler

- Configura se le API di rete di <xref:System.Net.Http.HttpClient>alto <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> livello, <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> ad esempio , utilizzano o l'implementazione di tale è basata su [libcurl](https://curl.haxx.se/libcurl/).
- Impostazione <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> predefinita: utilizzo ( ).`true`
- È possibile configurare questa impostazione a livello di codice chiamando il <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodo .

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true`- consente l'uso di<xref:System.Net.Http.SocketsHttpHandler><br/>`false`- consente l'uso di<xref:System.Net.Http.HttpClientHandler> |
| **Variabile di ambiente** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1`- consente l'uso di<xref:System.Net.Http.SocketsHttpHandler><br/>`0`- consente l'uso di<xref:System.Net.Http.HttpClientHandler> |

> [!NOTE]
> A partire da .NET 5, l'impostazione `System.Net.Http.UseSocketsHttpHandler` non è più disponibile.
