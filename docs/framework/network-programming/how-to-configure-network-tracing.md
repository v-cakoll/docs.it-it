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
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="b8884-102">Procedura: configurare la traccia di reteHow to: Configure network tracing</span><span class="sxs-lookup"><span data-stu-id="b8884-102">How to: Configure network tracing</span></span>

<span data-ttu-id="b8884-103">Nel file di configurazione del computer o dell'applicazione sono contenute le impostazioni che determinano il formato e il contenuto delle tracce di rete.</span><span class="sxs-lookup"><span data-stu-id="b8884-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="b8884-104">Prima di eseguire questa procedura, assicurarsi che la funzionalità di traccia sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="b8884-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="b8884-105">Per ulteriori informazioni, vedere [Abilitare l'analisi di rete](enabling-network-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="b8884-105">For more information, see [Enable network tracing](enabling-network-tracing.md).</span></span>

<span data-ttu-id="b8884-106">Il file di configurazione del computer, *machine.config*, è memorizzato nella cartella *%windir%.*</span><span class="sxs-lookup"><span data-stu-id="b8884-106">The computer configuration file, *machine.config*, is stored in the *%windir%\Microsoft.NET\Framework* folder.</span></span> <span data-ttu-id="b8884-107">È presente un file *machine.config* separato nelle cartelle in *%windir% , Microsoft.NET , Framework* per ogni versione di .NET Framework installata nel computer, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b8884-107">There is a separate *machine.config* file in the folders under *%windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer, for example:</span></span>

- <span data-ttu-id="b8884-108">*C:: WINDOWS Microsoft.NET Framework v2.0.50727 Config Machine.config*</span><span class="sxs-lookup"><span data-stu-id="b8884-108">*C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*</span></span>
- <span data-ttu-id="b8884-109">*C:: WINDOWS Microsoft.NET Framework64 v4.0.30319 Config machine.config*</span><span class="sxs-lookup"><span data-stu-id="b8884-109">*C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*</span></span>

<span data-ttu-id="b8884-110">Queste impostazioni possono essere effettuate anche nel file di configurazione dell'applicazione, che ha la precedenza sul file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="b8884-110">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>

## <a name="configure-network-tracing"></a><span data-ttu-id="b8884-111">Configurare la traccia di rete</span><span class="sxs-lookup"><span data-stu-id="b8884-111">Configure network tracing</span></span>

<span data-ttu-id="b8884-112">Per configurare l'analisi di rete, aggiungere le righe seguenti al file di configurazione appropriato.</span><span class="sxs-lookup"><span data-stu-id="b8884-112">To configure network tracing, add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="b8884-113">I valori e le opzioni per queste impostazioni sono descritti nelle tabelle riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="b8884-113">The values and options for these settings are described in the tables below.</span></span>

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

### <a name="trace-output-from-methods"></a><span data-ttu-id="b8884-114">Tracciare l'output dai metodi</span><span class="sxs-lookup"><span data-stu-id="b8884-114">Trace output from methods</span></span>

<span data-ttu-id="b8884-115">Quando si aggiunge un nome al blocco `<switches>`, l'output di traccia include informazioni da alcuni metodi correlati al nome.</span><span class="sxs-lookup"><span data-stu-id="b8884-115">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="b8884-116">Nella tabella seguente viene descritto l'output:</span><span class="sxs-lookup"><span data-stu-id="b8884-116">The following table describes the output:</span></span>

|<span data-ttu-id="b8884-117">Nome</span><span class="sxs-lookup"><span data-stu-id="b8884-117">Name</span></span>|<span data-ttu-id="b8884-118">Output da</span><span class="sxs-lookup"><span data-stu-id="b8884-118">Output from</span></span>|
|----------|-----------------|
|`System.Net.Sockets`|<span data-ttu-id="b8884-119">Alcuni metodi pubblici <xref:System.Net.Sockets.Socket> <xref:System.Net.Sockets.TcpListener>delle <xref:System.Net.Sockets.TcpClient>classi <xref:System.Net.Dns> , , e .</span><span class="sxs-lookup"><span data-stu-id="b8884-119">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes.</span></span>|
|`System.Net`|<span data-ttu-id="b8884-120">Alcuni metodi pubblici <xref:System.Net.HttpWebRequest> <xref:System.Net.HttpWebResponse>delle <xref:System.Net.FtpWebRequest>classi <xref:System.Net.FtpWebResponse> , , e e le informazioni di debug SSL (certificati non validi, elenco delle autorità di certificazione mancanti ed errori relativi ai certificati client).</span><span class="sxs-lookup"><span data-stu-id="b8884-120">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors).</span></span>|
|`System.Net.HttpListener`|<span data-ttu-id="b8884-121">Alcuni metodi pubblici delle classi <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> e <xref:System.Net.HttpListenerResponse>.</span><span class="sxs-lookup"><span data-stu-id="b8884-121">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|
|`System.Net.Cache`|<span data-ttu-id="b8884-122">Alcuni metodi interni e privati in `System.Net.Cache`.</span><span class="sxs-lookup"><span data-stu-id="b8884-122">Some private and internal methods in `System.Net.Cache`.</span></span>|
|`System.Net.Http`|<span data-ttu-id="b8884-123">Alcuni metodi pubblici delle classi <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> e <xref:System.Net.Http.WebRequestHandler>.</span><span class="sxs-lookup"><span data-stu-id="b8884-123">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="b8884-124">Alcuni metodi pubblici delle classi <xref:System.Net.WebSockets.ClientWebSocket> e <xref:System.Net.WebSockets.WebSocket>.</span><span class="sxs-lookup"><span data-stu-id="b8884-124">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|

