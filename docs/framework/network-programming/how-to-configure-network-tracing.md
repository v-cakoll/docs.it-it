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
ms.openlocfilehash: 6b1a61ac7566f624f44480ffed2337dba5e51ca2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143363"
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="f39c6-102">Procedura: Configurare la traccia di rete</span><span class="sxs-lookup"><span data-stu-id="f39c6-102">How to: Configure Network Tracing</span></span>
<span data-ttu-id="f39c6-103">Nel file di configurazione del computer o dell'applicazione sono contenute le impostazioni che determinano il formato e il contenuto delle tracce di rete.</span><span class="sxs-lookup"><span data-stu-id="f39c6-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="f39c6-104">Prima di eseguire questa procedura, assicurarsi che la funzionalità di traccia sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="f39c6-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="f39c6-105">Per informazioni su come abilitare la traccia di rete, vedere [Abilitazione della traccia di rete](../../../docs/framework/network-programming/enabling-network-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="f39c6-105">For information about enabling tracing, see [Enabling Network Tracing](../../../docs/framework/network-programming/enabling-network-tracing.md).</span></span>  
  
 <span data-ttu-id="f39c6-106">Il file di configurazione del computer, machine.config, è memorizzato nella cartella %Windir%\Microsoft.NET\Framework nella directory in cui è installato Windows.</span><span class="sxs-lookup"><span data-stu-id="f39c6-106">The computer configuration file, machine.config, is stored in the %Windir%\Microsoft.NET\Framework folder in the directory where Windows was installed.</span></span> <span data-ttu-id="f39c6-107">Esiste un file machine.config separato nelle cartelle %Windir%\Microsoft.NET\Framework per ogni versione di .NET Framework installata nel computer, ad esempio C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config o C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.</span><span class="sxs-lookup"><span data-stu-id="f39c6-107">There is a separate machine.config file in the folders under %Windir%\Microsoft.NET\Framework for each version of the .NET Framework installed on the computer (for example, C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config or C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.).</span></span>  
  
 <span data-ttu-id="f39c6-108">Queste impostazioni possono essere effettuate anche nel file di configurazione dell'applicazione, che ha la precedenza sul file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="f39c6-108">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
### <a name="to-configure-network-tracing"></a><span data-ttu-id="f39c6-109">Per configurare la traccia di rete</span><span class="sxs-lookup"><span data-stu-id="f39c6-109">To configure network tracing</span></span>  
  
-   <span data-ttu-id="f39c6-110">Aggiungere le seguenti righe al file di configurazione appropriato.</span><span class="sxs-lookup"><span data-stu-id="f39c6-110">Add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="f39c6-111">I valori e le opzioni per queste impostazioni sono descritti nelle tabelle riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="f39c6-111">The values and options for these settings are described in the tables below.</span></span>  
  
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
  
 <span data-ttu-id="f39c6-112">Quando si aggiunge un nome al blocco `<switches>`, l'output di traccia include informazioni da alcuni metodi correlati al nome.</span><span class="sxs-lookup"><span data-stu-id="f39c6-112">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="f39c6-113">Nella tabella riportata di seguito viene descritto l'output.</span><span class="sxs-lookup"><span data-stu-id="f39c6-113">The following table describes the output.</span></span>  
  
|<span data-ttu-id="f39c6-114">nome</span><span class="sxs-lookup"><span data-stu-id="f39c6-114">Name</span></span>|<span data-ttu-id="f39c6-115">Output da</span><span class="sxs-lookup"><span data-stu-id="f39c6-115">Output from</span></span>|  
|----------|-----------------|  
|`System.Net.Sockets`|<span data-ttu-id="f39c6-116">Alcuni metodi pubblici delle classi <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> e <xref:System.Net.Dns></span><span class="sxs-lookup"><span data-stu-id="f39c6-116">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes</span></span>|  
|`System.Net`|<span data-ttu-id="f39c6-117">Alcuni metodi pubblici delle classi <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> e <xref:System.Net.FtpWebResponse> e informazioni sul debug SSL (certificati non validi, elenco di autorità emittenti mancante ed errori di certificato del client).</span><span class="sxs-lookup"><span data-stu-id="f39c6-117">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors.)</span></span>|  
|`System.Net.HttpListener`|<span data-ttu-id="f39c6-118">Alcuni metodi pubblici delle classi <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> e <xref:System.Net.HttpListenerResponse>.</span><span class="sxs-lookup"><span data-stu-id="f39c6-118">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|  
|`System.Net.Cache`|<span data-ttu-id="f39c6-119">Alcuni metodi interni e privati in `System.Net.Cache`.</span><span class="sxs-lookup"><span data-stu-id="f39c6-119">Some private and internal methods in `System.Net.Cache`.</span></span>|  
|`System.Net.Http`|<span data-ttu-id="f39c6-120">Alcuni metodi pubblici delle classi <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> e <xref:System.Net.Http.WebRequestHandler>.</span><span class="sxs-lookup"><span data-stu-id="f39c6-120">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|  
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="f39c6-121">Alcuni metodi pubblici delle classi <xref:System.Net.WebSockets.ClientWebSocket> e <xref:System.Net.WebSockets.WebSocket>.</span><span class="sxs-lookup"><span data-stu-id="f39c6-121">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|  
  
 <span data-ttu-id="f39c6-122">Gli attributi elencati nella tabella seguente sono utilizzati per configurare l'output di traccia.</span><span class="sxs-lookup"><span data-stu-id="f39c6-122">The attributes listed in the following table configure trace output.</span></span>  
  
