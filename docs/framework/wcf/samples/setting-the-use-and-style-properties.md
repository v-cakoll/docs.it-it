---
title: Esempi di utilizzo e stile delle proprietà
ms.date: 03/30/2017
ms.assetid: c09a0600-116f-41cf-900a-1b7e4ea4e300
ms.openlocfilehash: f400c0bc08588afa951ae33f221663b47b37602c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144032"
---
# <a name="setting-the-use-and-style-properties"></a>Impostazione delle proprietà Use e Style

In questo esempio viene illustrato l'uso delle proprietà Use e Style in <xref:System.ServiceModel.XmlSerializerFormatAttribute> e <xref:System.ServiceModel.DataContractFormatAttribute>. Queste proprietà influiscono sulla formattazione dei messaggi. Per impostazione predefinita, la formattazione del corpo del messaggio prevede che lo stile sia impostato su <xref:System.ServiceModel.OperationFormatStyle.Document>. Queste impostazioni possono essere specificate a livello del contratto di servizio o a livello del contratto dell'operazione.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

La proprietà di stile <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> determina come vengono formattati i metadati WSDL per il servizio. I valori possibili sono <xref:System.ServiceModel.OperationFormatStyle.Document> e <xref:System.ServiceModel.OperationFormatStyle.Rpc>. RPC indica che la rappresentazione WSDL dei messaggi scambiati in un'operazione contiene parametri analoghi a quelli di una chiamata a procedura remota. Di seguito è riportato un esempio.

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="n1" type="xsd:double"/>
  <wsdl:part name="n2" type="xsd:double"/>
</wsdl:message>
```

Se si imposta lo stile su <xref:System.ServiceModel.OperationFormatStyle.Document> la rappresentazione WSDL contiene un solo elemento che rappresenta il documento scambiato in un'operazione, come mostrato nell'esempio seguente.

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="parameters" element="tns:Add"/>
</wsdl:message>
```

La proprietà <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> determina il formato del messaggio. I valori possibili sono <xref:System.ServiceModel.OperationFormatUse.Literal> e <xref:System.ServiceModel.OperationFormatUse.Encoded>. Il valore predefinito è <xref:System.ServiceModel.OperationFormatUse.Literal>. Literal significa che il messaggio è un'istanza letterale dello schema nel linguaggio WSDL, come illustrato nell'esempio documento/letterale seguente.

```xml
<Add xmlns="http://Microsoft.ServiceModel.Samples">
  <n1>100</n1>
  <n2>15.99</n2>
</Add>
```

Encoded indica che gli schemi nel linguaggio WSDL sono specifiche astratte codificate secondo le regole incluse nella sezione 5 della specifica di SOAP 1.1. Di seguito viene riportato un esempio RPC/codificato.

```xml
<q1:Add xmlns:q1="http://Microsoft.ServiceModel.Samples">
  <n1 xsi:type="xsd:double" xmlns="">100</n1>
  <n2 xsi:type="xsd:double" xmlns="">15.99</n2>
</q1:Add>
```

L'uso di <xref:System.ServiceModel.OperationFormatUse.Encoded> è proibito in WS-I Basic Profile 1.0 e deve essere usato solo quando richiesto dai servizi legacy. Il formato di messaggio `Encoded` è disponibile solo quando si usa XmlSerializer.

Per consentire la visualizzazione dei messaggi inviati e ricevuti, questo esempio si basa sulla traccia e la [registrazione dei messaggi](tracing-and-message-logging.md). La configurazione del servizio e il codice sorgente sono stati modificati per abilitare e usare la traccia e la registrazione dei messaggi. <xref:System.ServiceModel.WSHttpBinding> è stato inoltre configurato senza la sicurezza, pertanto i messaggi registrati possono essere visualizzati in un formato non crittografato. I log di traccia risultanti (System.ServiceModel.e2e e Message.log) devono essere visualizzati utilizzando [lo strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md). Le tracci vengono configurate per essere create nella cartella C:\LOGS. Creare la cartella prima di eseguire l'esempio. Per visualizzare il contenuto dei messaggi nello strumento Visualizzatore di traccia, selezionare **Messaggi** sia nel riquadro sinistro che in quello destro dello strumento.

Nel codice seguente viene descritto il contratto di servizio con la proprietà <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> impostata su <xref:System.ServiceModel.OperationFormatUse> e il formato del corpo del messaggio modificato dal valore predefinito <xref:System.ServiceModel.OperationFormatStyle> a <xref:System.ServiceModel.OperationFormatStyle.Document>.

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

Per visualizzare la differenza tra le impostazioni <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> e <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A>, modificarle nel servizio, rigenerare il client, eseguire l'esempio ed esaminare il file c:\logs\message.logs con lo strumento Visualizzatore di tracce dei servizi. Osservare anche l'impatto `http://localhost/ServiceModelSamples/service.svc?wsdl`sui metadati visualizzando . I metadati per i servizi in genere vengono suddivisi su più pagine. La pagina wsdl principale contiene le `http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0` associazioni WSDL, ma la visualizzazione per osservare le definizioni dei messaggi.

## <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).

2. Creare una directory C:\LOGS per la registrazione dei messaggi. Assegnare all'account Servizio di rete le autorizzazioni di scrittura per questa directory.

3. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).

4. Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](running-the-samples.md).

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\UseAndStyle`
