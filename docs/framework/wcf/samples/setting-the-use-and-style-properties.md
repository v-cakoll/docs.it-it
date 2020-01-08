---
title: Impostazione degli esempi di proprietà Use e Style
ms.date: 03/30/2017
ms.assetid: c09a0600-116f-41cf-900a-1b7e4ea4e300
ms.openlocfilehash: 36111aa05680fb8b369cde6b42d22c9c3b8474ad
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345138"
---
# <a name="setting-the-use-and-style-properties"></a><span data-ttu-id="3302b-102">Impostazione delle proprietà Use e Style</span><span class="sxs-lookup"><span data-stu-id="3302b-102">Setting the Use and Style Properties</span></span>

<span data-ttu-id="3302b-103">In questo esempio viene illustrato l'uso delle proprietà Use e Style in <xref:System.ServiceModel.XmlSerializerFormatAttribute> e <xref:System.ServiceModel.DataContractFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3302b-103">This sample demonstrates how to use the Use and Style properties on the <xref:System.ServiceModel.XmlSerializerFormatAttribute> and the <xref:System.ServiceModel.DataContractFormatAttribute>.</span></span> <span data-ttu-id="3302b-104">Queste proprietà influiscono sulla formattazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="3302b-104">These properties affect how messages are formatted.</span></span> <span data-ttu-id="3302b-105">Per impostazione predefinita, la formattazione del corpo del messaggio prevede che lo stile sia impostato su <xref:System.ServiceModel.OperationFormatStyle.Document>.</span><span class="sxs-lookup"><span data-stu-id="3302b-105">By default, the message body is formatted with the style set to <xref:System.ServiceModel.OperationFormatStyle.Document>.</span></span> <span data-ttu-id="3302b-106">Queste impostazioni possono essere specificate a livello del contratto di servizio o a livello del contratto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="3302b-106">These settings can be specified at either the service contract level or the operation contract level.</span></span>

> [!NOTE]
> <span data-ttu-id="3302b-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3302b-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="3302b-108">La proprietà di stile <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> determina come vengono formattati i metadati WSDL per il servizio.</span><span class="sxs-lookup"><span data-stu-id="3302b-108">The <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> style property determines how the WSDL metadata for the service is formatted.</span></span> <span data-ttu-id="3302b-109">I valori possibili sono <xref:System.ServiceModel.OperationFormatStyle.Document> e <xref:System.ServiceModel.OperationFormatStyle.Rpc>.</span><span class="sxs-lookup"><span data-stu-id="3302b-109">Possible values are <xref:System.ServiceModel.OperationFormatStyle.Document>, and <xref:System.ServiceModel.OperationFormatStyle.Rpc>.</span></span> <span data-ttu-id="3302b-110">RPC indica che la rappresentazione WSDL dei messaggi scambiati in un'operazione contiene parametri analoghi a quelli di una chiamata a procedura remota.</span><span class="sxs-lookup"><span data-stu-id="3302b-110">RPC means that the WSDL representation of messages exchanged for an operation contains parameters as if it were a remote procedure call.</span></span> <span data-ttu-id="3302b-111">Di seguito è riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="3302b-111">The following is an example.</span></span>

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="n1" type="xsd:double"/>
  <wsdl:part name="n2" type="xsd:double"/>
</wsdl:message>
```

<span data-ttu-id="3302b-112">Se si imposta lo stile su <xref:System.ServiceModel.OperationFormatStyle.Document> la rappresentazione WSDL contiene un solo elemento che rappresenta il documento scambiato in un'operazione, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3302b-112">Setting the style to <xref:System.ServiceModel.OperationFormatStyle.Document> means that the WSDL representation contains a single element that represents the document that is exchanged for an operation as shown in the following example.</span></span>

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="parameters" element="tns:Add"/>
</wsdl:message>
```

