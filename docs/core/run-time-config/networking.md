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
# <a name="run-time-configuration-options-for-networking"></a>Opzioni di configurazione della fase di esecuzione per la rete

## <a name="http2-protocol"></a>Protocollo HTTP/2

- Configura se è abilitato il supporto per il protocollo HTTP/2.

- Se si omette questa impostazione, il supporto per il protocollo HTTP/2 è disabilitato. Equivale a impostare il valore su `false` .

- Introdotta in .NET Core 3,0.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false`-disabilitato<br/>`true`-abilitato |
| **Variabile di ambiente** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0`-disabilitato<br/>`1`-abilitato |

## <a name="usesocketshttphandler"></a>UseSocketsHttpHandler

- Configura se <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> Usa <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> o stack del protocollo http meno recenti ( <xref:System.Net.Http.WinHttpHandler> in Windows e `CurlHandler` , una classe interna implementata in [libcurl](https://curl.haxx.se/libcurl/)in Linux).

  > [!NOTE]
  > È possibile che si stiano usando API di rete di alto livello anziché creare direttamente un'istanza della <xref:System.Net.Http.HttpClientHandler> classe. Questa impostazione interessa anche lo stack di protocolli HTTP usato dalle API di rete di alto livello, tra cui <xref:System.Net.Http.HttpClient> e [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).

- Se si omette questa impostazione, <xref:System.Net.Http.HttpClientHandler> utilizza <xref:System.Net.Http.SocketsHttpHandler> . Equivale a impostare il valore su `true` .

- È possibile configurare questa impostazione a livello di codice chiamando il <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodo.

| | Nome impostazione | Valori |
| - | - | - |
| **runtimeconfig. JSON** | `System.Net.Http.UseSocketsHttpHandler` | `true`-Abilita l'uso di<xref:System.Net.Http.SocketsHttpHandler><br/>`false`-Abilita l'uso di <xref:System.Net.Http.WinHttpHandler> in Windows o [libcurl](https://curl.haxx.se/libcurl/) in Linux |
| **Variabile di ambiente** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1`-Abilita l'uso di<xref:System.Net.Http.SocketsHttpHandler><br/>`0`-Abilita l'uso di <xref:System.Net.Http.WinHttpHandler> in Windows o [libcurl](https://curl.haxx.se/libcurl/) in Linux |

> [!NOTE]
> A partire da .NET 5, l' `System.Net.Http.UseSocketsHttpHandler` impostazione non è più disponibile.