### <a name="trace-output-attributes"></a><span data-ttu-id="b8884-125">Attributi di output di traccia</span><span class="sxs-lookup"><span data-stu-id="b8884-125">Trace output attributes</span></span>

<span data-ttu-id="b8884-126">Gli attributi elencati nella tabella seguente configurano l'output di traccia:</span><span class="sxs-lookup"><span data-stu-id="b8884-126">The attributes listed in the following table configure trace output:</span></span>

|<span data-ttu-id="b8884-127">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="b8884-127">Attribute name</span></span>|<span data-ttu-id="b8884-128">Valore di attributo</span><span class="sxs-lookup"><span data-stu-id="b8884-128">Attribute value</span></span>|
|--------------------|---------------------|
|`value`|<span data-ttu-id="b8884-129">Attributo <xref:System.String> obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8884-129">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="b8884-130">Imposta il livello di dettaglio dell'output.</span><span class="sxs-lookup"><span data-stu-id="b8884-130">Sets the verbosity of the output.</span></span> <span data-ttu-id="b8884-131">I valori consentiti sono `Critical`, `Error`, `Verbose`, `Warning` e `Information`.</span><span class="sxs-lookup"><span data-stu-id="b8884-131">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /><span data-ttu-id="b8884-132">Questo attributo deve essere impostato sull'elemento **add** dell'elemento **switches.**</span><span class="sxs-lookup"><span data-stu-id="b8884-132">This attribute must be set on the **add** element of the **switches** element.</span></span> <span data-ttu-id="b8884-133">Se questo attributo è impostato sull'elemento **di origine,** viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b8884-133">An exception is thrown if this attribute is set on the **source** element.</span></span><br/><br/><span data-ttu-id="b8884-134">Esempio: `<add name="System.Net" value="Verbose"/>`</span><span class="sxs-lookup"><span data-stu-id="b8884-134">Example: `<add name="System.Net" value="Verbose"/>`</span></span>|
|`maxdatasize`|<span data-ttu-id="b8884-135">Attributo <xref:System.Int32> facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b8884-135">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="b8884-136">Imposta il numero massimo di byte di dati di rete inclusi in ogni traccia di riga.</span><span class="sxs-lookup"><span data-stu-id="b8884-136">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="b8884-137">Il valore predefinito è 1024.</span><span class="sxs-lookup"><span data-stu-id="b8884-137">The default value is 1024.</span></span><br /><br /><span data-ttu-id="b8884-138">Questo attributo deve essere impostato sull'elemento **di origine.**</span><span class="sxs-lookup"><span data-stu-id="b8884-138">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="b8884-139">Se questo attributo è impostato su un elemento sotto l'elemento **switches,** viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b8884-139">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="b8884-140">Esempio: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="b8884-140">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|
|`tracemode`|<span data-ttu-id="b8884-141">Attributo <xref:System.String> facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b8884-141">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="b8884-142">Impostare su `includehex` per visualizzare le tracce del protocollo nel formato esadecimale e di testo.</span><span class="sxs-lookup"><span data-stu-id="b8884-142">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="b8884-143">Impostare su `protocolonly` per mostrare solo testo.</span><span class="sxs-lookup"><span data-stu-id="b8884-143">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="b8884-144">Il valore predefinito è `includehex`.</span><span class="sxs-lookup"><span data-stu-id="b8884-144">The default value is `includehex`.</span></span><br /><br /><span data-ttu-id="b8884-145">Questo attributo deve essere impostato sull'elemento **di origine.**</span><span class="sxs-lookup"><span data-stu-id="b8884-145">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="b8884-146">Se questo attributo è impostato su un elemento sotto l'elemento **switches,** viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b8884-146">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="b8884-147">Esempio: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="b8884-147">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|

## <a name="see-also"></a><span data-ttu-id="b8884-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8884-148">See also</span></span>

- [<span data-ttu-id="b8884-149">Interpretazione della traccia di rete</span><span class="sxs-lookup"><span data-stu-id="b8884-149">Interpreting Network Tracing</span></span>](interpreting-network-tracing.md)
- [<span data-ttu-id="b8884-150">Traccia di rete in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b8884-150">Network Tracing in the .NET Framework</span></span>](network-tracing.md)
- [<span data-ttu-id="b8884-151">Abilitazione della traccia di rete</span><span class="sxs-lookup"><span data-stu-id="b8884-151">Enabling Network Tracing</span></span>](enabling-network-tracing.md)
- [<span data-ttu-id="b8884-152">Traccia e strumentazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="b8884-152">Tracing and Instrumenting Applications</span></span>](../debug-trace-profile/tracing-and-instrumenting-applications.md)
