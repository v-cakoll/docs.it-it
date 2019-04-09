---
title: Utilizzo degli strumenti di sviluppo WCF
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 1ffa3be4a6b8976ab978ea995e8b2c1faaacf0ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144638"
---
# <a name="using-the-wcf-development-tools"></a>Utilizzo degli strumenti di sviluppo WCF
In questa sezione vengono descritti gli strumenti di sviluppo di Visual Studio che possono facilitare lo sviluppo del servizio WCF.  
  
 È possibile usare i modelli di Visual Studio come base per compilare rapidamente un servizio personalizzato, quindi utilizzare Host automatico servizio di WCF e Client di prova WCF per eseguire il debug e testare il servizio. Questi strumenti forniscono funzioni di debug e test veloci e trasparenti e precludono la necessità di eseguire il commit a un modello di hosting in fase iniziale.  
  
## <a name="the-wcf-developer-tools"></a>Strumenti dello sviluppatore WCF  
 [Modelli di Visual Studio WCF](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 È possibile usare i modelli predefiniti di progetti ed elementi di Visual Studio in Visual Studio per compilare rapidamente i servizi WCF e le relative applicazioni.  
  
 [Host servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 L'Host automatico servizio di WCF (WcfSvcHost.exe) consente di avviare il debugger di Visual Studio (F5) per ospitare e testare un servizio che è stato implementato automaticamente. È quindi possibile testare il servizio utilizzando il Client di prova WCF (wcfTestClient.exe) o il proprio client di individuare e correggere qualsiasi errore potenziale.  
  
 [Client di test WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 Client di prova WCF (WcfTestClient.exe) è un strumento GUI che consente di immettere parametri di tipi arbitrari, inviare tale input al servizio e visualizzare che la risposta del servizio invia di nuovo. Fornisce un servizio facile test combinazione con Host automatico servizio di WCF.  
  
 [Generazione di classi di tipo dati da XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 I dati XML archiviati negli Appunti possono essere incollati in una tabella codici. Le classi definite nei dati verranno convertite in tipi di codice.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Utilizzo degli strumenti senza privilegio di amministratore  
 Per abilitare gli utenti senza privilegi di amministratore per lo sviluppo di servizi WCF, viene creato un ACL (Access Control List) per lo spazio dei nomi "http://+:8731/Design_Time_Addresses" durante l'installazione di Visual Studio. L'ACL viene impostato su (UI) che include tutti gli utenti interattivi che hanno eseguito l'accesso al computer. Gli amministratori possono aggiungere o possono utenti da questo ACL oppure aprire porte aggiuntive. Questo ACL aggiuntivo consente a WCF o ai modelli WF di inviare e ricevere dati nella relativa configurazione predefinita. Consente inoltre agli utenti di utilizzare Host automatico del servizio WCF (wcfSvcHost.exe) senza concedere loro privilegi di amministratore.  
  
 È inoltre possibile modificare l'accesso mediante lo strumento Netsh.exe disponibile in [!INCLUDE[wv](../../../includes/wv-md.md)] utilizzando l'account di amministratore con privilegi elevati. Di seguito è riportato un esempio di utilizzo di Netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Per altre informazioni sulle Netsh.exe, vedere [come usare lo strumento di Netsh.exe e opzioni della riga di comando](https://go.microsoft.com/fwlink/?LinkId=97877).  
  
## <a name="see-also"></a>Vedere anche

- [Modelli di Visual Studio WCF](../../../docs/framework/wcf/wcf-vs-templates.md)
- [Host servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
- [Client di test WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
