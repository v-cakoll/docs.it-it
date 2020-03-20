---
title: Utilizzo degli strumenti di sviluppo WCF
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 82bb7e225492bcdba4d2e611de405a09571355c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183073"
---
# <a name="using-the-wcf-development-tools"></a>Utilizzo degli strumenti di sviluppo WCF
In questa sezione vengono descritti gli strumenti di sviluppo di Visual Studio che consentono di sviluppare il servizio WCF.  
  
 È possibile usare i modelli di Visual Studio come base per compilare rapidamente il proprio servizio, quindi usare l'host automatico del servizio WCF e il client di test WCF per eseguire il debug e testare il servizio. Questi strumenti forniscono funzioni di debug e test veloci e trasparenti e precludono la necessità di eseguire il commit a un modello di hosting in fase iniziale.  

 > [!NOTE]
 > A partire da Visual Studio 2017, gli strumenti di sviluppo WCF non vengono installati per impostazione predefinita. Per utilizzare queste funzionalità, è necessario assicurarsi che il componente Windows Communication Foundation sia selezionato nel programma di installazione di Visual Studio.In order to use these features, you must ensure the Windows Communication Foundation component is selected in the Visual Studio installer.
  
## <a name="the-wcf-developer-tools"></a>Strumenti dello sviluppatore WCF  
 [Modelli di Visual Studio WCF](wcf-vs-templates.md)  
  
 È possibile usare il progetto di Visual Studio predefinito e i modelli di elemento in Visual Studio per compilare rapidamente i servizi WCF e le applicazioni circostanti.  
  
 [Host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)  
  
 L'host automatico del servizio WCF (WcfSvcHost.exe) consente di avviare il debugger di Visual Studio (F5) per ospitare e testare automaticamente un servizio implementato. È quindi possibile testare il servizio utilizzando il Client di Test WCF (wcfTestClient.exe) o il proprio client per trovare e correggere eventuali errori potenziali.  
  
 [Client di prova WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)  
  
 Client di test WCF (WcfTestClient.exe) è uno strumento GUI che consente di immettere parametri di tipi arbitrari, inviare tale input al servizio e visualizzare la risposta inviata dal servizio. Fornisce un'esperienza di test del servizio senza interruzioni quando combinato con l'host automatico del servizio WCF.  
  
 [Generazione di classi di tipi dati da XML](generating-data-type-classes-from-xml.md)  
  
 I dati XML archiviati negli Appunti possono essere incollati in una tabella codici. Le classi definite nei dati verranno convertite in tipi di codice.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Utilizzo degli strumenti senza privilegio di amministratore  
 Per consentire agli utenti senza privilegi di amministratore di sviluppare servizi WCF,http://+:8731/Design_Time_Addressesviene creato un ACL (Access Control List) per lo spazio dei nomi " " durante l'installazione di Visual Studio. L'ACL viene impostato su (UI) che include tutti gli utenti interattivi che hanno eseguito l'accesso al computer. Gli amministratori possono aggiungere o possono utenti da questo ACL oppure aprire porte aggiuntive. Questo ACL aggiuntivo consente a WCF o ai modelli WF di inviare e ricevere dati nella relativa configurazione predefinita. Consente inoltre agli utenti di utilizzare l'host automatico del servizio WCF (wcfSvcHost.exe) senza concedere loro privilegi di amministratore.  
  
 È possibile modificare l'accesso utilizzando lo strumento Netsh.exe in Windows Vista con l'account amministratore con privilegi elevati. Di seguito è riportato un esempio di utilizzo di Netsh.exe.  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Per ulteriori informazioni su Netsh.exe, vedere Utilizzo delle opzioni della riga di comando [e degli strumenti Netsh.exe](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).  
  
## <a name="see-also"></a>Vedere anche

- [Modelli di Visual Studio WCF](wcf-vs-templates.md)
- [Host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [Client di prova WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
