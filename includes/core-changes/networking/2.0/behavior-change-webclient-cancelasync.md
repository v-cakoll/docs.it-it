---
ms.openlocfilehash: 80d4bbbfe52ab9685d7ca54f21b80d4b1773da22
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859630"
---
### <a name="webclientcancelasync-doesnt-always-cancel-immediately"></a>WebClient. CancelAsync non viene sempre annullato immediatamente

A partire da .NET Core 2,0, <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> la chiamata a non annulla la richiesta immediatamente se la risposta è stata avviata per il recupero.

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> chiamando immediatamente la richiesta è stata annullata. A partire da .NET Core 2,0, <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> la chiamata a Annulla la richiesta immediatamente solo se la risposta non ha iniziato a recuperare. Se la risposta ha iniziato a recuperare, la richiesta viene annullata solo dopo la lettura di una risposta completa.

Questa modifica è stata implementata <xref:System.Net.WebClient> perché l'API è deprecata a <xref:System.Net.Http.HttpClient>favore di.

#### <a name="version-introduced"></a>Versione introdotta

2.0

#### <a name="recommended-action"></a>Azione consigliata

Utilizzare la <xref:System.Net.Http.HttpClient?displayProperty=fullName> classe anziché <xref:System.Net.WebClient?displayProperty=fullName>, che è deprecata.

#### <a name="category"></a>Categoria

Rete

#### <a name="affected-apis"></a>API interessate

- <xref:System.Net.WebClient.CancelAsync?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.WebClient.CancelAsync`

-->
