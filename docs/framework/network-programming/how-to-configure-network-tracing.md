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
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="c06a7-104">Procedura: configurare la traccia di rete</span><span class="sxs-lookup"><span data-stu-id="c06a7-104">How to: Configure network tracing</span></span>

<span data-ttu-id="c06a7-105">Nel file di configurazione del computer o dell'applicazione sono contenute le impostazioni che determinano il formato e il contenuto delle tracce di rete.</span><span class="sxs-lookup"><span data-stu-id="c06a7-105">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="c06a7-106">Prima di eseguire questa procedura, assicurarsi che la funzionalità di traccia sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="c06a7-106">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="c06a7-107">Per altre informazioni, vedere [abilitare la traccia di rete](enabling-network-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="c06a7-107">For more information, see [Enable network tracing](enabling-network-tracing.md).</span></span>

<span data-ttu-id="c06a7-108">Il file di configurazione del computer, *Machine. config*, viene archiviato nella cartella *%windir%\Microsoft.NET\Framework*</span><span class="sxs-lookup"><span data-stu-id="c06a7-108">The computer configuration file, *machine.config*, is stored in the *%windir%\Microsoft.NET\Framework* folder.</span></span> <span data-ttu-id="c06a7-109">Nelle cartelle in *%windir%\Microsoft.NET\Framework* è presente un file *Machine. config* separato per ogni versione del .NET Framework installato nel computer, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c06a7-109">There is a separate *machine.config* file in the folders under *%windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer, for example:</span></span>

- <span data-ttu-id="c06a7-110">*C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*</span><span class="sxs-lookup"><span data-stu-id="c06a7-110">*C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*</span></span>
- <span data-ttu-id="c06a7-111">*C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*</span><span class="sxs-lookup"><span data-stu-id="c06a7-111">*C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*</span></span>

<span data-ttu-id="c06a7-112">Queste impostazioni possono essere effettuate anche nel file di configurazione dell'applicazione, che ha la precedenza sul file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="c06a7-112">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>

## <a name="configure-network-tracing"></a><span data-ttu-id="c06a7-113">Configurare la traccia di rete</span><span class="sxs-lookup"><span data-stu-id="c06a7-113">Configure network tracing</span></span>

<span data-ttu-id="c06a7-114">Per configurare la traccia di rete, aggiungere le righe seguenti al file di configurazione appropriato.</span><span class="sxs-lookup"><span data-stu-id="c06a7-114">To configure network tracing, add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="c06a7-115">I valori e le opzioni per queste impostazioni sono descritti nelle tabelle riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="c06a7-115">The values and options for these settings are described in the tables below.</span></span>

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

### <a name="trace-output-from-methods"></a><span data-ttu-id="c06a7-116">Tracciare l'output dei metodi</span><span class="sxs-lookup"><span data-stu-id="c06a7-116">Trace output from methods</span></span>

<span data-ttu-id="c06a7-117">Quando si aggiunge un nome al blocco `<switches>`, l'output di traccia include informazioni da alcuni metodi correlati al nome.</span><span class="sxs-lookup"><span data-stu-id="c06a7-117">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="c06a7-118">La tabella seguente descrive l'output:</span><span class="sxs-lookup"><span data-stu-id="c06a7-118">The following table describes the output:</span></span>

|<span data-ttu-id="c06a7-119">Nome</span><span class="sxs-lookup"><span data-stu-id="c06a7-119">Name</span></span>|<span data-ttu-id="c06a7-120">Output da</span><span class="sxs-lookup"><span data-stu-id="c06a7-120">Output from</span></span>|
|----------|-----------------|
|`System.Net.Sockets`|<span data-ttu-id="c06a7-121">Alcuni metodi pubblici delle <xref:System.Net.Sockets.Socket> classi, <xref:System.Net.Sockets.TcpListener> , <xref:System.Net.Sockets.TcpClient> e <xref:System.Net.Dns> .</span><span class="sxs-lookup"><span data-stu-id="c06a7-121">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes.</span></span>|
|`System.Net`|<span data-ttu-id="c06a7-122">Alcuni metodi pubblici delle <xref:System.Net.HttpWebRequest> classi, <xref:System.Net.HttpWebResponse> , <xref:System.Net.FtpWebRequest> e e <xref:System.Net.FtpWebResponse> le informazioni di debug SSL (certificati non validi, elenco di autorità emittenti mancanti ed errori del certificato client).</span><span class="sxs-lookup"><span data-stu-id="c06a7-122">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors).</span></span>|
|`System.Net.HttpListener`|<span data-ttu-id="c06a7-123">Alcuni metodi pubblici delle classi <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> e <xref:System.Net.HttpListenerResponse>.</span><span class="sxs-lookup"><span data-stu-id="c06a7-123">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|
|`System.Net.Cache`|<span data-ttu-id="c06a7-124">Alcuni metodi interni e privati in `System.Net.Cache`.</span><span class="sxs-lookup"><span data-stu-id="c06a7-124">Some private and internal methods in `System.Net.Cache`.</span></span>|
|`System.Net.Http`|<span data-ttu-id="c06a7-125">Alcuni metodi pubblici delle classi <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> e <xref:System.Net.Http.WebRequestHandler>.</span><span class="sxs-lookup"><span data-stu-id="c06a7-125">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="c06a7-126">Alcuni metodi pubblici delle classi <xref:System.Net.WebSockets.ClientWebSocket> e <xref:System.Net.WebSockets.WebSocket>.</span><span class="sxs-lookup"><span data-stu-id="c06a7-126">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|

