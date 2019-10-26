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
ms.openlocfilehash: 98854fa0dff8d4cfb1d67d5864751ab01a21150b
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920305"
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="ae8d2-102">Procedura: configurare la traccia di rete</span><span class="sxs-lookup"><span data-stu-id="ae8d2-102">How to: Configure network tracing</span></span>

<span data-ttu-id="ae8d2-103">Nel file di configurazione del computer o dell'applicazione sono contenute le impostazioni che determinano il formato e il contenuto delle tracce di rete.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="ae8d2-104">Prima di eseguire questa procedura, assicurarsi che la funzionalità di traccia sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="ae8d2-105">Per altre informazioni, vedere [abilitare la traccia di rete](enabling-network-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="ae8d2-105">For more information, see [Enable network tracing](enabling-network-tracing.md).</span></span>

<span data-ttu-id="ae8d2-106">Il file di configurazione del computer, Machine. config, viene archiviato nella cartella%windir%\Microsoft.NET\Framework</span><span class="sxs-lookup"><span data-stu-id="ae8d2-106">The computer configuration file, machine.config, is stored in the %windir%\Microsoft.NET\Framework folder.</span></span> <span data-ttu-id="ae8d2-107">Nelle cartelle in%windir%\Microsoft.NET\Framework è presente un file Machine. config separato per ogni versione del .NET Framework installato nel computer, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ae8d2-107">There is a separate machine.config file in the folders under %windir%\Microsoft.NET\Framework for each version of the .NET Framework installed on the computer, for example:</span></span>

- <span data-ttu-id="ae8d2-108">C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config</span><span class="sxs-lookup"><span data-stu-id="ae8d2-108">C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config</span></span>
- <span data-ttu-id="ae8d2-109">C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config</span><span class="sxs-lookup"><span data-stu-id="ae8d2-109">C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config</span></span>
  
<span data-ttu-id="ae8d2-110">Queste impostazioni possono essere effettuate anche nel file di configurazione dell'applicazione, che ha la precedenza sul file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-110">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
## <a name="configure-network-tracing"></a><span data-ttu-id="ae8d2-111">Configurare la traccia di rete</span><span class="sxs-lookup"><span data-stu-id="ae8d2-111">Configure network tracing</span></span>  
  
<span data-ttu-id="ae8d2-112">Per configurare la traccia di rete, aggiungere le righe seguenti al file di configurazione appropriato.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-112">To configure network tracing, add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="ae8d2-113">I valori e le opzioni per queste impostazioni sono descritti nelle tabelle riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-113">The values and options for these settings are described in the tables below.</span></span>  
  
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

### <a name="trace-output-from-methods"></a><span data-ttu-id="ae8d2-114">Tracciare l'output dei metodi</span><span class="sxs-lookup"><span data-stu-id="ae8d2-114">Trace output from methods</span></span>

<span data-ttu-id="ae8d2-115">Quando si aggiunge un nome al blocco `<switches>`, l'output di traccia include informazioni da alcuni metodi correlati al nome.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-115">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="ae8d2-116">La tabella seguente descrive l'output:</span><span class="sxs-lookup"><span data-stu-id="ae8d2-116">The following table describes the output:</span></span>
  
|<span data-ttu-id="ae8d2-117">Name</span><span class="sxs-lookup"><span data-stu-id="ae8d2-117">Name</span></span>|<span data-ttu-id="ae8d2-118">Output da</span><span class="sxs-lookup"><span data-stu-id="ae8d2-118">Output from</span></span>|  
|----------|-----------------|  
|`System.Net.Sockets`|<span data-ttu-id="ae8d2-119">Alcuni metodi pubblici delle classi <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>e <xref:System.Net.Dns>.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-119">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes.</span></span>|  
|`System.Net`|<span data-ttu-id="ae8d2-120">Alcuni metodi pubblici delle classi <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>e <xref:System.Net.FtpWebResponse> e le informazioni di debug SSL (certificati non validi, elenco di autorità emittenti mancanti ed errori del certificato client).</span><span class="sxs-lookup"><span data-stu-id="ae8d2-120">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors).</span></span>|  
|`System.Net.HttpListener`|<span data-ttu-id="ae8d2-121">Alcuni metodi pubblici delle classi <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> e <xref:System.Net.HttpListenerResponse>.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-121">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|  
|`System.Net.Cache`|<span data-ttu-id="ae8d2-122">Alcuni metodi interni e privati in `System.Net.Cache`.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-122">Some private and internal methods in `System.Net.Cache`.</span></span>|  
|`System.Net.Http`|<span data-ttu-id="ae8d2-123">Alcuni metodi pubblici delle classi <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> e <xref:System.Net.Http.WebRequestHandler>.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-123">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|  
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="ae8d2-124">Alcuni metodi pubblici delle classi <xref:System.Net.WebSockets.ClientWebSocket> e <xref:System.Net.WebSockets.WebSocket>.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-124">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|  

