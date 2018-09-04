---
title: Risoluzione dei problemi relativi all'esercitazione introduttiva
ms.date: 03/30/2017
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 43128743ba16aefc8669ace85070a16d80145a71
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519421"
---
# <a name="troubleshooting-the-getting-started-tutorial"></a>Risoluzione dei problemi relativi all'esercitazione introduttiva
In questo argomento vengono elencati i problemi più comuni che possono verificarsi durante l'Esercitazione introduttiva e le relative soluzioni.  
  
**Non riesco a trovare i file di progetto sul disco rigido.**

 Visual Studio salva i file di progetto in c:\users\\<user name>\Documents\\< versione di Visual Studio\>\Projects.  
  
**Provare a eseguire l'applicazione di servizio: HTTP non è stato possibile registrare l'URL `http://+:8000/ServiceModelSamples/Service/`.** 
 **Il processo non dispone dei diritti di accesso per questo spazio dei nomi.** 

 Il processo che ospita un servizio WCF deve eseguire con privilegi amministrativi. Se si esegue il servizio da Visual Studio, è necessario eseguire Visual Studio come amministratore. Per eseguire questa operazione, selezionare **avviare**, fare doppio clic su **Visual Studio \< *versione* >**  selezionare **Esegui come amministratore**. Se si esegue il servizio da un prompt della riga di comando nella finestra della console, è necessario avviare la finestra della console con privilegi di amministratore in modo analogo. Fare clic su **avviare**, fare doppio clic su **prompt dei comandi** e selezionare **Esegui come amministratore**.  
  
**Tentativo di utilizzare lo strumento Svcutil.exe: 'svcutil' non è riconosciuto come comando interno o esterno, programma eseguibile o file batch.**

 Svcutil.exe deve trovarsi nel percorso di sistema. La soluzione più semplice consiste nell'utilizzare il prompt dei comandi. Fare clic su **avviare**, selezionare **tutti i programmi**, **Visual Studio \< *versione*>**,  **Strumenti di Visual Studio**, e **prompt dei comandi per gli sviluppatori per Visual Studio**. Questo prompt dei comandi imposta il percorso di sistema per i percorsi corretti per tutti gli strumenti forniti come parte di Visual Studio.  

**Impossibile trovare il file app. config generato da Svcutil.exe.**

 Il **Aggiungi elemento esistente** finestra di dialogo Visualizza solo i file con le estensioni seguenti per impostazione predefinita: cs, resx, Settings, XSD,. WSDL. È possibile specificare che si desidera vedere tutti i tipi di file selezionando **tutti i file (\*.\*)**  nella casella di riepilogo discesa nell'angolo inferiore destro del **Aggiungi elemento esistente** nella finestra di dialogo.  


**La compilazione dell'applicazione client: 'CalculatorClient' non contiene una definizione per '\<nome metodo >' e alcun metodo di estensione '\<nome metodo >' che accetta un primo argomento di tipo 'CalculatorClient' è stato possibile trovare (sei manca un utilizzo della direttiva o un riferimento all'assembly?)**  

Solo i metodi contrassegnati con `ServiceOperationAttribute` vengono esposti al mondo esterno. Se omette il `ServiceOperationAttribute` attributo da uno dei metodi nel `ICalculator` interfaccia, viene visualizzato questo messaggio di errore durante la compilazione di un'applicazione client che effettua una chiamata all'operazione di attributo mancante.  

**La compilazione dell'applicazione client: il nome di tipo o spazio dei nomi 'CalculatorClient' non è stato trovato (probabilmente manca un utilizzo della direttiva o un riferimento all'assembly?)**

 Questo errore si verifica se il file Proxy.cs o Proxy.vb non viene aggiunto al progetto client.  

**Esegue il client: eccezione non gestita: EndpointNotFoundException: Impossibile connettersi al `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`. Codice di errore TCP 10061: non è stato possibile connettersi perché rifiuto persistente del computer di destinazione.**

Si verifica questo errore se l'applicazione client viene eseguita senza eseguire il servizio.  
  
**Eccezione non gestita: SecurityNegotiationException: negoziazione di sicurezza SOAP con `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` per la destinazione `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` non è riuscita**  

Questo errore si verifica in un computer aggiunto a un dominio senza connettività di rete. Connettere il computer alla rete o disattivare la sicurezza sia per il client che per il servizio. Per quest'ultimo, modificare inoltre il codice che crea WSHttpBinding nel modo seguente.  
  
```csharp
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
```

Per il client, modificare il  **\<sicurezza >** elemento sotto il  **\<associazione >** elemento al seguente:  
  
```xml
<security mode="Node" />  
```  

## <a name="see-also"></a>Vedere anche  
 [Esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Guida rapida alla risoluzione dei problemi di WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)  
 [Risoluzione dei problemi di installazione](../../../docs/framework/wcf/troubleshooting-setup-issues.md)
