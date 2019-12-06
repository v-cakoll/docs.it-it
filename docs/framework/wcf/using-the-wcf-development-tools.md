---
title: Uso degli strumenti di sviluppo WCF
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 8253a9136b2310deeb7c6d162a9f190c13ba02da
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837727"
---
# <a name="using-the-wcf-development-tools"></a>Uso degli strumenti di sviluppo WCF
Questa sezione descrive gli strumenti di sviluppo di Visual Studio che possono risultare utili per lo sviluppo di WCFservice.  
  
 È possibile utilizzare i modelli di Visual Studio come base per creare rapidamente un servizio personalizzato, quindi utilizzare l'host automatico del servizio WCF e il client di prova WCF per eseguire il debug e il test del servizio. Questi strumenti forniscono funzioni di debug e test veloci e trasparenti e precludono la necessità di eseguire il commit a un modello di hosting in fase iniziale.  
 
 > [!NOTE]
 > A partire da Visual Studio 2017, gli strumenti di sviluppo WCF non sono installati per impostazione predefinita. Per usare queste funzionalità, è necessario assicurarsi che il componente Windows Communication Foundation sia selezionato nel programma di installazione di Visual Studio.
  
## <a name="the-wcf-developer-tools"></a>Strumenti dello sviluppatore WCF  
 [Modelli di Visual Studio WCF](wcf-vs-templates.md)  
  
 È possibile utilizzare i modelli di progetto e di elemento predefiniti di Visual Studio in Visual Studio per compilare rapidamente i servizi WCF e le applicazioni circostanti.  
  
 [Host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)  
  
 L'host automatico del servizio WCF (WcfSvcHost. exe) consente di avviare il debugger di Visual Studio (F5) per ospitare e testare automaticamente un servizio implementato. È quindi possibile testare il servizio utilizzando il client di prova WCF (wcfTestClient. exe) o il client per individuare e correggere eventuali errori potenziali.  
  
 [Client di prova WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)  
  
 Il client di prova WCF (WcfTestClient. exe) è uno strumento GUI che consente di immettere parametri di tipi arbitrari, inviare tale input al servizio e visualizzare la risposta restituita dal servizio. Offre un'esperienza di test dei servizi senza problemi in combinazione con l'host automatico del servizio WCF.  
  
 [Generazione di classi di tipi dati da XML](generating-data-type-classes-from-xml.md)  
  
 I dati XML archiviati negli Appunti possono essere incollati in una tabella codici. Le classi definite nei dati verranno convertite in tipi di codice.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Utilizzo degli strumenti senza privilegio di amministratore  
 Per consentire agli utenti senza privilegi di amministratore di sviluppare servizi WCF, viene creato un ACL (elenco di controllo di accesso) per lo spazio dei nomi "http://+:8731/Design_Time_Addresses" durante l'installazione di Visual Studio. L'ACL viene impostato su (UI) che include tutti gli utenti interattivi che hanno eseguito l'accesso al computer. Gli amministratori possono aggiungere o possono utenti da questo ACL oppure aprire porte aggiuntive. Questo ACL aggiuntivo consente a WCF o ai modelli WF di inviare e ricevere dati nella relativa configurazione predefinita. Consente inoltre agli utenti di utilizzare l'host automatico del servizio WCF (wcfSvcHost. exe) senza concedere loro privilegi di amministratore.  
  
 È possibile modificare l'accesso utilizzando lo strumento Netsh. exe in Windows Vista con l'account amministratore con privilegi elevati. Di seguito è riportato un esempio di utilizzo di Netsh.exe.  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Per ulteriori informazioni su Netsh. exe, vedere [come utilizzare lo strumento Netsh. exe e le opzioni della riga di comando](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).  
  
## <a name="see-also"></a>Vedere anche

- [Modelli di Visual Studio WCF](wcf-vs-templates.md)
- [Host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [Client di prova WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
