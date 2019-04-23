---
ms.openlocfilehash: 77d4978df76735d11f63c7118c1b4708b5b85502
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236029"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a>Rimuovere Ssl3 da TransportDefaults in WCF

|   |   |
|---|---|
|Dettagli|Quando si usa NetTcp con la sicurezza del trasporto e un tipo di certificato con credenziali, il protocollo SSL 3 non è più un protocollo predefinito usato per negoziare una connessione protetta. Nella maggior parte dei casi non vi sarà alcun impatto sulle applicazioni esistenti, poiché TLS 1.0 è sempre stato incluso nell'elenco di protocolli per NetTcp. Tutti i client esistenti devono essere in grado di negoziare una connessione usando almeno TLS1.0.|
|Suggerimento|Se è necessario il protocollo Ssl3, usare uno dei meccanismi di configurazione seguenti per aggiungere SsI3 all'elenco dei protocolli negoziati.<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[\<transport> di \<netTcpBinding>](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li>[Sezione &lt;sslStreamSecurity&gt; di &lt;customBinding&gt;](~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</li></ul>|
|Ambito|Microsoft Edge|
|Versione|4.6.2|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|
