---
title: Reliable Secure Profile
ms.date: 03/30/2017
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: dfdafbcdc461c80192e310a86d5bff50f0885283
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205947"
---
# <a name="reliable-secure-profile"></a>Reliable Secure Profile
Questo esempio viene illustrato come creare WCF e [Reliable Secure Profile](https://go.microsoft.com/fwlink/?LinkId=178140) (RSP). In questo esempio illustra l'implementazione di un [Crea connessione](https://go.microsoft.com/fwlink/?LinkId=178141) canale che può essere composti insieme a messaggi affidabili e, facoltativamente, un canale sicuro per creare un'associazione sicura affidabile basata sulla specifica RSP.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## <a name="discussion"></a>Discussione  
 In questo esempio viene descritto uno scenario di scambio di messaggi bidirezionale asincrono affidabile. Il servizio dispone di un contratto duplex e il client implementa il contratto di callback duplex. Il client avvia una richiesta a un servizio per il quale è attesa una risposta in una connessione separata. Il messaggio di richiesta viene inviato in modo affidabile. Il client non desidera aprire un endpoint di ascolto in corrispondenza del punto finale. Pertanto, esegue il polling del servizio con richieste "Crea connessione" affinché il servizio restituisca la risposta nel canale di supporto di tale richiesta "Crea connessione". In questo esempio viene descritto come disporre di una comunicazione duplex affidabile sicura su HTTP senza che il client esponga un endpoint di ascolto (e creando un'eccezione del firewall).  
  
## <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Aprire il **ReliableSecureProfile** soluzione.  
  
2.  Fare clic il **Service** del progetto **Esplora soluzioni**, selezionare **Debug**, **Avvia nuova istanza** dal menu di scelta rapida. In questo modo, viene avviato l'host del servizio.  
  
3.  Fare clic il **Client** del progetto **Esplora soluzioni**, selezionare **Debug**, **Avvia nuova istanza** dal menu di scelta rapida. In questo modo, il client viene avviato.  
  
4.  Digitare qualsiasi stringa nel messaggio di richiesta nella finestra della console client e fare clic su INVIO. In questo modo, la stringa di input viene inviata al servizio, che calcola un hash di tale stringa.  
  
5.  Visualizzare il risultato nelle finestre del client quando il servizio richiama l'operazione del contratto di callback duplex per visualizzare il risultato nella finestra della console client. Nel servizio si verifica un ritardo intenzionale per simulare il completamento di un'operazione lunga di elaborazione dei dati.  
  
6.  Il monitoraggio del traffico HTTP (da parte di strumenti per il monitoraggio della rete online quali Network Monitor, Fiddler e così via) mostra che tra il client e il servizio viene creata una sequenza per la comunicazione come stabilito da Reliable Secure Profile. Viene inoltre illustrato come il client esegue il polling del servizio con richieste "Crea connessione". Quando il servizio è pronto per restituire la richiesta elaborata, utilizza il canale di supporto dell'ultima richiesta "Crea connessione" per la restituzione dei risultati.  
  
7.  Premere INVIO nella finestra della console del servizio per chiudere il servizio. Premere INVIO nella finestra della console client per chiudere il client.
