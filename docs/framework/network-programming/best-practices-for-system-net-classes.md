---
title: Procedure consigliate per le classi System.Net
ms.date: 03/30/2017
helpviewer_keywords:
- sending data, best practices
- requesting data from Internet, best practices
- WebRequest class, best practices
- data requests, best practices
- WebResponse class, best practices
- best practices, data requests
- receiving data, best practices
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
ms.openlocfilehash: c7324dcbc27c95c7d799592700d46c195e7d952b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048885"
---
# <a name="best-practices-for-systemnet-classes"></a>Procedure consigliate per le classi System.Net
I suggerimenti seguenti consentono di usare al meglio le classi contenute in <xref:System.Net>:  
  
- Per le procedure consigliate per Transport Layer Security (TLS), vedere [Procedure consigliate per Transport Layer Security (TLS) con .NET Framework](tls.md).

- Se possibile, usare le classi <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> anziché eseguire cast di tipo nelle classi derivate. Le applicazioni che usano **WebRequest** e **WebResponse** possono usufruire dei nuovi protocolli Internet senza dover apportare modifiche significative al codice.  
  
- Quando si scrivono applicazioni ASP.NET da eseguire su un server mediante le classi **System.Net**, è spesso preferibile, in termini di prestazioni, usare i metodi asincroni per <xref:System.Net.WebRequest.GetResponse%2A> e <xref:System.Net.WebResponse.GetResponseStream%2A>.  
  
- Il numero di connessioni aperte a una risorsa Internet può influire in modo significativo sulle prestazioni di rete e sulla velocità effettiva. Per impostazione predefinita, **System.Net** usa due connessioni per ogni applicazione e per ogni host. Impostando la proprietà <xref:System.Net.ServicePoint.ConnectionLimit%2A> nella classe <xref:System.Net.ServicePoint> relativa all'applicazione, è possibile aumentare questo numero per un determinato host. L'impostazione della proprietà <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType> consente invece di aumentare il numero predefinito per tutti gli host.  
  
- Quando si scrivono protocolli di livello socket, è preferibile usare <xref:System.Net.Sockets.TcpClient> o <xref:System.Net.Sockets.UdpClient> anziché scrivere direttamente su un <xref:System.Net.Sockets.Socket>. Queste due classi client, infatti, incapsulano la creazione di socket TCP e UDP, evitando di dover gestire i dettagli della connessione.  
  
- Quando si accede a siti che richiedono credenziali, usare la classe <xref:System.Net.CredentialCache> per creare una cache di credenziali anziché fornirle con ogni richiesta. La classe **CredentialCache** cerca nella cache la credenziale appropriata da presentare con una richiesta, sollevando l'utente dalla responsabilità di creare e presentare credenziali in base all'URL.  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione di rete in .NET Framework](index.md)
