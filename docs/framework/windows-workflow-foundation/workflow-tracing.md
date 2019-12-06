---
title: Traccia del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: 972520aae7a2af950ed1ba079769861173784148
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837506"
---
# <a name="workflow-tracing"></a>Traccia del flusso di lavoro
La traccia del flusso di lavoro consente di acquisire informazioni diagnostiche usando i listener di traccia di .NET Framework. La traccia può essere abilitata in seguito al rilevamento di un problema con l'applicazione, quindi nuovamente disabilitata quando il problema viene risolto. Sono disponibili due modi per abilitare la traccia di debug per i flussi di lavoro: è possibile configurarla usando il visualizzatore di Traccia eventi oppure usare l'oggetto <xref:System.Diagnostics> per inviare eventi di traccia a un file.  
  
## <a name="enabling-debug-tracing-in-etw"></a>Abilitazione della traccia di debug in ETW  
 Per abilitare la traccia tramite ETW, abilitare il canale Debug in Visualizzatore eventi:  
  
1. Passare al nodo dei registri analitici e di debug in Visualizzatore eventi.  
  
2. Nella visualizzazione struttura ad albero di Visualizzatore eventi passare a **Visualizzatore eventi-> registri applicazioni e servizi-> Microsoft-> Windows-> server applicazioni-applicazioni**. Fare clic con il pulsante destro del mouse su **server applicazioni-applicazioni** e selezionare visualizza **-> Visualizza log analitici e di debug**. Fare clic con il pulsante destro del mouse su **debug** e selezionare **Abilita log**.  
  
3. Quando un flusso di lavoro esegue il debug e le tracce vengono create nel canale di debug ETW, queste ultime possono essere visualizzate in Visualizzatore eventi. Passare a **Visualizzatore eventi-> registri applicazioni e servizi-> Microsoft-> Windows-> server applicazioni-applicazioni**. Fare clic con il pulsante destro del mouse su **debug** e selezionare **Aggiorna**.  
  
4. La dimensione del buffer di traccia analitica predefinita è solo 4 kilobyte (KB). Si consiglia di aumentare la dimensione a 32 KB. A tale scopo, eseguire i passaggi seguenti.  
  
    1. Eseguire il comando seguente nella directory del framework corrente (ad esempio, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`  
  
    2. Modificare il valore di \<bufferSize > nel file Windows. ApplicationServer. Applications. Man in 32.  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3. Eseguire il comando seguente nella directory del framework corrente (ad esempio, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`  
  
> [!NOTE]
> Se si usa il .NET Framework 4 Client Profile, è necessario prima registrare il manifesto ETW eseguendo il comando seguente dalla directory .NET Framework 4: `ServiceModelReg.exe –i –c:etw`  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a>Abilitazione della traccia di debug tramite l'oggetto System.Diagnostics  
 Questi listener possono essere configurati nel file App.config dell'applicazione flusso di lavoro o nel file Web.config per un servizio flusso di lavoro. In questo esempio, una <xref:System.Diagnostics.TextWriterTraceListener> è configurata in modo da salvare le informazioni di traccia nel file nel MyTraceLog. txt nella directory corrente.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Monitoraggio di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [Monitoraggio delle applicazioni con l'infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