### <a name="trace-output-attributes"></a><span data-ttu-id="ae8d2-125">Attributi di output di traccia</span><span class="sxs-lookup"><span data-stu-id="ae8d2-125">Trace output attributes</span></span>

<span data-ttu-id="ae8d2-126">Gli attributi elencati nella tabella seguente configurano l'output di traccia:</span><span class="sxs-lookup"><span data-stu-id="ae8d2-126">The attributes listed in the following table configure trace output:</span></span>
  
|<span data-ttu-id="ae8d2-127">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="ae8d2-127">Attribute name</span></span>|<span data-ttu-id="ae8d2-128">Valore attributo</span><span class="sxs-lookup"><span data-stu-id="ae8d2-128">Attribute value</span></span>|  
|--------------------|---------------------|  
|`value`|<span data-ttu-id="ae8d2-129">Attributo <xref:System.String> obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-129">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="ae8d2-130">Imposta il livello di dettaglio dell'output.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-130">Sets the verbosity of the output.</span></span> <span data-ttu-id="ae8d2-131">I valori consentiti sono `Critical`, `Error`, `Verbose`, `Warning` e `Information`.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-131">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /><span data-ttu-id="ae8d2-132">Questo attributo deve essere impostato sull'elemento **Add** dell'elemento **Switches** .</span><span class="sxs-lookup"><span data-stu-id="ae8d2-132">This attribute must be set on the **add** element of the **switches** element.</span></span> <span data-ttu-id="ae8d2-133">Viene generata un'eccezione se l'attributo è impostato sull'elemento di **origine** .</span><span class="sxs-lookup"><span data-stu-id="ae8d2-133">An exception is thrown if this attribute is set on the **source** element.</span></span><br/><br/><span data-ttu-id="ae8d2-134">Esempio: `<add name="System.Net" value="Verbose"/>`</span><span class="sxs-lookup"><span data-stu-id="ae8d2-134">Example: `<add name="System.Net" value="Verbose"/>`</span></span>|
|`maxdatasize`|<span data-ttu-id="ae8d2-135">Attributo <xref:System.Int32> facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-135">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="ae8d2-136">Imposta il numero massimo di byte di dati di rete inclusi in ogni traccia di riga.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-136">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="ae8d2-137">Il valore predefinito è 1024.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-137">The default value is 1024.</span></span><br /><br /><span data-ttu-id="ae8d2-138">Questo attributo deve essere impostato sull'elemento di **origine** .</span><span class="sxs-lookup"><span data-stu-id="ae8d2-138">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="ae8d2-139">Viene generata un'eccezione se questo attributo è impostato su un elemento sotto l'elemento **Switches** .</span><span class="sxs-lookup"><span data-stu-id="ae8d2-139">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="ae8d2-140">Esempio: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="ae8d2-140">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|
|`tracemode`|<span data-ttu-id="ae8d2-141">Attributo <xref:System.String> facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-141">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="ae8d2-142">Impostare su `includehex` per visualizzare le tracce del protocollo nel formato esadecimale e di testo.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-142">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="ae8d2-143">Impostare su `protocolonly` per mostrare solo testo.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-143">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="ae8d2-144">Il valore predefinito è `includehex`.</span><span class="sxs-lookup"><span data-stu-id="ae8d2-144">The default value is `includehex`.</span></span><br /><br /><span data-ttu-id="ae8d2-145">Questo attributo deve essere impostato sull'elemento di **origine** .</span><span class="sxs-lookup"><span data-stu-id="ae8d2-145">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="ae8d2-146">Viene generata un'eccezione se questo attributo è impostato su un elemento sotto l'elemento **Switches** .</span><span class="sxs-lookup"><span data-stu-id="ae8d2-146">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="ae8d2-147">Esempio: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="ae8d2-147">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="ae8d2-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae8d2-148">See also</span></span>

- [<span data-ttu-id="ae8d2-149">Interpretazione della traccia di rete</span><span class="sxs-lookup"><span data-stu-id="ae8d2-149">Interpreting Network Tracing</span></span>](interpreting-network-tracing.md)
- [<span data-ttu-id="ae8d2-150">Traccia di rete in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ae8d2-150">Network Tracing in the .NET Framework</span></span>](network-tracing.md)
- [<span data-ttu-id="ae8d2-151">Abilitazione della traccia di rete</span><span class="sxs-lookup"><span data-stu-id="ae8d2-151">Enabling Network Tracing</span></span>](enabling-network-tracing.md)
- [<span data-ttu-id="ae8d2-152">Traccia e strumentazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="ae8d2-152">Tracing and Instrumenting Applications</span></span>](../debug-trace-profile/tracing-and-instrumenting-applications.md)
