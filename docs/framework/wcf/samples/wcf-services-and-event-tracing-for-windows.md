---
title: Servizi WCF e traccia eventi per Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: d45e83919dae52ee3719fe52463711999ba48dd3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555544"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a>Servizi WCF e traccia eventi per Windows
Questo esempio viene illustrato come utilizzare la traccia analitica in Windows Communication Foundation (WCF) per generare eventi di Event Tracing for Windows (ETW). Le tracce analitiche sono eventi generati in punti chiave nello stack di WCF che consentono la risoluzione dei problemi dei servizi WCF nell'ambiente di produzione.

 Traccia analitica nei servizi WCF è la traccia che può essere attivata in un ambiente di produzione con impatto minimo sulle prestazioni. Queste tracce vengono inviate come eventi a una sessione ETW.

 In questo esempio include un servizio WCF di base in cui vengono generati gli eventi dal servizio nel registro eventi, che può essere visualizzato tramite Visualizzatore eventi. È anche possibile avviare una sessione ETW dedicata che attende gli eventi dal servizio WCF. Nell'esempio è incluso uno script che consente di creare una sessione ETW dedicata che archivia gli eventi in un file binario che può essere letto tramite Visualizzatore eventi.

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1.  Usa Visual Studio 2012, aprire il file della soluzione Etwanalytictracesample.

2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.

3.  Per eseguire la soluzione, premere CTRL+F5.

     Nel Web browser, fare clic su **Calculator**. L'URI del documento WSDL per il servizio viene visualizzato nel browser. Copiare l'URI.

     Per impostazione predefinita, il servizio avvia l'ascolto delle richieste sulla porta 1378 `http://localhost:1378/Calculator.svc`.

4.  Eseguire il client di prova WCF (WcfTestClient.exe).

     Il client di prova WCF (WcfTestClient.exe) si trova in `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.  La directory di installazione di Visual Studio 2012 impostazione predefinita è `C:\Program Files\Microsoft Visual Studio 10.0`.

5.  All'interno del client di test WCF, aggiungere il servizio selezionando **File**e quindi **Aggiungi servizio**.

     Aggiungere l'indirizzo dell'endpoint nella casella di input. Il valore predefinito è `http://localhost:1378/Calculator.svc`.

6.  Aprire l'applicazione Visualizzatore eventi.

     Prima di richiamare il servizio, avviare Visualizzatore eventi e assicurarsi che il registro eventi sia in ascolto per rilevare eventi creati dal servizio WCF.

7.  Dal **avviare** dal menu **strumenti di amministrazione**e quindi **Visualizzatore eventi**.  Abilitare la **analitico** e **Debug** i log.

8.  Nella visualizzazione albero in Visualizzatore eventi passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi **Server applicazioni-applicazioni**. Fare doppio clic su **Server applicazioni-applicazioni**, selezionare **View**e quindi **Visualizza registri analitici e Debug**.

     Verificare che il **Visualizza registri analitici e Debug** opzione è selezionata.

9. Abilitare la **analitico** log.

     Nella visualizzazione albero in Visualizzatore eventi passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi **Server applicazioni-applicazioni**. Fare doppio clic su **analitico** e selezionare **Attiva registro**.

#### <a name="to-test-the-service"></a>Per eseguire il test del servizio

1.  Tornare al client di prova WCF e fare doppio clic su `Divide` e mantenere i valori predefiniti, che specificano un denominatore pari a 0.

     Se il valore del denominatore è 0, il servizio genererà un errore.

2.  Osservare gli eventi creati dal servizio.

     Tornare a Visualizzatore eventi e passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi **Server applicazioni-applicazioni**. Fare doppio clic su **analitico** e selezionare **aggiornare**.

     Gli eventi di traccia analitici di WCF verranno visualizzati nel Visualizzatore eventi. Si noti che poiché un errore è stato generato dal servizio, nel Visualizzatori eventi viene visualizzato un evento traccia di errore.

3.  Ripetere i passaggi 1 e 2 con valori di input validi. Il valore del parametro `N2` deve essere un numero diverso da 0.

     Aggiornare il canale analitico per visualizzare gli eventi WCF e osservare come non includano alcun evento di errore.

 Nell'esempio vengono illustrati gli eventi di traccia analitici creati da un servizio WCF.

#### <a name="to-cleanup-optional"></a>Per eseguire la pulizia (facoltativo)

1.  Aprire Visualizzatore eventi.

2.  Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi  **Server applicazioni-applicazioni**. Fare doppio clic su **analitico** e selezionare **Disattiva registro**.

3.  Passare a **Visualizzatore eventi**, **registri applicazioni e servizi**, **Microsoft**, **Windows**e quindi  **Server applicazioni-applicazioni**. Fare doppio clic su **analitico** e selezionare **Cancella Log**.

4.  Scegliere il **cancellare** opzione per cancellare gli eventi.

> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a>Vedere anche
- [Esempi di monitoraggio di AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
