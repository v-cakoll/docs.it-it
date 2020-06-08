---
title: 'Procedura: Configurare la traccia di rete'
description: Informazioni su come configurare la traccia di rete nel file di configurazione del computer o nel file di configurazione dell'applicazione. Un file di configurazione dell'applicazione ha la precedenza.
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
ms.openlocfilehash: b089746e9838c591ed5ccc9ac9aaeedb217de9a9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502561"
---
# <a name="how-to-configure-network-tracing"></a>Procedura: configurare la traccia di rete

Nel file di configurazione del computer o dell'applicazione sono contenute le impostazioni che determinano il formato e il contenuto delle tracce di rete. Prima di eseguire questa procedura, assicurarsi che la funzionalità di traccia sia abilitata. Per altre informazioni, vedere [abilitare la traccia di rete](enabling-network-tracing.md).

Il file di configurazione del computer, *Machine. config*, viene archiviato nella cartella *%windir%\Microsoft.NET\Framework* Nelle cartelle in *%windir%\Microsoft.NET\Framework* è presente un file *Machine. config* separato per ogni versione del .NET Framework installato nel computer, ad esempio:

- *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*
- *C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*

Queste impostazioni possono essere effettuate anche nel file di configurazione dell'applicazione, che ha la precedenza sul file di configurazione del computer.

## <a name="configure-network-tracing"></a>Configurare la traccia di rete

Per configurare la traccia di rete, aggiungere le righe seguenti al file di configurazione appropriato. I valori e le opzioni per queste impostazioni sono descritti nelle tabelle riportate di seguito.

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

### <a name="trace-output-from-methods"></a>Tracciare l'output dei metodi

Quando si aggiunge un nome al blocco `<switches>`, l'output di traccia include informazioni da alcuni metodi correlati al nome. La tabella seguente descrive l'output:

|Nome|Output da|
|----------|-----------------|
|`System.Net.Sockets`|Alcuni metodi pubblici delle <xref:System.Net.Sockets.Socket> classi, <xref:System.Net.Sockets.TcpListener> , <xref:System.Net.Sockets.TcpClient> e <xref:System.Net.Dns> .|
|`System.Net`|Alcuni metodi pubblici delle <xref:System.Net.HttpWebRequest> classi, <xref:System.Net.HttpWebResponse> , <xref:System.Net.FtpWebRequest> e e <xref:System.Net.FtpWebResponse> le informazioni di debug SSL (certificati non validi, elenco di autorità emittenti mancanti ed errori del certificato client).|
|`System.Net.HttpListener`|Alcuni metodi pubblici delle classi <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> e <xref:System.Net.HttpListenerResponse>.|
|`System.Net.Cache`|Alcuni metodi interni e privati in `System.Net.Cache`.|
|`System.Net.Http`|Alcuni metodi pubblici delle classi <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> e <xref:System.Net.Http.WebRequestHandler>.|
|`System.Net.WebSockets.WebSocket`|Alcuni metodi pubblici delle classi <xref:System.Net.WebSockets.ClientWebSocket> e <xref:System.Net.WebSockets.WebSocket>.|

### <a name="trace-output-attributes"></a>Attributi di output di traccia

Gli attributi elencati nella tabella seguente configurano l'output di traccia:

|Nome attributo|Valore di attributo|
|--------------------|---------------------|
|`value`|Attributo <xref:System.String> obbligatorio. Imposta il livello di dettaglio dell'output. I valori consentiti sono `Critical`, `Error`, `Verbose`, `Warning` e `Information`.<br /><br />Questo attributo deve essere impostato sull'elemento **Add** dell'elemento **Switches** . Viene generata un'eccezione se l'attributo è impostato sull'elemento di **origine** .<br/><br/>Esempio: `<add name="System.Net" value="Verbose"/>`|
|`maxdatasize`|Attributo <xref:System.Int32> facoltativo. Imposta il numero massimo di byte di dati di rete inclusi in ogni traccia di riga. Il valore predefinito è 1024.<br /><br />Questo attributo deve essere impostato sull'elemento di **origine** . Viene generata un'eccezione se questo attributo è impostato su un elemento sotto l'elemento **Switches** .<br/><br/>Esempio: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`|
|`tracemode`|Attributo <xref:System.String> facoltativo. Impostare su `includehex` per visualizzare le tracce del protocollo nel formato esadecimale e di testo. Impostare su `protocolonly` per mostrare solo testo. Il valore predefinito è `includehex`.<br /><br />Questo attributo deve essere impostato sull'elemento di **origine** . Viene generata un'eccezione se questo attributo è impostato su un elemento sotto l'elemento **Switches** .<br/><br/>Esempio: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`|

## <a name="see-also"></a>Vedere anche

- [Interpretazione della traccia di rete](interpreting-network-tracing.md)
- [Traccia di rete in .NET Framework](network-tracing.md)
- [Abilitazione della traccia di rete](enabling-network-tracing.md)
- [Traccia e strumentazione di applicazioni](../debug-trace-profile/tracing-and-instrumenting-applications.md)
