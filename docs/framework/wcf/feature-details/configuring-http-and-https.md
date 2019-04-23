---
title: Configurazione di HTTP e HTTPS - WCF
ms.date: 04/08/2019
helpviewer_keywords:
- configuring HTTP [WCF]
ms.assetid: b0c29a86-bc0c-41b3-bc1e-4eb5bb5714d4
ms.openlocfilehash: 86705a4f8daa327c442ac6c53c9b44c5b5c5c2ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59427175"
---
# <a name="configuring-http-and-https"></a>Configurazione di HTTP e HTTPS

I client e i servizi WCF possono comunicare su HTTP e HTTPS. Le impostazioni HTTP/HTTPS vengono configurate tramite Internet Information Services (IIS) o tramite l'utilizzo di uno strumento da riga di comando. Quando un servizio WCF è ospitato in IIS è possibile configurare le impostazioni HTTP o HTTPS in IIS utilizzando lo strumento inetmgr.exe. Se un servizio WCF è indipendente, le impostazioni HTTP o HTTPS vengono configurate tramite uno strumento da riga di comando.

Come minimo, si desidera configurare la registrazione di un URL e aggiungere un'eccezione del Firewall per l'URL verrà usato il servizio. È possibile configurare queste impostazioni con lo strumento Netsh.exe.

## <a name="configuring-namespace-reservations"></a>Configurazione delle prenotazioni dello spazio dei nomi

La prenotazione dello spazio dei nomi assegna i diritti per una parte dello spazio dei nomi URL HTTP a un particolare gruppo di utenti. Una prenotazione concede a quegli utenti il diritto di creare servizi in ascolto sulla parte dello spazio dei nomi. Le prenotazioni sono prefissi URL, vale a dire che la prenotazione riguarda tutti i sottopercorsi del percorso di prenotazione. Le prenotazioni dello spazio dei nomi permettono due modalità per utilizzare caratteri jolly. La documentazione dell'API Server HTTP viene descritto il [ordine di risoluzione tra attestazioni dello spazio dei nomi che implicano caratteri jolly](/windows/desktop/Http/routing-incoming-requests).

Un'applicazione in esecuzione può creare una richiesta simile per aggiungere registrazioni dello spazio dei nomi. Registrazioni e prenotazioni competono per parti dello spazio dei nomi. Una prenotazione può avere precedenza su una registrazione a seconda dell'ordine di risoluzione indicato nel [ordine di risoluzione tra attestazioni dello spazio dei nomi che implicano caratteri jolly](/windows/desktop/Http/routing-incoming-requests). In questo caso, la prenotazione blocca la ricezione delle richieste da parte dell'applicazione in esecuzione.

Nell'esempio seguente usa lo strumento Netsh.exe:

```console
netsh http add urlacl url=http://+:80/MyUri user=DOMAIN\user
```

Questo comando aggiunge una prenotazione URL per lo spazio dei nomi URL specificato per l'account DOMAIN\User. Per altre informazioni sull'uso del comando netsh, digitare `netsh http add urlacl /?` in un prompt dei comandi e premere INVIO.

## <a name="configuring-a-firewall-exception"></a>Configurazione di un'eccezione del firewall

In caso di un servizio WCF self-hosted che comunica tramite HTTP, è necessario aggiungere un'eccezione alla configurazione del firewall per consentire connessioni in ingresso tramite un particolare URL.

## <a name="configuring-ssl-certificates"></a>Configurazione dei certificati SSL

Il protocollo SSL (Secure Sockets Layer) utilizza certificati nel client e nel server per memorizzare le chiavi di crittografia. Il server fornisce il proprio certificato SSL quando viene stabilita una connessione, in modo che il client possa verificare l'identità del server. Il server può inoltre richiedere un certificato dal client, per fornire l'autenticazione reciproca di entrambi i lati della connessione.

I certificati vengono memorizzati in un archivio centralizzato in base all'indirizzo IP e al numero di porta della connessione. L'indirizzo IP speciale 0.0.0.0 corrisponde a qualsiasi indirizzo IP del computer locale. Si noti che l'archivio certificati non distingue gli URL basati sul percorso. I servizi con la stessa combinazione di indirizzo IP e porta deve condividere certificati anche se il percorso nell'URL dei servizi è diverso.

Per istruzioni dettagliate, vedere [come: Configurare una porta con un certificato SSL](how-to-configure-a-port-with-an-ssl-certificate.md).

## <a name="configuring-the-ip-listen-list"></a>Configurazione dell'elenco di ascolto IP

L'API server HTTP viene associata a un indirizzo IP e a una porta solo quando un utente registra un URL. Per impostazione predefinita, l'API server HTTP viene associata alla porta nell'URL per tutti gli indirizzi IP del computer. Si verifica un conflitto se un'applicazione che non usa l'API Server HTTP è stata precedentemente associata a tale combinazione di indirizzo IP e porta. L'elenco di ascolto IP consente ai servizi WCF coesistere con applicazioni che usano una porta per alcuni degli indirizzi IP della macchina. Se l'elenco di ascolto IP contiene voci, l'API server HTTP viene associata solo agli indirizzi IP specificati nell'elenco. La modifica dell'elenco di ascolto IP richiede privilegi amministrativi.

Usare lo strumento netsh per modificare l'elenco di ascolto IP, come illustrato nell'esempio seguente:

```console
netsh http add iplisten ipaddress=0.0.0.0:8000
```

## <a name="other-configuration-settings"></a>Altre impostazioni di configurazione

Quando si utilizza <xref:System.ServiceModel.WSDualHttpBinding>, la connessione client utilizza impostazioni predefinite compatibili con le prenotazioni dello spazio dei nomi e il firewall Windows. Se si sceglie di personalizzare l'indirizzo client di base di una connessione doppia, è necessario configurare anche queste impostazioni HTTP sul client per farle corrispondere al nuovo indirizzo.

L'API Server HTTP ha alcune impostazioni di configurazione avanzata che non sono disponibili tramite HttpCfg. Queste impostazioni vengono mantenute nel Registro di sistema e valgono per tutte le applicazioni in esecuzione sui sistemi che utilizzano API server HTTP. Per informazioni su queste impostazioni, vedere [impostazioni del Registro di sistema HTTP. sys per IIS](https://support.microsoft.com/en-us/help/820129/http-sys-registry-settings-for-windows). La maggior parte degli utenti non necessario modificare queste impostazioni.

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.WSDualHttpBinding>
- [Procedura: Configurare una porta con un certificato SSL](how-to-configure-a-port-with-an-ssl-certificate.md)