<span data-ttu-id="3302b-113">La proprietà <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> determina il formato del messaggio.</span><span class="sxs-lookup"><span data-stu-id="3302b-113">The <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> property determines the format of the message.</span></span> <span data-ttu-id="3302b-114">I valori possibili sono <xref:System.ServiceModel.OperationFormatUse.Literal> e <xref:System.ServiceModel.OperationFormatUse.Encoded>. Il valore predefinito è <xref:System.ServiceModel.OperationFormatUse.Literal>.</span><span class="sxs-lookup"><span data-stu-id="3302b-114">Possible values are <xref:System.ServiceModel.OperationFormatUse.Literal> and <xref:System.ServiceModel.OperationFormatUse.Encoded>; the default value is <xref:System.ServiceModel.OperationFormatUse.Literal>.</span></span> <span data-ttu-id="3302b-115">Literal significa che il messaggio è un'istanza letterale dello schema nel linguaggio WSDL, come illustrato nell'esempio documento/letterale seguente.</span><span class="sxs-lookup"><span data-stu-id="3302b-115">Literal means that the message is a literal instance of the schema in the WSDL as shown in the following Document/ Literal example.</span></span>

```xml
<Add xmlns="http://Microsoft.ServiceModel.Samples">
  <n1>100</n1>
  <n2>15.99</n2>
</Add>
```

<span data-ttu-id="3302b-116">Encoded indica che gli schemi nel linguaggio WSDL sono specifiche astratte codificate secondo le regole incluse nella sezione 5 della specifica di SOAP 1.1.</span><span class="sxs-lookup"><span data-stu-id="3302b-116">Encoded means that the schemas in the WSDL are abstract specifications that are encoded according to the rules found in SOAP 1.1 section 5.</span></span> <span data-ttu-id="3302b-117">Di seguito viene riportato un esempio RPC/codificato.</span><span class="sxs-lookup"><span data-stu-id="3302b-117">The following is an RPC/Encoded example.</span></span>

```xml
<q1:Add xmlns:q1="http://Microsoft.ServiceModel.Samples">
  <n1 xsi:type="xsd:double" xmlns="">100</n1>
  <n2 xsi:type="xsd:double" xmlns="">15.99</n2>
</q1:Add>
```

<span data-ttu-id="3302b-118">L'uso di <xref:System.ServiceModel.OperationFormatUse.Encoded> è proibito in WS-I Basic Profile 1.0 e deve essere usato solo quando richiesto dai servizi legacy.</span><span class="sxs-lookup"><span data-stu-id="3302b-118">The WS-I Basic Profile 1.0 prohibits the use of <xref:System.ServiceModel.OperationFormatUse.Encoded> and you should only use it when required by legacy services.</span></span> <span data-ttu-id="3302b-119">Il formato di messaggio `Encoded` è disponibile solo quando si usa XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="3302b-119">The `Encoded` message format is only available when using the XmlSerializer.</span></span>

