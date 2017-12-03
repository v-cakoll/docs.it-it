---
title: Utilizzo degli strumenti di sviluppo WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9532363adafd492ca35e10e6d20c788ddf5b1d17
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-wcf-development-tools"></a>Utilizzo degli strumenti di sviluppo WCF
Contenuto della sezione vengono descritti gli strumenti di sviluppo [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)][!INCLUDE[indigo1](../../../includes/indigo1-md.md)] che possono fornire assistenza nello sviluppo del servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 È possibile utilizzare i modelli di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] come base per compilare rapidamente un servizio specifico, quindi utilizzare Host automatico servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e Client di test di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] per eseguire il debug e testare il servizio. Questi strumenti forniscono funzioni di debug e test veloci e trasparenti e precludono la necessità di eseguire il commit a un modello di hosting in fase iniziale.  
  
## <a name="the-wcf-developer-tools"></a>Strumenti dello sviluppatore WCF  
 [Modelli di Visual Studio WCF](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 È possibile utilizzare il progetto [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] predefinito e i modelli di elemento disponibili in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] per compilare rapidamente i servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e le relative applicazioni.  
  
 [Host del servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 Host automatico servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfSvcHost.exe) consente di avviare il debugger (F5) di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] per attivare automaticamente funzioni di host e test di un servizio implementato. È quindi possibile testare il servizio mediante Client di test di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfTestClient.exe) o un client specifico per trovare e correggere qualsiasi errore potenziale.  
  
 [Client di prova WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 Client di test di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe) è un strumento GUI che consente di immettere parametri di tipi arbitrari, inviare tale input al servizio e visualizzare la risposta restituita dal servizio. In combinazione con Host automatico servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], offre una funzione di test del servizio trasparente.  
  
 [Generazione di classi di tipi dati da XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 I dati XML archiviati negli Appunti possono essere incollati in una tabella codici. Le classi definite nei dati verranno convertite in tipi di codice.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Utilizzo degli strumenti senza privilegio di amministratore  
 Per consentire agli utenti senza privilegio di amministratore di sviluppare servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], viene creato un ACL (Elenco di controllo di accesso) per lo spazio dei nomi "http://+:8731/Design_Time_Addresses" durante l'installazione di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]. L'ACL viene impostato su (UI) che include tutti gli utenti interattivi che hanno eseguito l'accesso al computer. Gli amministratori possono aggiungere o possono utenti da questo ACL oppure aprire porte aggiuntive. Questo ACL aggiuntivo consente a WCF o ai modelli WF di inviare e ricevere dati nella relativa configurazione predefinita. Consente inoltre agli utenti di utilizzare Host automatico servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfSvcHost.exe) senza che vengano concessi privilegi di amministratore.  
  
 È inoltre possibile modificare l'accesso mediante lo strumento Netsh.exe disponibile in [!INCLUDE[wv](../../../includes/wv-md.md)] utilizzando l'account di amministratore con privilegi elevati. Di seguito è riportato un esempio di utilizzo di Netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]Netsh.exe, vedere [sull'utilizzo dello strumento Netsh.exe e parametri della riga di comando](http://go.microsoft.com/fwlink/?LinkId=97877).  
  
## <a name="see-also"></a>Vedere anche  
 [Modelli di Visual Studio WCF](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [Host del servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [Client di prova WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