### <a name="trace-output-attributes"></a><span data-ttu-id="c06a7-127">Attributi di output di traccia</span><span class="sxs-lookup"><span data-stu-id="c06a7-127">Trace output attributes</span></span>

<span data-ttu-id="c06a7-128">Gli attributi elencati nella tabella seguente configurano l'output di traccia:</span><span class="sxs-lookup"><span data-stu-id="c06a7-128">The attributes listed in the following table configure trace output:</span></span>

|<span data-ttu-id="c06a7-129">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="c06a7-129">Attribute name</span></span>|<span data-ttu-id="c06a7-130">Valore di attributo</span><span class="sxs-lookup"><span data-stu-id="c06a7-130">Attribute value</span></span>|
|--------------------|---------------------|
|`value`|<span data-ttu-id="c06a7-131">Attributo <xref:System.String> obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c06a7-131">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="c06a7-132">Imposta il livello di dettaglio dell'output.</span><span class="sxs-lookup"><span data-stu-id="c06a7-132">Sets the verbosity of the output.</span></span> <span data-ttu-id="c06a7-133">I valori consentiti sono `Critical`, `Error`, `Verbose`, `Warning` e `Information`.</span><span class="sxs-lookup"><span data-stu-id="c06a7-133">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /><span data-ttu-id="c06a7-134">Questo attributo deve essere impostato sull'elemento **Add** dell'elemento **Switches** .</span><span class="sxs-lookup"><span data-stu-id="c06a7-134">This attribute must be set on the **add** element of the **switches** element.</span></span> <span data-ttu-id="c06a7-135">Viene generata un'eccezione se l'attributo è impostato sull'elemento di **origine** .</span><span class="sxs-lookup"><span data-stu-id="c06a7-135">An exception is thrown if this attribute is set on the **source** element.</span></span><br/><br/><span data-ttu-id="c06a7-136">Esempio: `<add name="System.Net" value="Verbose"/>`</span><span class="sxs-lookup"><span data-stu-id="c06a7-136">Example: `<add name="System.Net" value="Verbose"/>`</span></span>|
|`maxdatasize`|<span data-ttu-id="c06a7-137">Attributo <xref:System.Int32> facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c06a7-137">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="c06a7-138">Imposta il numero massimo di byte di dati di rete inclusi in ogni traccia di riga.</span><span class="sxs-lookup"><span data-stu-id="c06a7-138">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="c06a7-139">Il valore predefinito è 1024.</span><span class="sxs-lookup"><span data-stu-id="c06a7-139">The default value is 1024.</span></span><br /><br /><span data-ttu-id="c06a7-140">Questo attributo deve essere impostato sull'elemento di **origine** .</span><span class="sxs-lookup"><span data-stu-id="c06a7-140">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="c06a7-141">Viene generata un'eccezione se questo attributo è impostato su un elemento sotto l'elemento **Switches** .</span><span class="sxs-lookup"><span data-stu-id="c06a7-141">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="c06a7-142">Esempio: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="c06a7-142">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|
|`tracemode`|<span data-ttu-id="c06a7-143">Attributo <xref:System.String> facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c06a7-143">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="c06a7-144">Impostare su `includehex` per visualizzare le tracce del protocollo nel formato esadecimale e di testo.</span><span class="sxs-lookup"><span data-stu-id="c06a7-144">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="c06a7-145">Impostare su `protocolonly` per mostrare solo testo.</span><span class="sxs-lookup"><span data-stu-id="c06a7-145">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="c06a7-146">Il valore predefinito è `includehex`.</span><span class="sxs-lookup"><span data-stu-id="c06a7-146">The default value is `includehex`.</span></span><br /><br /><span data-ttu-id="c06a7-147">Questo attributo deve essere impostato sull'elemento di **origine** .</span><span class="sxs-lookup"><span data-stu-id="c06a7-147">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="c06a7-148">Viene generata un'eccezione se questo attributo è impostato su un elemento sotto l'elemento **Switches** .</span><span class="sxs-lookup"><span data-stu-id="c06a7-148">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="c06a7-149">Esempio: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="c06a7-149">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|

## <a name="see-also"></a><span data-ttu-id="c06a7-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c06a7-150">See also</span></span>

- [<span data-ttu-id="c06a7-151">Interpretazione della traccia di rete</span><span class="sxs-lookup"><span data-stu-id="c06a7-151">Interpreting Network Tracing</span></span>](interpreting-network-tracing.md)
- [<span data-ttu-id="c06a7-152">Traccia di rete in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c06a7-152">Network Tracing in the .NET Framework</span></span>](network-tracing.md)
- [<span data-ttu-id="c06a7-153">Abilitazione della traccia di rete</span><span class="sxs-lookup"><span data-stu-id="c06a7-153">Enabling Network Tracing</span></span>](enabling-network-tracing.md)
- [<span data-ttu-id="c06a7-154">Traccia e strumentazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="c06a7-154">Tracing and Instrumenting Applications</span></span>](../debug-trace-profile/tracing-and-instrumenting-applications.md)
