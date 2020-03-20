---
title: Servizi WCF e traccia eventi per Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: b8a1f30f20aa2c541a574a070b3644569d633ca2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183205"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a>Servizi WCF e traccia eventi per Windows
In questo esempio viene illustrato come utilizzare la traccia analitica in Windows Communication Foundation (WCF) per generare eventi in Event Tracing for Windows (ETW). Le tracce analitiche sono eventi generati in punti chiave nello stack WCF che consentono la risoluzione dei problemi dei servizi WCF nell'ambiente di produzione.

 La traccia analitica nei servizi WCF è la traccia che può essere attivata in un ambiente di produzione con un impatto minimo sulle prestazioni. Queste tracce vengono inviate come eventi a una sessione ETW.

 Questo esempio include un servizio WCF di base in cui gli eventi vengono generati dal servizio al registro eventi, che può essere visualizzato tramite il Visualizzatore eventi. È anche possibile avviare una sessione ETW dedicata in ascolto di eventi dal servizio WCF. Nell'esempio è incluso uno script che consente di creare una sessione ETW dedicata che archivia gli eventi in un file binario che può essere letto tramite Visualizzatore eventi.

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Utilizzando Visual Studio 2012, aprire il file di soluzione EtwAnalyticTraceSample.sln.

2. Per compilare la soluzione, premere CTRL+MAIUSC+B.

3. Per eseguire la soluzione, premere CTRL+F5.

     Nel browser Web fare clic su **Calculator.svc**. L'URI del documento WSDL per il servizio viene visualizzato nel browser. Copiare l'URI.

     Per impostazione predefinita, il servizio avvia l'ascolto delle richieste sulla porta 1378 `http://localhost:1378/Calculator.svc`.

4. Eseguire il client di test WCF (WcfTestClient.exe).

     Il client di test WCF (WcfTestClient.exe) si trova in `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.  Il dir di installazione di Visual `C:\Program Files\Microsoft Visual Studio 10.0`Studio 2012 predefinito è .

5. All'interno del client di test WCF aggiungere il servizio selezionando **File**, quindi **Aggiungi servizio**.

     Aggiungere l'indirizzo dell'endpoint nella casella di input. Il valore predefinito è `http://localhost:1378/Calculator.svc`.

6. Aprire l'applicazione Visualizzatore eventi.

     Prima di richiamare il servizio, avviare il Visualizzatore eventi e assicurarsi che il registro eventi sia in ascolto per tenere traccia degli eventi generati dal servizio WCF.

7. Dal menu **Start** selezionare **Strumenti di amministrazione**, quindi **Visualizzatore eventi**.  Abilitare i registri **analitici** e **di debug.**

8. Nella visualizzazione struttura nel Visualizzatore eventi passare a **Visualizzatore eventi**, **Registri applicazioni e servizi**, **Microsoft**, **Windows**e infine Applicazioni **server applicazioni**. Fare clic con il pulsante destro del mouse su **Applicazioni server applicazioni**, scegliere **Visualizza**, quindi Mostra **registri analitici e**di debug .

     Verificare che l'opzione **Mostra registri analitici e** di debug sia selezionata.

9. Abilitare il registro **analitico.**

     Nella visualizzazione struttura nel Visualizzatore eventi passare a **Visualizzatore eventi**, **Registri applicazioni e servizi**, **Microsoft**, **Windows**e infine Applicazioni **server applicazioni**. Fare clic con il pulsante destro del mouse su **Analitica** e selezionare **Abilita registro**.

#### <a name="to-test-the-service"></a>Per eseguire il test del servizio

1. Tornare al client di test `Divide` WCF e fare doppio clic e mantenere i valori predefiniti, che specificano un denominatore pari a 0.

     Se il valore del denominatore è 0, il servizio genererà un errore.

2. Osservare gli eventi creati dal servizio.

     Tornare al Visualizzatore eventi e passare a **Visualizzatore eventi**, **Registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi Applicazioni **server applicazioni**. Fare clic con il pulsante destro del mouse su **Analitica** e scegliere **Aggiorna**.

     Gli eventi di traccia analitici di WCF verranno visualizzati nel Visualizzatore eventi. Si noti che poiché un errore è stato generato dal servizio, nel Visualizzatori eventi viene visualizzato un evento traccia di errore.

3. Ripetere i passaggi 1 e 2 con valori di input validi. Il valore del parametro `N2` deve essere un numero diverso da 0.

     Aggiornare il canale analitico per visualizzare gli eventi WCF e osservare come non includano alcun evento di errore.

 Nell'esempio vengono illustrati gli eventi di traccia analitici creati da un servizio WCF.

#### <a name="to-cleanup-optional"></a>Per eseguire la pulizia (facoltativo)

1. Aprire Visualizzatore eventi.

2. Passare a **Visualizzatore eventi**, **Registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi **Applicazioni-Server-applicazioni**. Fare clic con il pulsante destro del mouse su **Analisi** e selezionare **Disattiva registro**.

3. Passare a **Visualizzatore eventi**, **Registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi **Applicazioni-Server-applicazioni**. Fare clic con il pulsante destro del mouse su **Analitica** e selezionare **Cancella registro**.

4. Scegliere l'opzione **Cancella** per cancellare gli eventi.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a>Vedere anche

- [Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
