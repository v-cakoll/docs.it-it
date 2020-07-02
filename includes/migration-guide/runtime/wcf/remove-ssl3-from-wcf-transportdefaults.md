---
ms.openlocfilehash: 9b734fe960165b6d4b97b861cb3e8f31979f25c5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621211"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a>Rimuovere Ssl3 da TransportDefaults in WCF

#### <a name="details"></a>Dettagli

Quando si usa NetTcp con la sicurezza del trasporto e un tipo di certificato con credenziali, il protocollo SSL 3 non è più un protocollo predefinito usato per negoziare una connessione protetta. Nella maggior parte dei casi non vi sarà alcun impatto sulle applicazioni esistenti, poiché TLS 1.0 è sempre stato incluso nell'elenco di protocolli per NetTcp. Tutti i client esistenti devono essere in grado di negoziare una connessione usando almeno TLS1.0.

#### <a name="suggestion"></a>Suggerimento

Se è necessario il protocollo Ssl3, usare uno dei meccanismi di configurazione seguenti per aggiungere SsI3 all'elenco dei protocolli negoziati.<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li>Sezione [&lt;sslStreamSecurity&gt; di &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</li></ul>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.6.2|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|