<span data-ttu-id="3302b-120">Per consentire la visualizzazione dei messaggi inviati e ricevuti, questo esempio è basato sulla [traccia e sulla registrazione dei messaggi](tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="3302b-120">To allow you to see the messages being sent and received, this sample is based on the [Tracing and Message Logging](tracing-and-message-logging.md).</span></span> <span data-ttu-id="3302b-121">La configurazione del servizio e il codice sorgente sono stati modificati per abilitare e usare la traccia e la registrazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="3302b-121">The service configuration and source code have been modified to enable and utilize tracing and message logging.</span></span> <span data-ttu-id="3302b-122"><xref:System.ServiceModel.WSHttpBinding> è stato inoltre configurato senza la sicurezza, pertanto i messaggi registrati possono essere visualizzati in un formato non crittografato.</span><span class="sxs-lookup"><span data-stu-id="3302b-122">In addition, the <xref:System.ServiceModel.WSHttpBinding> has been configured without security, so the logged messages can be viewed in an unencrypted format.</span></span> <span data-ttu-id="3302b-123">Per visualizzare i log di traccia risultanti (System. ServiceModel. e2e e Message. log), usare lo [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="3302b-123">The resulting trace logs (System.ServiceModel.e2e and Message.log) should be viewed by using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="3302b-124">Le tracci vengono configurate per essere create nella cartella C:\LOGS.</span><span class="sxs-lookup"><span data-stu-id="3302b-124">The traces are configured to be created in the C:\LOGS folder.</span></span> <span data-ttu-id="3302b-125">Creare la cartella prima di eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="3302b-125">Create the folder before running the sample.</span></span> <span data-ttu-id="3302b-126">Per visualizzare il contenuto del messaggio nello strumento Visualizzatore di tracce, selezionare **messaggi** nei riquadri di sinistra e di destra dello strumento.</span><span class="sxs-lookup"><span data-stu-id="3302b-126">To view message contents in the Trace Viewer tool, select **Messages** in both the left and the right panes of the tool.</span></span>

<span data-ttu-id="3302b-127">Nel codice seguente viene descritto il contratto di servizio con la proprietà <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> impostata su <xref:System.ServiceModel.OperationFormatUse> e il formato del corpo del messaggio modificato dal valore predefinito <xref:System.ServiceModel.OperationFormatStyle> a <xref:System.ServiceModel.OperationFormatStyle.Document>.</span><span class="sxs-lookup"><span data-stu-id="3302b-127">The following code shows the service contract with the <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> property set to <xref:System.ServiceModel.OperationFormatUse> and the format of the message body changed from the default <xref:System.ServiceModel.OperationFormatStyle> to <xref:System.ServiceModel.OperationFormatStyle.Document>.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),
XmlSerializerFormat(Style = OperationFormatStyle.Rpc, 
                                 Use = OperationFormatUse.Encoded)]
public interface IUseAndStyleCalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

<span data-ttu-id="3302b-128">Per visualizzare la differenza tra le impostazioni <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> e <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A>, modificarle nel servizio, rigenerare il client, eseguire l'esempio ed esaminare il file c:\logs\message.logs con lo strumento Visualizzatore di tracce dei servizi.</span><span class="sxs-lookup"><span data-stu-id="3302b-128">To see the difference between the different <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> and <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A> settings, modify them in the service, regenerate the client, run the sample, and examine the c:\logs\message.logs file with the Service Trace Viewer tool.</span></span> <span data-ttu-id="3302b-129">Osservare anche l'effetto sui metadati visualizzando `http://localhost/ServiceModelSamples/service.svc?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="3302b-129">Also observe the impact on the metadata by viewing `http://localhost/ServiceModelSamples/service.svc?wsdl`.</span></span> <span data-ttu-id="3302b-130">I metadati per i servizi in genere vengono suddivisi su più pagine.</span><span class="sxs-lookup"><span data-stu-id="3302b-130">The metadata for services is typically broken up into multiple pages.</span></span> <span data-ttu-id="3302b-131">La pagina WSDL principale contiene le associazioni WSDL, ma Visualizza `http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0` per osservare le definizioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="3302b-131">The main wsdl page contains the WSDL bindings, but view `http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0` to observe the message definitions.</span></span>

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3302b-132">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="3302b-132">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="3302b-133">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3302b-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="3302b-134">Creare una directory C:\LOGS per la registrazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="3302b-134">Create a C:\LOGS directory for logging messages.</span></span> <span data-ttu-id="3302b-135">Assegnare all'account Servizio di rete le autorizzazioni di scrittura per questa directory.</span><span class="sxs-lookup"><span data-stu-id="3302b-135">Give the user Network Service write permissions for this directory.</span></span>

3. <span data-ttu-id="3302b-136">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3302b-136">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="3302b-137">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3302b-137">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3302b-138">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3302b-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3302b-139">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3302b-139">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="3302b-140">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="3302b-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3302b-141">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3302b-141">This sample is located in the following directory.</span></span>
> 
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\UseAndStyle`
