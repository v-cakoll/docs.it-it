---
title: Attraversamento NAT con IPv6 e Teredo
ms.date: 03/30/2017
ms.assetid: 568cd245-3300-49ef-a995-d81bf845d961
ms.openlocfilehash: f617dc8912091576727b90da1e9efb9ebd5f9bda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "61642178"
---
# <a name="nat-traversal-using-ipv6-and-teredo"></a>Attraversamento NAT con IPv6 e Teredo
Sono stati introdotti miglioramenti per il supporto dell'attraversamento NAT (Network Address Translation). Queste modifiche sono progettate per l'uso con IPv6 e Teredo, ma sono applicabili anche ad altre tecnologie di tunneling IP. Questi miglioramenti hanno effetti sulle classi in <xref:System.Net> e sugli spazi dei nomi correlati.  
  
 Queste modifiche possono influire sulle applicazioni client e server che prevedono di usare tecnologie di tunneling IP.  
  
 Le modifiche per il supporto dell'attraversamento NAT sono disponibili solo per le applicazioni che usano .NET Framework versione 4. Queste funzionalità non sono disponibili nelle versioni precedenti di .NET Framework.  
  
## <a name="overview"></a>Panoramica  
 Internet Protocol versione 4 (IPv4) definisce un indirizzo IPv4 con una lunghezza di 32 bit. Di conseguenza, IPv4 supporta circa 4 miliardi di indirizzi IP univoci (2^32). Con la grande crescita del numero di computer e dispositivi di rete in Internet negli anni '90 sono diventati evidenti i limiti dello spazio indirizzi IPv4.  
  
 Una delle diverse tecniche usate per estendere la durata di IPv4 è stata distribuire NAT per consentire a un singolo indirizzo IP pubblico univoco di rappresentare un numero elevato di indirizzi IP privati (Intranet privata). Gli indirizzi IP privati dietro il dispositivo NAT condividono un singolo indirizzo IPv4 pubblico. Il dispositivo NAT può essere un dispositivo hardware dedicato (ad esempio, un punto di accesso wireless e router economico) o un computer che esegue un servizio per fornire funzionalità NAT. Un dispositivo o un servizio per questo indirizzo IP pubblico converte i pacchetti di rete IP tra la rete Internet pubblica e la rete Intranet privata.  
  
 Questo schema è appropriato per le applicazioni client eseguite sulla rete Intranet privata che inviano richieste ad altri indirizzi IP (in genere i server) su Internet. Il dispositivo NAT o il server può mantenere aggiornato un mapping delle richieste client, in modo che alla restituzione di una risposta sappia dove inviarla. Ma questo schema pone problemi per le applicazioni in esecuzione nella rete Intranet privata dietro il dispositivo NAT che vogliono fornire servizi, restare in ascolto dei pacchetti e rispondere. Ciò è vero in particolare per le applicazioni peer-to-peer.  
  
 Il protocollo IPv6 definisce un indirizzo IPv4 con una lunghezza di 128 bit. Di conseguenza, IPv6 supporta uno spazio indirizzi IP molto grande, pari a 3,2 x 10^38 indirizzi univoci (2^128). Con uno spazio indirizzi di queste dimensioni, a ogni dispositivo connesso a Internet può essere assegnato un indirizzo univoco. Ci sono però dei problemi. Gran parte del mondo continua a usare solo IPv4. In particolare, molti dei router e dei punti di accesso wireless esistenti usati da piccole imprese, organizzazioni e privati non supportano IPv6. Anche alcuni provider di servizi Internet che offrono i loro servizi a questo tipo di clienti non supportano o non hanno configurato il supporto per IPv6.  
  
 Sono state sviluppate varie tecnologie per la transizione a IPv6 per eseguire il tunneling di indirizzi IPv6 in un pacchetto IPv4. Queste tecnologie includono tunnel 6to4, ISATAP e Teredo che gestiscono l'assegnazione di indirizzi e il tunneling automatico da host a host per il traffico unicast IPv6 quando gli host IPv6 devono attraversare reti IPv4 per raggiungere altre reti IPv6. I pacchetti IPv6 vengono inviati tramite tunnel come pacchetti IPv4. Sono attualmente in uso varie tecniche di tunneling per consentire l'attraversamento NAT per gli indirizzi IPv6 attraverso un dispositivo NAT.  
  
 Teredo è una delle tecnologie per la transizione a IPv6 che rende disponibile la connettività IPv6 per le reti IPv4. Teredo è documentato nella specifica RFC 4380 pubblicata da Internet Engineering Task Force (IETF). Windows XP SP2 e versioni successive forniscono il supporto per una scheda Teredo virtuale che può fornire un indirizzo IPv6 pubblico nell'intervallo 2001:0::/32. Questo indirizzo IPv6 può essere usato per l'ascolto delle connessioni in ingresso da Internet e può essere fornito ai client abilitati per IPv6 che vogliono connettersi al servizio in ascolto. In questo modo, un'applicazione non deve preoccuparsi di come gestire l'indirizzo per un computer protetto da un dispositivo NAT, dato che può semplicemente connettersi a esso tramite il relativo indirizzo Teredo IPv6.  
  
