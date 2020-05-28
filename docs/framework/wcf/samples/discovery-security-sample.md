---
title: Esempio di sicurezza di individuazione
ms.date: 03/30/2017
ms.assetid: b8db01f4-b4a1-43fe-8e31-26d4e9304a65
ms.openlocfilehash: c6ec9b7e13234b7dae03541eb09ccba98f4cc93a
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144903"
---
# <a name="discovery-security-sample"></a>Esempio di sicurezza di individuazione

La specifica Discovery non richiede che gli endpoint che partecipano al processo di individuazione siano sicuri. Il potenziamento dei messaggi di individuazione tramite la sicurezza riduce tuttavia la possibilità di vari tipi di attacchi (modifica del messaggio, Denial of Service, replay, spoofing). In questo esempio vengono implementati canali personalizzati che calcolano e verificano le firme dei messaggi usando il formato di firma compatto (descritto nella Sezione 8.2 della specifica WS-Discovery). L'esempio supporta sia la [specifica di individuazione 2005](http://specs.xmlsoap.org/ws/2005/04/discovery/ws-discovery.pdf) che la [versione 1,1](http://docs.oasis-open.org/ws-dd/discovery/1.1/cs-01/wsdd-discovery-1.1-spec-cs-01.pdf).  
  
 Il canale personalizzato viene applicato sullo stack di canali esistente per gli endpoint di individuazione e degli annunci. In questo modo, per ogni messaggio inviato viene applicata un'intestazione di firma. La firma viene verificata nei messaggi ricevuti e quando non corrisponde oppure quando i messaggi non presentano una firma, i messaggi vengono eliminati. Nell'esempio per firmare e verificare i messaggi vengono usati i certificati.  
  
## <a name="discussion"></a>Discussione  
 WCF è estendibile e consente agli utenti di personalizzare i canali nel modo desiderato. Nell'esempio viene implementato un elemento di associazione protetta dell'individuazione che consente la compilazione di canali sicuri. I canali sicuri verificano le firme dei messaggi e vengono applicati sullo stack corrente.  
  
 L'elemento di associazione protetta compila le channel factory e i listener di canale sicuri.  
  
## <a name="secure-channel-factory"></a>Channel factory protetta  
 La channel factory protetta crea output o canali duplex che aggiungono una firma compatta alle intestazioni dei messaggi. Per contenere il più possibile le dimensioni dei messaggi, viene usato il formato della firma compatto. La struttura di una firma compatta viene illustrata nell'esempio seguente.  
  
```xml  
<d:Security ... >
  [<d:Sig Scheme="xs:anyURI"
         [KeyId="xs:base64Binary"]?  
          Refs="..."  
         [PrefixList]="xs:NMTOKENS"
          Sig="xs:base64Binary"
          ... />]?  
  ...
</d:Security>  
```  
  
> [!NOTE]
> Alla versione 2008 del protocollo Discovery è stato aggiunto `PrefixList`.  
  
 Per calcolare la firma, nell'esempio vengono determinati gli elementi della firma espansi. Viene creata una firma XML (`SignedInfo`) usando il prefisso dello spazio dei nomi `ds`, come richiesto dalla specifica WS-Discovery. Al corpo e a tutte le intestazioni presenti negli spazi dei nomi di individuazione e indirizzamento viene fatto riferimento nella firma, impedendone pertanto l'alterazione. Ogni elemento a cui viene fatto riferimento viene trasformato usando la canonizzazione esclusiva ( <http://www.w3.org/2001/10/xml-exc-c14n#> ) e quindi viene calcolato un valore digest SHA-1 ( <http://www.w3.org/2000/09/xmldsig#sha1> ). In base a tutti gli elementi a cui viene fatto riferimento e ai relativi valori di digest, il valore della firma viene calcolato usando l'algoritmo RSA ( <http://www.w3.org/2000/09/xmldsig#rsa-sha1> ).  
  
 I messaggi vengono firmati con un certificato specificato dal client. Il percorso dell'archivio, il nome e il nome del soggetto del certificato devono essere specificati quando viene creato l'elemento di associazione. `KeyId` nella firma compressa rappresenta l'identificatore di chiave del token di firma e corrisponde all'identificatore di chiave del soggetto (SKI, Subject Key Identifier) del token di firma oppure (se l'identificatore SKI non esiste) a un hash SHA-1 della chiave pubblica del token di firma.  
  
## <a name="secure-channel-listener"></a>Listener del canale protetto  
 Il listener del canale protetto crea l'input o i canali duplex che verificano la firma compatta nei messaggi ricevuti. Per verificare la firma, l'elemento `KeyId` specificato nella firma compatta allegata al messaggio viene usato per selezionare un certificato nell'archivio specificato. Se il messaggio non presenta una firma o il controllo della firma ha esito negativo, i messaggi vengono eliminati. Per usare l'associazione protetta, nell'esempio viene definita una factory che crea gli oggetti <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> e <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> personalizzati a cui è stato aggiunto l'elemento di individuazione dell'associazione protetta. Questi endpoint sicuri possono essere usati nei listener degli annunci di individuazione e nei servizi individuabili.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 In questo esempio sono incluse un'applicazione di libreria e 4 applicazioni console:
  
- **DiscoverySecurityChannels**: raccolta che espone l'associazione protetta. La libreria calcola e verifica la firma compatta per i messaggi in uscita/in arrivo.  
  
- **Servizio**: un servizio che espone il contratto ICalculatorService, self hosted. Il servizio è contrassegnato come individuabile. L'utente specifica i dettagli del certificato usato per firmare i messaggi specificando il percorso e il nome dell'archivio e il nome del soggetto o di un altro identificatore univoco per il certificato, nonché l'archivio in cui si trovano i certificati client (i certificati usati per il controllo della firma dei messaggi in arrivo). In base a questi dettagli, viene compilato e usato un oggetto UdpDiscoveryEndpoint con sicurezza aggiunta.  
  
- **Client**: questa classe tenta di individuare un ICalculatorService e di chiamare i metodi nel servizio. Un <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> con sicurezza aggiunta viene di nuovo compilato e usato per firmare e verificare i messaggi.  
  
- **AnnouncementListener**: un servizio indipendente che rimane in ascolto degli annunci online e offline e usa l'endpoint di annuncio protetto.  
  
> [!NOTE]
> Se Setup.bat viene eseguito più volte, il gestore di certificati richiederà di scegliere un certificato da aggiungere, in quanto esistono certificati duplicati. In tal caso, Setup.bat dovrà essere interrotto e sarà necessario chiamare Cleanup.bat, poiché i duplicati sono già stati creati. Cleanup.bat richiederà inoltre di scegliere un certificato da eliminare. Selezionare un certificato nell'elenco e continuare a eseguire Cleanup.bat fino a quando non rimarrà alcun certificato.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1. Eseguire lo script Setup. bat da un Prompt dei comandi per gli sviluppatori per Visual Studio. Nell'esempio vengono usati certificati per firmare e verificare i messaggi. Lo script crea i certificati usando Makecert.exe, quindi li installa usando Certmgr.exe. Lo script deve essere eseguito con i privilegi di amministratore.  
  
2. Per compilare ed eseguire l'esempio, aprire il file Security. sln in Visual Studio e scegliere **Ricompila tutto**. Aggiornare le proprietà della soluzione per avviare più progetti: selezionare **Avvia** per tutti i progetti ad eccezione di DiscoverySecureChannels. Eseguire la soluzione in modo normale.  
  
3. Dopo aver completato l'esempio, eseguire lo script Cleanup.bat per rimuovere i certificati creati per questo esempio.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DiscoveryScenario`  
