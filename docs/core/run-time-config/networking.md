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

- Configura se <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> utilizza o precedenti stack<xref:System.Net.Http.WinHttpHandler> di `CurlHandler`protocollo HTTP (in Windows e , una classe interna implementata su [libcurl](https://curl.haxx.se/libcurl/), su Linux).

  > [!NOTE]
  > È possibile che si utilizzino API di rete di <xref:System.Net.Http.HttpClientHandler> alto livello anziché creare direttamente un'istanza della classe. Questa impostazione influisce anche sullo stack di protocollo HTTP utilizzato <xref:System.Net.Http.HttpClient> dalle API di rete di alto livello, tra cui e [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).

- Impostazione <xref:System.Net.Http.SocketsHttpHandler> predefinita: utilizzo ( ).`true`

- È possibile configurare questa impostazione a livello di codice chiamando il <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodo .

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true`- consente l'uso di<xref:System.Net.Http.SocketsHttpHandler><br/>`false`- consente l'uso di <xref:System.Net.Http.WinHttpHandler> su Windows o [libcurl](https://curl.haxx.se/libcurl/) su Linux |
| **Variabile di ambiente** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1`- consente l'uso di<xref:System.Net.Http.SocketsHttpHandler><br/>`0`- consente l'uso di <xref:System.Net.Http.WinHttpHandler> su Windows o [libcurl](https://curl.haxx.se/libcurl/) su Linux |

> [!NOTE]
> A partire da .NET 5, l'impostazione `System.Net.Http.UseSocketsHttpHandler` non è più disponibile.
