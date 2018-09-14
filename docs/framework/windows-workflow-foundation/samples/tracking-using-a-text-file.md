---
title: Rilevamento tramite un file di testo
ms.date: 03/30/2017
ms.assetid: 56a82682-73c2-4b91-a206-4d8bb12c561b
ms.openlocfilehash: 19b4d544bc1d1c5bc9ebfa51b4ba28eb82c525d0
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45513643"
---
# <a name="tracking-using-a-text-file"></a>Rilevamento tramite un file di testo
In questo esempio viene illustrato come estendere il rilevamento in Windows Workflow Foundation (WF) creando un partecipante del rilevamento personalizzato. I partecipanti di rilevamento sono classi .NET Framework che ricevono record di rilevamento dal runtime man mano che vengono generati. È possibile creare un partecipante di rilevamento per trasportare gli eventi di rilevamento a qualunque destinazione necessaria per lo specifico scenario. Ad esempio, il partecipante di rilevamento Analisi eventi per Windows (ETW) viene fornito come parte di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Il partecipante di rilevamento in questo esempio scrive i record in formato XML in un file di testo.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Per ottimizzare l'utilità e l'affidabilità del partecipante di rilevamento, è necessario completare alcuni passaggi aggiuntivi per collegare correttamente il partecipante di rilevamento al runtime. Nella tabella seguente vengono descritte le classi usate in questo esempio per creare un partecipante di rilevamento conforme alle procedure consigliate.  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|`TextFileTrackingExtensionElement`|<xref:System.ServiceModel.Configuration.BehaviorExtensionElement> consente di definire la sezione di configurazione usata per configurare il partecipante di rilevamento del file di testo. Gli utenti possono specificare la destinazione del file di log usando file di configurazione standard di .NET Framework.|  
|`TextFileTrackingBehavior`|I comportamenti di WCF consentono agli utenti di inserire estensioni nel runtime. Tramite questo comportamento il partecipante di rilevamento viene aggiunto al servizio all'avvio di quest'ultimo.|  
|`TextFileTrackingParticipant`|Il partecipante di rilevamento riceve i partecipanti di rilevamento in fase di esecuzione e li archivia in un file di log come XML.|  
  
## <a name="behavior-extension-elements-configuration"></a>Configurazione degli elementi estensione di comportamento  
 Per poter usare l'elemento estensione di comportamento descritto in precedenza usando file di configurazione di .NET Framework, è necessario un ulteriore passaggio. La configurazione seguente deve essere inserita nei file di configurazione in cui verrà usata l'estensione.  
  
```xml  
<system.serviceModel>  
    <extensions>  
      <behaviorExtensions>  
        <add name="textFileTracking" type="Microsoft.Samples.TextFileTracking.TextFileTrackingExtensionElement, WFStockPriceApplication, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
…  
  </system.serviceModel>  
```  
  
> [!NOTE]
>  Vedere il file Web.config incluso nell'esempio per un completo esempio di utilizzo della configurazione di elementi estensione di comportamento.  
  
## <a name="custom-tracking-records"></a>Record di rilevamento personalizzati  
 Il file GetStockPrices.cs illustra come creare record di rilevamento personalizzati dall'interno di <xref:System.Activities.CodeActivity>. Quando si esegue l'esempio, cercare questo record.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione WFStockPriceApplication.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
     Viene aperta la finestra del browser in cui viene mostrata la visualizzazione directory per l'applicazione.  
  
4.  Nel browser fare clic su StockPriceService.xamlx.  
  
5.  Nel browser viene visualizzata la **StockPriceService** pagina, che contiene l'indirizzo wsdl del servizio locale. Copiare questo indirizzo.  
  
     Un esempio dell'indirizzo wsdl del servizio locale è http://localhost:53797/StockPriceService.xamlx?wsdl.  
  
6.  Da [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] passare alla cartella [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] (la cartella di installazione predefinita è %SystemDrive%\Programmi\Microsoft Visual Studio 10.0). Individuare quindi la sottocartella Common7\IDE\.  
  
7.  Fare doppio clic sul file WcfTestClient.exe per avviare il client di prova WCF.  
  
8.  Nel Client di prova WCF selezionare **aggiunta di un servizio...** dal **File** menu.  
  
9. Incollare l'URL appena copiato nella casella di testo.  
  
10. Fare clic su **OK** per chiudere la finestra di dialogo.  
  
11. Testare il servizio usando il client di prova WCF.  
  
    1.  Nel Client di prova WCF fare doppio clic **getstockprice ()** sotto il **IStockPriceService** nodo.  
  
         Il **getstockprice ()** metodo viene visualizzato nel riquadro di destra, con un solo parametro.  
  
    2.  Digitare Contoso come valore per il parametro.  
  
    3.  Fare clic su **richiamare**.  
  
12. Vedere gli eventi rilevati nel file di log presente nella directory dei dati dell'applicazione in %APPDATA%\trackingRecords.log.  
  
    > [!NOTE]
    >  % APPDATA % è una variabile di ambiente che viene risolta in %systemdrive%\users.\\< nomeutente\>\AppData\Roaming in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], o Windows Server 2008.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\TextFileTracking`  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di monitoraggio di AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
