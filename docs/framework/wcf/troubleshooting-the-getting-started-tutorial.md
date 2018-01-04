---
title: Risoluzione dei problemi relativi all'esercitazione introduttiva
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 55288074b35bcb00d6c6b453f1320ad40d26a5f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-the-getting-started-tutorial"></a>Risoluzione dei problemi relativi all'esercitazione introduttiva
In questo argomento vengono elencati i problemi più comuni che possono verificarsi durante l'Esercitazione introduttiva e le relative soluzioni.  
  
1.  [Non riesco a trovare i file di progetto sul disco rigido.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q1)  
  
2.  [Se si tenta di eseguire l'applicazione del servizio, viene visualizzato l'errore seguente: HTTP non è stato in grado di registrare l'URL http://+:8000/ServiceModelSamples/Service/. Il processo non dispone dei diritti di accesso a questo spazio dei nomi.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q2)  
  
3.  [Il tentativo di utilizzare lo strumento Svcutil.exe: 'svcutil' non è riconosciuto come comando interno o esterno, programma eseguibile o file batch.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q3)  
  
4.  [Impossibile trovare il file app. config generato da Svcutil.exe.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q4)  
  
5.  [La compilazione dell'applicazione client: 'CalculatorClient' non contiene una definizione per '&lt;nome del metodo&gt;'e alcun metodo di estensione'&lt;nome del metodo&gt;' che accetta un primo argomento di tipo 'CalculatorClient' è stato possibile trovare (probabilmente manca un utilizzo della direttiva o un riferimento all'assembly?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q5)  
  
6.  [La compilazione dell'applicazione client: il nome di tipo o spazio dei nomi 'CalculatorClient' non è stato trovato (probabilmente manca un utilizzo della direttiva o un riferimento all'assembly?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q6)  
  
7.  [Esegue il client: eccezione non gestita: EndpointNotFoundException: Impossibile connettersi al http://localhost:8000/servicemodelsamples/Service/ServiceModelSamples/Service/CalculatorService. Codice di errore TCP 10061: Impossibile stabilire la connessione rifiuto persistente del computer di destinazione.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q7)  
  
<a name="BKMK_q1"></a>   
## <a name="i-am-unable-to-find-the-project-files-on-my-hard-drive"></a>Impossibile trovare i file di progetto nell'unità disco rigido.  
 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]Salva file di progetto in c:\users\\< utente name\Documents\\< versione di Visual Studio\>\Projects in [!INCLUDE[wv](../../../includes/wv-md.md)] e [!INCLUDE[win7_client_secondref](../../../includes/win7-client-secondref-md.md)]e c:\Documents and Settings\\< nome utente\>Documenti \My\\< versione di Visual Studio\>\Projects nelle versioni precedenti di Windows.  
  
<a name="BKMK_q2"></a>   
## <a name="attempting-to-run-the-service-application-http-could-not-register-url-http8000servicemodelsamplesservice-your-process-does-not-have-access-rights-to-this-namespace"></a>Se si tenta di eseguire l'applicazione del servizio, viene visualizzato l'errore seguente: HTTP non è stato in grado di registrare l'URL http://+:8000/ServiceModelSamples/Service/. Il processo non dispone dei diritti di accesso a questo spazio dei nomi.  
 Il processo che ospita un servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] deve essere eseguito con privilegi di amministratore. Se il servizio viene eseguito da [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], è necessario eseguire [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] come amministratore. Per fare **avviare**, fare doppio clic su [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] e selezionare **Esegui come amministratore**. Se il servizio viene eseguito da un prompt della riga di comando, è necessario avviare il prompt della riga di comando come amministratore. Fare clic su **avviare**, fare doppio clic su **prompt dei comandi** e selezionare **Esegui come amministratore**.  
  
<a name="BKMK_q3"></a>   
## <a name="attempting-to-use-the-svcutilexe-tool-svcutil-is-not-recognized-as-an-internal-or-external-command-operable-program-or-batch-file"></a>Se si tenta di utilizzare lo strumento Svcutil.exe, viene visualizzato l'errore seguente: 'svcutil' non è riconosciuto come comando interno o esterno, un programma eseguibile o un file batch.  
 Svcutil.exe deve trovarsi nel percorso di sistema. La soluzione più semplice consiste nell'utilizzare il prompt dei comandi. Fare clic su **avviare**selezionare **tutti i programmi**, [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], **Visual Studio Tools**, e [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] **prompt dei comandi**. Questo prompt dei comandi consente di impostare il percorso di sistema sui percorsi corretti per tutti gli strumenti forniti con [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
