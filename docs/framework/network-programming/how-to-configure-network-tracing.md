---
title: 'Procedura: Configurare la traccia di rete'
ms.date: 03/30/2017
helpviewer_keywords:
- formatting [.NET Framework], network tracing
- network tracing, configuring
- level attribute
- app.config files, network tracing
- configuration files [.NET Framework], network tracing
- protocol-level trace output
- application configuration files, network tracing
- sockets, trace output
ms.assetid: 5ef9fe4b-8d3d-490e-9259-1d014b2181af
ms.openlocfilehash: 06132509860b16d1e22cfdf7e3226c968d16b7cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73040651"
---
# <a name="how-to-configure-network-tracing"></a>Procedura: configurare la traccia di reteHow to: Configure network tracing

Nel file di configurazione del computer o dell'applicazione sono contenute le impostazioni che determinano il formato e il contenuto delle tracce di rete. Prima di eseguire questa procedura, assicurarsi che la funzionalità di traccia sia abilitata. Per ulteriori informazioni, vedere [Abilitare l'analisi di rete](enabling-network-tracing.md).

Il file di configurazione del computer, *machine.config*, è memorizzato nella cartella *%windir%.* È presente un file *machine.config* separato nelle cartelle in *%windir% , Microsoft.NET , Framework* per ogni versione di .NET Framework installata nel computer, ad esempio:

- *C:: WINDOWS Microsoft.NET Framework v2.0.50727 Config Machine.config*
- *C:: WINDOWS Microsoft.NET Framework64 v4.0.30319 Config machine.config*

Queste impostazioni possono essere effettuate anche nel file di configurazione dell'applicazione, che ha la precedenza sul file di configurazione del computer.

## <a name="configure-network-tracing"></a>Configurare la traccia di rete

Per configurare l'analisi di rete, aggiungere le righe seguenti al file di configurazione appropriato. I valori e le opzioni per queste impostazioni sono descritti nelle tabelle riportate di seguito.

```xml
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.Net" tracemode="includehex" maxdatasize="1024">
        <listeners>
          <add name="System.Net"/>
        </listeners>
      </source>
      <source name="System.Net.Cache">
        <listeners>
          <add name="System.Net"/>
        </listeners>
      </source>
      <source name="System.Net.Http">
        <listeners>
          <add name="System.Net"/>
        </listeners>
      </source>
      <source name="System.Net.Sockets">
        <listeners>
          <add name="System.Net"/>
        </listeners>
      </source>
      <source name="System.Net.WebSockets">
        <listeners>
          <add name="System.Net"/>
        </listeners>
      </source>
   </sources>
    <switches>
      <add name="System.Net" value="Verbose"/>
      <add name="System.Net.Cache" value="Verbose"/>
      <add name="System.Net.Http" value="Verbose"/>
      <add name="System.Net.Sockets" value="Verbose"/>
      <add name="System.Net.WebSockets" value="Verbose"/>
    </switches>
    <sharedListeners>
      <add name="System.Net"
        type="System.Diagnostics.TextWriterTraceListener"
        initializeData="network.log"
        traceOutputOptions="ProcessId, DateTime"
      />
    </sharedListeners>
    <trace autoflush="true"/>
  </system.diagnostics>
</configuration>
```

### <a name="trace-output-from-methods"></a>Tracciare l'output dai metodi

Quando si aggiunge un nome al blocco `<switches>`, l'output di traccia include informazioni da alcuni metodi correlati al nome. Nella tabella seguente viene descritto l'output:

|Nome|Output da|
|----------|-----------------|
|`System.Net.Sockets`|Alcuni metodi pubblici <xref:System.Net.Sockets.Socket> <xref:System.Net.Sockets.TcpListener>delle <xref:System.Net.Sockets.TcpClient>classi <xref:System.Net.Dns> , , e .|
|`System.Net`|Alcuni metodi pubblici <xref:System.Net.HttpWebRequest> <xref:System.Net.HttpWebResponse>delle <xref:System.Net.FtpWebRequest>classi <xref:System.Net.FtpWebResponse> , , e e le informazioni di debug SSL (certificati non validi, elenco delle autorità di certificazione mancanti ed errori relativi ai certificati client).|
|`System.Net.HttpListener`|Alcuni metodi pubblici delle classi <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> e <xref:System.Net.HttpListenerResponse>.|
|`System.Net.Cache`|Alcuni metodi interni e privati in `System.Net.Cache`.|
|`System.Net.Http`|Alcuni metodi pubblici delle classi <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> e <xref:System.Net.Http.WebRequestHandler>.|
|`System.Net.WebSockets.WebSocket`|Alcuni metodi pubblici delle classi <xref:System.Net.WebSockets.ClientWebSocket> e <xref:System.Net.WebSockets.WebSocket>.|

### <a name="trace-output-attributes"></a>Attributi di output di traccia

Gli attributi elencati nella tabella seguente configurano l'output di traccia:

|Nome attributo|Valore di attributo|
|--------------------|---------------------|
|`value`|Attributo <xref:System.String> obbligatorio. Imposta il livello di dettaglio dell'output. I valori consentiti sono `Critical`, `Error`, `Verbose`, `Warning` e `Information`.<br /><br />Questo attributo deve essere impostato sull'elemento **add** dell'elemento **switches.** Se questo attributo è impostato sull'elemento **di origine,** viene generata un'eccezione.<br/><br/>Esempio: `<add name="System.Net" value="Verbose"/>`|
|`maxdatasize`|Attributo <xref:System.Int32> facoltativo. Imposta il numero massimo di byte di dati di rete inclusi in ogni traccia di riga. Il valore predefinito è 1024.<br /><br />Questo attributo deve essere impostato sull'elemento **di origine.** Se questo attributo è impostato su un elemento sotto l'elemento **switches,** viene generata un'eccezione.<br/><br/>Esempio: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`|
|`tracemode`|Attributo <xref:System.String> facoltativo. Impostare su `includehex` per visualizzare le tracce del protocollo nel formato esadecimale e di testo. Impostare su `protocolonly` per mostrare solo testo. Il valore predefinito è `includehex`.<br /><br />Questo attributo deve essere impostato sull'elemento **di origine.** Se questo attributo è impostato su un elemento sotto l'elemento **switches,** viene generata un'eccezione.<br/><br/>Esempio: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`|

## <a name="see-also"></a>Vedere anche

- [Interpretazione della traccia di rete](interpreting-network-tracing.md)
- [Traccia di rete in .NET Framework](network-tracing.md)
- [Abilitazione della traccia di rete](enabling-network-tracing.md)
- [Traccia e strumentazione di applicazioni](../debug-trace-profile/tracing-and-instrumenting-applications.md)
