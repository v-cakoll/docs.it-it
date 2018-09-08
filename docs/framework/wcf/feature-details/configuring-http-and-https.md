---
title: Configurazione di HTTP e HTTPS
ms.date: 03/30/2017
helpviewer_keywords:
- configuring HTTP [WCF]
ms.assetid: b0c29a86-bc0c-41b3-bc1e-4eb5bb5714d4
ms.openlocfilehash: 36dbf725dfcd6fefe6482f7de69daea9356d3d07
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087699"
---
# <a name="configuring-http-and-https"></a>Configurazione di HTTP e HTTPS
I client e i servizi WCF possono comunicare su HTTP e HTTPS. Le impostazioni HTTP/HTTPS vengono configurate tramite Internet Information Services (IIS) o tramite l'utilizzo di uno strumento da riga di comando. Quando un servizio WCF è ospitato in IIS è possibile configurare le impostazioni HTTP o HTTPS in IIS utilizzando lo strumento inetmgr.exe. Se un servizio WCF è indipendente, le impostazioni HTTP o HTTPS vengono configurate tramite uno strumento da riga di comando.  
  
 Sarà necessario almeno configurare la registrazione di un URL e aggiungere un'eccezione del firewall per l'URL che sarà utilizzato dal servizio.  
  
 Lo strumento utilizzato per configurare le impostazioni HTTP dipende dal sistema operativo in esecuzione nel computer.  
  
 Quando si esegue [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], utilizzare lo strumento HttpCfg.exe. [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] installa automaticamente questo strumento. Quando si esegue [!INCLUDE[wxp](../../../../includes/wxp-md.md)], è possibile scaricare lo strumento [strumenti di supporto di Windows XP Service Pack 2](https://go.microsoft.com/fwlink/?LinkId=88606). Per altre informazioni, vedere [Panoramica di Httpcfg](https://go.microsoft.com/fwlink/?LinkId=88605).  
  
 Quando si esegue [!INCLUDE[wv](../../../../includes/wv-md.md)] o Windows 7, aver configurato queste impostazioni con lo strumento Netsh.exe.  
  
## <a name="configuring-namespace-reservations"></a>Configurazione delle prenotazioni dello spazio dei nomi  
 La prenotazione dello spazio dei nomi assegna i diritti per una parte dello spazio dei nomi URL HTTP a un particolare gruppo di utenti. Una prenotazione concede a quegli utenti il diritto di creare servizi in ascolto sulla parte dello spazio dei nomi. Le prenotazioni sono prefissi URL, pertanto la prenotazione riguarda tutti i sottopercorsi del percorso di prenotazione. Le prenotazioni dello spazio dei nomi permettono due modalità per utilizzare caratteri jolly. La documentazione dell'API Server HTTP viene descritto il [ordine di risoluzione tra attestazioni dello spazio dei nomi che implicano caratteri jolly](https://go.microsoft.com/fwlink/?LinkId=94841).  
  
 Un'applicazione in esecuzione può creare una richiesta simile per aggiungere registrazioni dello spazio dei nomi. Registrazioni e prenotazioni competono per parti dello spazio dei nomi. Una prenotazione può avere precedenza su una registrazione a seconda dell'ordine di risoluzione indicato nel [ordine di risoluzione tra attestazioni dello spazio dei nomi che implicano caratteri jolly](https://go.microsoft.com/fwlink/?LinkId=94841). In questo caso, la prenotazione blocca la ricezione delle richieste da parte dell'applicazione in esecuzione.  
  
### <a name="running-windows-xp-or-server-2003"></a>Esecuzione di Windows XP o di Windows Server 2003  
 Usare il `httpcfg.exe set urlacl` comando per modificare le prenotazioni dello spazio dei nomi. Il [documentazione di Windows Support Tools](https://go.microsoft.com/fwlink/?LinkId=94840) viene illustrata la sintassi per lo strumento Httpcfg.exe. La modifica dei diritti di prenotazione per una parte dello spazio dei nomi richiede privilegi amministrativi o la proprietà della parte in questione dello spazio dei nomi. Inizialmente, l'intero spazio dei nomi HTTP appartiene all'amministratore locale.  
  
 Nell'esempio seguente viene illustrata la sintassi del comando Httpcfg con l'opzione `set urlacl`  
  
```  
httpcfg set urlacl /u {http://URL:Port/ | https://URL:Port/} /aACL  
```  
  
 Quando si utilizza `/u` è necessario il parametro `set urlacl`, che accetta una stringa contenente un URL completo che funge da chiave record per la prenotazione eseguita.  
  
 Quando si utilizza `/a` è necessario anche il parametro `set urlacl`, che accetta una stringa contenente un elenco di controllo di accesso (ACL) in forma di stringa SDDL (Security Descriptor Definition Language).  
  
 Di seguito viene illustrato un esempio di utilizzo del comando.  
  
```  
httpcfg.exe set urlacl /u http://myhost:8000/ /a "O:AOG:DAD:(A;;RPWPCCDCLCSWRCWDWOGA;;;S-1-0-0)"  
```  
  
### <a name="running-windows-vista-windows-server-2008-r2-or-windows-7"></a>Esecuzione di Windows Vista, Windows Server 2008 R2 o Windows 7  
 Se si esegue l'applicazione in [!INCLUDE[wv](../../../../includes/wv-md.md)], Windows Server 2008 R2 o Windows 7, utilizzare lo strumento Netsh.exe. Di seguito viene illustrato un esempio di utilizzo del comando.  
  
```  
netsh http add urlacl url=http://+:80/MyUri user=DOMAIN\user  
```  
  
 Questo comando aggiunge una prenotazione URL per lo spazio dei nomi URL specificato per l'account DOMAIN\user.  Per altre informazioni sull'uso del tipo di comando netsh "netsh http add urlacl" in un prompt dei comandi e premere immettere.  
  
## <a name="configuring-a-firewall-exception"></a>Configurazione di un'eccezione del firewall  
 In caso di un servizio WCF self-hosted che comunica tramite HTTP, è necessario aggiungere un'eccezione alla configurazione del firewall per consentire connessioni in ingresso tramite un particolare URL. Per altre informazioni, vedere [aprire una porta nel Firewall di Windows (Windows 7)](https://go.microsoft.com/fwlink/?LinkId=239961)  
  
## <a name="configuring-ssl-certificates"></a>Configurazione di certificati SSL  
 Il protocollo SSL (Secure Sockets Layer) utilizza certificati nel client e nel server per memorizzare le chiavi di crittografia. Il server fornisce il proprio certificato SSL quando viene stabilita una connessione, in modo che il client possa verificare l'identità del server. Il server può inoltre richiedere un certificato dal client, per fornire l'autenticazione reciproca di entrambi i lati della connessione.  
  
 I certificati vengono memorizzati in un archivio centralizzato in base all'indirizzo IP e al numero di porta della connessione. L'indirizzo IP speciale 0.0.0.0 corrisponde a qualsiasi indirizzo IP del computer locale. Si noti che l'archivio certificati non distingue gli URL in base al percorso. I servizi con la stessa combinazione di indirizzo IP e porta deve condividere certificati anche se il percorso nell'URL dei servizi è diverso.  
  
 Per istruzioni dettagliate, vedere [procedura: configurare una porta con un certificato SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
## <a name="configuring-the-ip-listen-list"></a>Configurazione dell'elenco di ascolto IP  
 L'API server HTTP viene associata a un indirizzo IP e a una porta solo quando un utente registra un URL. Per impostazione predefinita, l'API server HTTP viene associata alla porta nell'URL per tutti gli indirizzi IP del computer. Nasce un conflitto se un'applicazione che non utilizza l'API server HTTP è stata precedentemente associata alla combinazione in questione di indirizzo IP e porta. L'elenco di ascolto IP consente ai servizi WCF coesistere con applicazioni che usano una porta per alcuni degli indirizzi IP della macchina. Se l'elenco di ascolto IP contiene voci, l'API server HTTP viene associata solo agli indirizzi IP specificati nell'elenco. La modifica dell'elenco di ascolto IP richiede privilegi amministrativi.  
  
### <a name="running-windows-xp-or-server-2003"></a>Esecuzione di Windows XP o di Windows Server 2003  
 Utilizzare lo strumento httpcfg per modificare l'elenco di ascolto IP, come illustrato nell'esempio seguente. Il [documentazione di Windows Support Tools](https://go.microsoft.com/fwlink/?LinkId=94840) viene illustrata la sintassi per lo strumento httpcfg.exe.  
  
```  
httpcfg.exe set iplisten -i 0.0.0.0:8000  
```  
  
### <a name="running-windows-vista-or-windows-7"></a>Esecuzione di Windows Vista o Windows 7  
 Utilizzare lo strumento netsh per modificare l'elenco di ascolto IP, come illustrato nell'esempio seguente.  
  
```  
netsh http add iplisten ipaddress=0.0.0.0:8000  
```  
  
## <a name="other-configuration-settings"></a>Altre impostazioni di configurazione  
 Quando si utilizza <xref:System.ServiceModel.WSDualHttpBinding>, la connessione client utilizza impostazioni predefinite compatibili con le prenotazioni dello spazio dei nomi e il firewall Windows. Se si sceglie di personalizzare l'indirizzo client di base di una connessione doppia, è necessario configurare anche queste impostazioni HTTP sul client per farle corrispondere al nuovo indirizzo.  
  
 L'API server HTTP prevede alcune impostazioni di configurazione avanzate non disponibili tramite HttpCfg. Queste impostazioni vengono mantenute nel Registro di sistema e valgono per tutte le applicazioni in esecuzione sui sistemi che utilizzano API server HTTP. Per informazioni su queste impostazioni, vedere [impostazioni del Registro di sistema HTTP. sys per IIS](https://go.microsoft.com/fwlink/?LinkId=94843). La maggior parte degli utenti non dovrebbe avere la necessità di modificare queste impostazioni.  
  
## <a name="issues-specific-to-windows-xp"></a>Problemi specifici di Windows XP  
 IIS non supporta la condivisione delle porte su [!INCLUDE[wxp](../../../../includes/wxp-md.md)]. Se IIS è in esecuzione e un servizio WCF tenta di usare uno spazio dei nomi con la stessa porta, il servizio WCF non verrà avviato. IIS e WCF che sia per impostazione predefinita utilizza la porta 80. Modificare l'assegnazione della porta per uno dei servizi o utilizzare l'elenco di ascolto IP per assegnare il servizio WCF a una scheda di rete non utilizzata da IIS. IIS 6.0 e versioni successive sono stati riprogettati per utilizzare API server HTTP.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.WSDualHttpBinding>  
 [Procedura: Configurare una porta con un certificato SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