<a name="BKMK_q4"></a>   
## <a name="unable-to-find-the-appconfig-file-generated-by-svcutilexe"></a>Impossibile trovare il file App.config generato da Svcutil.exe.  
 Il **Aggiungi elemento esistente** finestra di dialogo vengono visualizzati solo i file con le seguenti estensioni per impostazione predefinita:. cs, resx, Settings, XSD e WSDL. È possibile specificare che si desidera visualizzare tutti i tipi di file selezionando **tutti i file (\*.\*)**  nella casella di riepilogo nell'angolo inferiore destro di a discesa di **Aggiungi elemento esistente** la finestra di dialogo.  
  
<a name="BKMK_q5"></a>   
## <a name="compiling-the-client-application-calculatorclient-does-not-contain-a-definition-for-method-name-and-no-extension-method-method-name-accepting-a-first-argument-of-type-calculatorclient-could-be-found-are-you-missing-a-using-directive-or-an-assembly-reference"></a>La compilazione dell'applicazione client: 'CalculatorClient' non contiene una definizione per '\<nome metodo >' e alcun metodo di estensione '\<nome metodo >' che accetta un primo argomento di tipo 'CalculatorClient' è stato possibile trovare (probabilmente manca un utilizzo della direttiva o un riferimento all'assembly?)  
 Solo i metodi contrassegnati con `ServiceOperationAttribute` vengono esposti al mondo esterno. Se è stato omesso l'attributo `ServiceOperationAttribute` da uno dei metodi nell'interfaccia `ICalculator`, durante la compilazione di un'applicazione client che effettua una chiamata all'operazione a cui manca l'attributo viene visualizzato questo messaggio di errore.  
  
<a name="BKMK_q6"></a>   
## <a name="compiling-the-client-application-the-type-or-namespace-name-calculatorclient-could-not-be-found-are-you-missing-a-using-directive-or-an-assembly-reference"></a>Durante la compilazione dell'applicazione client, viene visualizzato l'errore seguente: Impossibile trovare il tipo o il nome dello spazio dei nomi 'CalculatorClient'; probabilmente manca una direttiva using o un riferimento a un assembly.  
 Questo errore si verifica se il file Proxy.cs o Proxy.vb non viene aggiunto al progetto client.  
  
<a name="BKMK_q7"></a>   
## <a name="running-the-client-unhandled-exception-systemservicemodelendpointnotfoundexception-could-not-connect-to-httplocalhost8000servicemodelsamplesservicecalculatorservice-tcp-error-code-10061-no-connection-could-be-made-because-the-target-machine-actively-refused-it"></a>Eseguendo il client, viene visualizzato l'errore seguente: Eccezione non gestita: System.ServiceModel.EndpointNotFoundException: Impossibile connettersi a http://localhost:8000/ServiceModelSamples/Service/CalculatorService. Codice di errore TCP 10061: Impossibile stabilire la connessione. Rifiuto persistente del computer di destinazione.  
 Si verifica questo errore se l'applicazione client viene eseguita senza eseguire il servizio.  
  
<a name="BKMK_q8"></a>   
## <a name="unhandled-exception-systemservicemodelsecuritysecuritynegotiationexception-soap-security-negotiation-with-httplocalhost8000servicemodelsamplesservicecalculatorservice-for-target-httplocalhost8000servicemodelsamplesservicecalculatorservice-failed"></a>Eccezione non gestita: System.ServiceModel.Security.SecurityNegotiationException: Negoziazione di sicurezza SOAP con 'http://localhost:8000/ServiceModelSamples/Service/CalculatorService' per la destinazione 'http://localhost:8000/ServiceModelSamples/Service/CalculatorService' non riuscita  
 Questo errore si verifica in un computer aggiunto a un dominio senza connettività di rete. Connettere il computer alla rete o disattivare la sicurezza sia per il client che per il servizio. Per quest'ultimo, modificare inoltre il codice che crea WSHttpBinding nel modo seguente.  
  
```  
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
```  
  
 Per il client, modificare il  **\<sicurezza >** elemento sotto il  **\<associazione >** il seguente:  
  
```xml  
<security mode="Node" />  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Guida rapida alla risoluzione dei problemi di WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)  
 [Risoluzione dei problemi di installazione](../../../docs/framework/wcf/troubleshooting-setup-issues.md)
