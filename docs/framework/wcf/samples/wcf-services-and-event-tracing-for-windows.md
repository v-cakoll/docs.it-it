---
title: Servizi WCF e traccia eventi per Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: 5bf965ad6a9997ec0603325f246679cf42662a52
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094813"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a>Servizi WCF e traccia eventi per Windows
In questo esempio viene illustrato come utilizzare la traccia analitica in Windows Communication Foundation (WCF) per generare eventi in Event Tracing for Windows (ETW). Le tracce analitiche sono eventi generati in punti chiave dello stack WCF che consentono la risoluzione dei problemi relativi ai servizi WCF nell'ambiente di produzione.

 Traccia analitica nei servizi WCF è la traccia che può essere attivata in un ambiente di produzione con un impatto minimo sulle prestazioni. Queste tracce vengono inviate come eventi a una sessione ETW.

 Questo esempio include un servizio WCF di base in cui gli eventi vengono generati dal servizio nel registro eventi, che possono essere visualizzati utilizzando Visualizzatore eventi. È inoltre possibile avviare una sessione ETW dedicata che rimane in ascolto degli eventi del servizio WCF. Nell'esempio è incluso uno script che consente di creare una sessione ETW dedicata che archivia gli eventi in un file binario che può essere letto tramite Visualizzatore eventi.

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Con Visual Studio 2012 aprire il file della soluzione EtwAnalyticTraceSample. sln.

2. Per compilare la soluzione, premere CTRL+MAIUSC+B.

3. Per eseguire la soluzione, premere CTRL+F5.

     Nella Web browser fare clic su **Calculator. svc**. L'URI del documento WSDL per il servizio viene visualizzato nel browser. Copiare l'URI.

     Per impostazione predefinita, il servizio inizia l'ascolto delle richieste sulla porta 1378 `http://localhost:1378/Calculator.svc`.

4. Eseguire il client di prova WCF (WcfTestClient. exe).

     Il client di prova WCF (WcfTestClient. exe) si trova in `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.  La directory di installazione predefinita di Visual Studio 2012 è `C:\Program Files\Microsoft Visual Studio 10.0`.

5. Nel client di prova WCF aggiungere il servizio selezionando **file**e quindi **Aggiungi servizio**.

     Aggiungere l'indirizzo dell'endpoint nella casella di input. Il valore predefinito è `http://localhost:1378/Calculator.svc`.

6. Aprire l'applicazione Visualizzatore eventi.

     Prima di richiamare il servizio, avviare Visualizzatore eventi e verificare che il registro eventi sia in ascolto di eventi di rilevamento generati dal servizio WCF.

7. Dal menu **Start** , selezionare **strumenti di amministrazione**, quindi **Visualizzatore eventi**.  Abilitare i log **analitici** e di **debug** .

8. Nella visualizzazione albero di Visualizzatore eventi passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, quindi **server applicazioni-applicazioni**. Fare clic con il pulsante destro del mouse su **server applicazioni-applicazioni**, selezionare **Visualizza**, quindi **Visualizza registri analitici e di debug**.

     Verificare che l'opzione **Mostra log analitici e di debug** sia selezionata.

9. Abilitare il registro **analitico** .

     Nella visualizzazione albero di Visualizzatore eventi passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, quindi **server applicazioni-applicazioni**. Fare clic con il pulsante destro del mouse su **analitico** e selezionare **Abilita log**.

#### <a name="to-test-the-service"></a>Per eseguire il test del servizio

1. Tornare al client di prova WCF, fare doppio clic su `Divide` e mantengono i valori predefiniti, che specificano un denominatore pari a 0.

     Se il valore del denominatore è 0, il servizio genererà un errore.

2. Osservare gli eventi creati dal servizio.

     Tornare a Visualizzatore eventi e passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, quindi Server applicazioni **-applicazioni**. Fare clic con il pulsante destro del mouse su **Analytics** e selezionare **Aggiorna**.

     Gli eventi di traccia analitici di WCF verranno visualizzati nel Visualizzatore eventi. Si noti che poiché un errore è stato generato dal servizio, nel Visualizzatori eventi viene visualizzato un evento traccia di errore.

3. Ripetere i passaggi 1 e 2 con valori di input validi. Il valore del parametro `N2` deve essere un numero diverso da 0.

     Aggiornare il canale analitico per visualizzare gli eventi WCF e osservare come non includano alcun evento di errore.

 Nell'esempio vengono illustrati gli eventi di traccia analitici creati da un servizio WCF.

#### <a name="to-cleanup-optional"></a>Per eseguire la pulizia (facoltativo)

1. Aprire Visualizzatore eventi.

2. Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, quindi **Application-Server-** Applications. Fare clic con il pulsante destro del mouse su **analitico** e selezionare **Disattiva log**.

3. Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**, quindi **Application-Server-** Applications. Fare clic con il pulsante destro del mouse su **analitico** e selezionare **Cancella log**.

4. Scegliere l'opzione **Cancella** per cancellare gli eventi.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di monitoraggio di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