## <a name="enhancements-to-support-nat-traversal-and-teredo"></a>Miglioramenti al supporto dell'attraversamento NAT e Teredo  
 Sono stati introdotti miglioramenti per gli spazi dei nomi <xref:System.Net>, <xref:System.Net.NetworkInformation> e <xref:System.Net.Sockets> per il supporto dell'attraversamento NAT con IPv6 e Teredo.  
  
 Sono stati aggiunti vari metodi alla classe <xref:System.Net.NetworkInformation.IPGlobalProperties?displayProperty=nameWithType> per ottenere l'elenco di indirizzi IP unicast nell'host. Il metodo <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A> avvia una richiesta asincrona per recuperare la tabella di indirizzi IP unicast stabili nel computer locale. Il metodo <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A> termina una richiesta asincrona in sospeso per recuperare la tabella di indirizzi IP unicast stabili nel computer locale. Il metodo <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A> è una richiesta sincrona per recuperare la tabella di indirizzi IP unicast stabili nel computer locale, aspettando che la tabella di indirizzi si stabilizzi se necessario.  
  
 È possibile usare la proprietà <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=nameWithType> per determinare se un <xref:System.Net.IPAddress> è un indirizzo IPv6 Teredo.  
  
 L'uso di questi nuovi metodi della classe <xref:System.Net.NetworkInformation.IPGlobalProperties> in combinazione con la proprietà <xref:System.Net.IPAddress.IsIPv6Teredo%2A> consente a un'applicazione di trovare con facilità l'indirizzo Teredo. Un'applicazione ha in genere solo l'esigenza di conoscere l'indirizzo Teredo locale se comunica queste informazioni ad applicazioni remote. Ad esempio, un'applicazione peer-to-peer potrebbe inviare tutti i relativi indirizzi IPv6 a un server di matchmaking che può quindi inoltrarli agli altri peer per consentire la comunicazione diretta.  
  
 Un'applicazione deve impostare normalmente il servizio di ascolto per l'ascolto di <xref:System.Net.IPAddress.IPv6Any?displayProperty=nameWithType> anziché dell'indirizzo Teredo locale. In questo modo, se un client remoto o peer dispone di una route IPv6 diretta all'host del servizio di ascolto, il client o il peer può connettersi direttamente tramite IPv6 senza dover usare Teredo per il tunneling dei pacchetti.  
  
 Per le applicazioni TCP, la classe <xref:System.Net.Sockets.TcpListener?displayProperty=nameWithType> include un metodo <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A> per abilitare l'attraversamento NAT. Per le applicazioni UDP, la classe <xref:System.Net.Sockets.UdpClient?displayProperty=nameWithType> include un metodo <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A> per abilitare l'attraversamento NAT.  
  
 Per le applicazioni che usano la classe <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> e le classi correlate, è possibile usare i metodi <xref:System.Net.Sockets.Socket.GetSocketOption%2A> e <xref:System.Net.Sockets.Socket.SetSocketOption%2A> con l'opzione socket <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType> per ottenere, abilitare o disabilitare l'attraversamento NAT.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=nameWithType>
- <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A?displayProperty=nameWithType>
- <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A?displayProperty=nameWithType>
- <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.SetIPProtectionLevel%2A?displayProperty=nameWithType>
- <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A?displayProperty=nameWithType>
- <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A?displayProperty=nameWithType>
