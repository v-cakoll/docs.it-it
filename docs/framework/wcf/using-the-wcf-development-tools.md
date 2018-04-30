---
title: Utilizzo degli strumenti di sviluppo WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7ec09b6b99b831245d11d858f90c27de05d1e21f
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="using-the-wcf-development-tools"></a>Utilizzo degli strumenti di sviluppo WCF
In questa sezione vengono descritti gli strumenti di sviluppo di Visual Studio che possono fornire assistenza nello sviluppo di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]servizio.  
  
 È possibile utilizzare i modelli di Visual Studio come base per rapidamente il proprio servizio di compilazione, quindi utilizzare [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Host automatico servizio e [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Client di Test per eseguire il debug e testare il servizio. Questi strumenti forniscono funzioni di debug e test veloci e trasparenti e precludono la necessità di eseguire il commit a un modello di hosting in fase iniziale.  
  
## <a name="the-wcf-developer-tools"></a>Strumenti dello sviluppatore WCF  
 [Modelli di Visual Studio WCF](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 È possibile utilizzare i modelli di progetto e di elemento Visual Studio predefiniti in Visual Studio per compilare rapidamente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servizi e le relative applicazioni.  
  
 [Host del servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 Il [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Host automatico servizio (WcfSvcHost.exe) consente di avviare il debugger di Visual Studio (F5) per ospitare e testare un servizio è stato implementato automaticamente. È quindi possibile testare il servizio mediante Client di test di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfTestClient.exe) o un client specifico per trovare e correggere qualsiasi errore potenziale.  
  
 [Client di prova WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 Client di test di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe) è un strumento GUI che consente di immettere parametri di tipi arbitrari, inviare tale input al servizio e visualizzare la risposta restituita dal servizio. In combinazione con Host automatico servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], offre una funzione di test del servizio trasparente.  
  
 [Generazione di classi di tipi dati da XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 I dati XML archiviati negli Appunti possono essere incollati in una tabella codici. Le classi definite nei dati verranno convertite in tipi di codice.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Utilizzo degli strumenti senza privilegio di amministratore  
 Per consentire agli utenti senza privilegio di amministratore di sviluppare [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, viene creato un ACL (Access Control List) per lo spazio dei nomi "http://+:8731/Design_Time_Addresses" durante l'installazione di Visual Studio. L'ACL viene impostato su (UI) che include tutti gli utenti interattivi che hanno eseguito l'accesso al computer. Gli amministratori possono aggiungere o possono utenti da questo ACL oppure aprire porte aggiuntive. Questo ACL aggiuntivo consente a WCF o ai modelli WF di inviare e ricevere dati nella relativa configurazione predefinita. Consente inoltre agli utenti di utilizzare Host automatico servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfSvcHost.exe) senza che vengano concessi privilegi di amministratore.  
  
 È inoltre possibile modificare l'accesso mediante lo strumento Netsh.exe disponibile in [!INCLUDE[wv](../../../includes/wv-md.md)] utilizzando l'account di amministratore con privilegi elevati. Di seguito è riportato un esempio di utilizzo di Netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Per ulteriori informazioni su Netsh.exe, vedere [come utilizzare lo strumento di Netsh.exe e opzioni della riga di comando](http://go.microsoft.com/fwlink/?LinkId=97877).  
  
## <a name="see-also"></a>Vedere anche  
 [Modelli di Visual Studio WCF](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [Host del servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [Client di prova WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
