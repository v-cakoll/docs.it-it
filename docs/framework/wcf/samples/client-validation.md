---
title: Convalida client
ms.date: 03/30/2017
ms.assetid: f0c1f805-1a81-4d0d-a112-bf5e2e87a631
ms.openlocfilehash: 6e34ca8e1bb14f610e363c02eaeb94b7fa5e27c7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
ms.locfileid: "33808286"
---
# <a name="client-validation"></a>Convalida client
I servizi pubblicano spesso metadati per consentire la generazione e configurazione automatica di tipi di proxy client. Quando il servizio non è considerato attendibile, le applicazioni client devono convalidare che i metadati siano conformi ai criteri dell'applicazione client riguardanti la sicurezza, le transazioni, il tipo di contratto di servizio e così via. Nell'esempio seguente viene dimostrato come scrivere un comportamento dell'endpoint client che convalida l'endpoint del servizio per garantire che quest'ultimo possa essere usato senza rischi.  
  
 Il servizio espone quattro endpoint del servizio. Il primo endpoint usa WSDualHttpBinding, il secondo usa l'autenticazione NTLM, il terzo abilita il flusso delle transazioni e il quarto usa l'autenticazione basata sui certificati.  
  
 Il client usa la classe <xref:System.ServiceModel.Description.MetadataResolver> per recuperare i metadati per il servizio. Il client applica i criteri di proibizione delle associazioni duplex, autenticazione NTLM e flusso delle transazioni usando un comportamento di convalida. Per ogni <xref:System.ServiceModel.Description.ServiceEndpoint> istanza importata dai metadati del servizio, l'applicazione client aggiunge un'istanza del `InternetClientValidatorBehavior` comportamento dell'endpoint per il <xref:System.ServiceModel.Description.ServiceEndpoint> prima di provare a utilizzare un client Windows Communication Foundation (WCF) per connettersi a l'endpoint. Il metodo `Validate` del comportamento viene eseguito prima che venga chiamata qualsiasi operazione nel servizio e applica i criteri del client generando `InvalidOperationExceptions`.  
  
### <a name="to-build-the-sample"></a>Per compilare l'esempio  
  
1.  Per compilare la soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>Per eseguire l'esempio nello stesso computer  
  
1.  Aprire un prompt dei comandi di Visual Studio con privilegi di amministratore ed eseguire Setup.bat dalla cartella di installazione dell'esempio. In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.  
  
2.  Eseguire l'applicazione di servizio da \service\bin\Debug.  
  
3.  Eseguire l'applicazione client da \client\bin\Debug. L'attività del client viene visualizzata nella finestra dell'applicazione console.  
  
4.  Se il client e il servizio non sono in grado di comunicare, vedere [suggerimenti per la risoluzione dei problemi](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
5.  Rimuovere i certificati eseguendo Cleanup.bat una volta completato l'esempio. Negli altri esempi relativi alla sicurezza vengono usati gli stessi certificati.  
  
### <a name="to-run-the-sample-across-computers"></a>Per eseguire l'esempio tra più computer  
  
1.  Nel server, in un prompt dei comandi di Visual Studio con privilegi di amministratore, digitare `setup.bat service`. Esecuzione `setup.bat` con il `service` argomento crea un certificato di servizio con il nome di dominio completo del computer e il certificato di servizio viene esportato in un file denominato Service.cer.  
  
2.  Modificare App.config sul server per riflettere il nome del nuovo certificato, Ossia, modifica il `findValue` attributo il [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) elemento sul nome di dominio completo del computer.  
  
3.  Copiare il file Service.cer dalla directory del servizio nella directory del client sul computer relativo.  
  
4.  Nel client, aprire un prompt dei comandi di Visual Studio con privilegi di amministratore e digitare `setup.bat client`. Esecuzione `setup.bat` con il `client` argomento crea un certificato client denominato Client.com ed Esporta il certificato client in un file denominato Client.cer.  
  
5.  Nel file client.cs modificare il valore dell'indirizzo dell'endpoint MEX e il `findValue` per impostare il certificato del server predefinito in modo che corrisponda al nuovo indirizzo del servizio. Tale operazione viene eseguita sostituendo localhost con il nome di dominio completo del server. Ricompilare il file.  
  
6.  Copiare il file Client.cer dalla directory del client nella directory del servizio sul server.  
  
7.  Sul client aprire un prompt dei comandi di Visual Studio con privilegi di amministratore ed eseguire ImportServiceCert.bat. In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.  
  
8.  Sul server aprire un prompt dei comandi di Visual Studio con privilegi di amministratore ed eseguire ImportClientCert.bat. In questo modo viene importato il certificato del client dal file Client.cer nell'archivio LocalMachine - TrustedPeople.  
  
9. Nel computer del servizio compilare il progetto di servizio in Visual Studio ed eseguire service.exe.  
  
10. Nel computer client eseguire client.exe.  
  
    1.  Se il client e il servizio non sono in grado di comunicare, vedere [suggerimenti per la risoluzione dei problemi](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### <a name="to-clean-up-after-the-sample"></a>Per eseguire la pulizia dopo l'esempio  
  
-   Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.  
  
    > [!NOTE]
    >  Questo script non rimuove i certificati del servizio da un client quando si esegue l'esempio tra più computer. Se sono stati eseguiti esempi WCF che usano certificati tra più computer, verificare di cancellare i certificati del servizio che sono stati installati in CurrentUser - TrustedPeople archiviare. A tale scopo, utilizzare il comando seguente: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>. For example: certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di metadati](../../../../docs/framework/wcf/feature-details/using-metadata.md)