|<span data-ttu-id="f39c6-123">Nome attributo</span><span class="sxs-lookup"><span data-stu-id="f39c6-123">Attribute name</span></span>|<span data-ttu-id="f39c6-124">Valore attributo</span><span class="sxs-lookup"><span data-stu-id="f39c6-124">Attribute value</span></span>|  
|--------------------|---------------------|  
|`Value`|<span data-ttu-id="f39c6-125">Attributo <xref:System.String> obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f39c6-125">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="f39c6-126">Imposta il livello di dettaglio dell'output.</span><span class="sxs-lookup"><span data-stu-id="f39c6-126">Sets the verbosity of the output.</span></span> <span data-ttu-id="f39c6-127">I valori consentiti sono `Critical`, `Error`, `Verbose`, `Warning` e `Information`.</span><span class="sxs-lookup"><span data-stu-id="f39c6-127">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /> <span data-ttu-id="f39c6-128">Questo attributo deve essere impostato per l'elemento \<add name> dell'elemento \<switches> come mostrato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="f39c6-128">This attribute must be set on the \<add name> element of the \<switches> element as shown in the example.</span></span> <span data-ttu-id="f39c6-129">Viene generata un'eccezione se l'attributo viene impostato per l'elemento \<source>.</span><span class="sxs-lookup"><span data-stu-id="f39c6-129">An exception is thrown if this attribute is set on the \<source> element.</span></span>|  
|`maxdatasize`|<span data-ttu-id="f39c6-130">Attributo <xref:System.Int32> facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f39c6-130">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="f39c6-131">Imposta il numero massimo di byte di dati di rete inclusi in ogni traccia di riga.</span><span class="sxs-lookup"><span data-stu-id="f39c6-131">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="f39c6-132">Il valore predefinito è 1024.</span><span class="sxs-lookup"><span data-stu-id="f39c6-132">The default value is 1024.</span></span><br /><br /> <span data-ttu-id="f39c6-133">Questo attributo deve essere impostato per l'elemento \<source> come mostrato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="f39c6-133">This attribute must be set on the \<source> element as shown in the example.</span></span> <span data-ttu-id="f39c6-134">Viene generata un'eccezione se questo attributo viene impostato per un elemento sotto l'elemento \<switches>.</span><span class="sxs-lookup"><span data-stu-id="f39c6-134">An exception is thrown if this attribute is set on an element under the \<switches> element.</span></span>|  
|`Tracemode`|<span data-ttu-id="f39c6-135">Attributo <xref:System.String> facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f39c6-135">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="f39c6-136">Impostare su `includehex` per visualizzare le tracce del protocollo nel formato esadecimale e di testo.</span><span class="sxs-lookup"><span data-stu-id="f39c6-136">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="f39c6-137">Impostare su `protocolonly` per mostrare solo testo.</span><span class="sxs-lookup"><span data-stu-id="f39c6-137">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="f39c6-138">Il valore predefinito è `includehex`.</span><span class="sxs-lookup"><span data-stu-id="f39c6-138">The default value is `includehex`.</span></span><br /><br /> <span data-ttu-id="f39c6-139">Questo attributo deve essere impostato per l'elemento \<switches> come mostrato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="f39c6-139">This attribute must be set on the \<switches> element as shown in the example.</span></span> <span data-ttu-id="f39c6-140">Viene generata un'eccezione se questo attributo viene impostato per un elemento sotto l'elemento \<source>.</span><span class="sxs-lookup"><span data-stu-id="f39c6-140">An exception is thrown if this attribute is set on an element under the \<source> element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f39c6-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f39c6-141">See Also</span></span>  
 [<span data-ttu-id="f39c6-142">Interpretazione della traccia di rete</span><span class="sxs-lookup"><span data-stu-id="f39c6-142">Interpreting Network Tracing</span></span>](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [<span data-ttu-id="f39c6-143">Traccia di rete in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f39c6-143">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)  
 [<span data-ttu-id="f39c6-144">Abilitazione della traccia di rete</span><span class="sxs-lookup"><span data-stu-id="f39c6-144">Enabling Network Tracing</span></span>](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [<span data-ttu-id="f39c6-145">Traccia e strumentazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="f39c6-145">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
