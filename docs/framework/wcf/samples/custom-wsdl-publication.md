---
title: Pubblicazione WSDL personalizzata
ms.date: 03/30/2017
ms.assetid: 3b3e8103-2c95-4db3-a05b-46aa8e9d4d29
ms.openlocfilehash: b18ac2f72d58c768b3784e1c414a71cdaec50c01
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596695"
---
# <a name="custom-wsdl-publication"></a>Pubblicazione WSDL personalizzata
Questo esempio dimostra come:  
  
- Implementare un'interfaccia <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> su un attributo <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> personalizzato per esportare le proprietà dell'attributo come annotazioni WSDL.  
  
- Implementare <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> per importare le annotazioni WSDL personalizzate.  
  
- Implementare <xref:System.ServiceModel.Description.IServiceContractGenerationExtension?displayProperty=nameWithType> e <xref:System.ServiceModel.Description.IOperationContractGenerationExtension?displayProperty=nameWithType> rispettivamente su un comportamento del contratto personalizzato e un comportamento dell'operazione personalizzato per scrivere le annotazioni importate come commenti in CodeDOM per il contratto e l'operazione importati.  
  
- Usare <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> per scaricare il file WSDL, un oggetto <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> per importare il file WSDL usando l'utilità di importazione WSDL personalizzata e <xref:System.ServiceModel.Description.ServiceContractGenerator?displayProperty=nameWithType> per generare il codice client di Windows Communication Foundation (WCF) con le annotazioni WSDL come///e i commenti ''' in C# e Visual Basic.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
## <a name="service"></a>Service  
 Il servizio in questo esempio è contrassegnato con due attributi personalizzati. Il primo, `WsdlDocumentationAttribute`, accetta una stringa nel costruttore e può essere applicato per fornire un'interfaccia o un'operazione del contratto con una stringa che ne descrive l'utilizzo. Il secondo, `WsdlParamOrReturnDocumentationAttribute`, può essere applicato ai valori o parametri restituiti per descrivere tali valori nell'operazione. Nell'esempio seguente viene illustrato un contratto di servizio, `ICalculator`, descritto mediante tali attributi.  
  
```csharp  
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
// Document it.  
[WsdlDocumentation("The ICalculator contract performs basic calculation services.")]  
public interface ICalculator  
{  
    [OperationContract]  
    [WsdlDocumentation("The Add operation adds two numbers and returns the result.")]  
    [return:WsdlParamOrReturnDocumentation("The result of adding the two arguments together.")]  
    double Add(  
      [WsdlParamOrReturnDocumentation("The first value to add.")]double n1,
      [WsdlParamOrReturnDocumentation("The second value to add.")]double n2  
    );  
  
    [OperationContract]  
    [WsdlDocumentation("The Subtract operation subtracts the second argument from the first.")]  
    [return:WsdlParamOrReturnDocumentation("The result of the second argument subtracted from the first.")]  
    double Subtract(  
      [WsdlParamOrReturnDocumentation("The value from which the second is subtracted.")]double n1,
      [WsdlParamOrReturnDocumentation("The value that is subtracted from the first.")]double n2  
    );  
  
    [OperationContract]  
    [WsdlDocumentation("The Multiply operation multiplies two values.")]  
    [return:WsdlParamOrReturnDocumentation("The result of multiplying the first and second arguments.")]  
    double Multiply(  
      [WsdlParamOrReturnDocumentation("The first value to multiply.")]double n1,
      [WsdlParamOrReturnDocumentation("The second value to multiply.")]double n2  
    );  
  
    [OperationContract]  
    [WsdlDocumentation("The Divide operation returns the value of the first argument divided by the second argument.")]  
    [return:WsdlParamOrReturnDocumentation("The result of dividing the first argument by the second.")]  
    double Divide(  
      [WsdlParamOrReturnDocumentation("The numerator.")]double n1,
      [WsdlParamOrReturnDocumentation("The denominator.")]double n2  
    );  
}  
```  
  
 `WsdlDocumentationAttribute` implementa <xref:System.ServiceModel.Description.IContractBehavior> e <xref:System.ServiceModel.Description.IOperationBehavior>, pertanto le istanze dell'attributo vengono aggiunte all'elemento <xref:System.ServiceModel.Description.ContractDescription> o <xref:System.ServiceModel.Description.OperationDescription> corrispondente quando il servizio è aperto. L'attributo implementa anche <xref:System.ServiceModel.Description.IWsdlExportExtension>. Quando il metodo <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%28System.ServiceModel.Description.WsdlExporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> viene chiamato, l'elemento <xref:System.ServiceModel.Description.WsdlExporter> utilizzato per esportare i metadati e l'elemento <xref:System.ServiceModel.Description.WsdlContractConversionContext> contenente gli oggetti descrizione del servizio vengono passati come parametri che abilitano la modifica dei metadati esportati.  
  
 In questo esempio, a seconda che l'oggetto contesto di esportazione disponga di un elemento <xref:System.ServiceModel.Description.ContractDescription> o un elemento <xref:System.ServiceModel.Description.OperationDescription>, viene estratto un commento dall'attributo utilizzando la proprietà Text e viene aggiunto all'elemento annotazione WSDL, come illustrato nel codice seguente.  
  
```csharp
public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)
{
    if (contractDescription != null)
    {
        // Inside this block it is the contract-level comment attribute.
        // This.Text returns the string for the contract attribute.
        // Set the doc element; if this isn't done first, there is no XmlElement in the
        // DocumentElement property.
        context.WsdlPortType.Documentation = string.Empty;
        // Contract comments.
        XmlDocument owner = context.WsdlPortType.DocumentationElement.OwnerDocument;
        XmlElement summaryElement = owner.CreateElement("summary");
        summaryElement.InnerText = this.Text;
        context.WsdlPortType.DocumentationElement.AppendChild(summaryElement);
    }
    else
    {
        Operation operation = context.GetOperation(operationDescription);
        if (operation != null)
        {
            // We are dealing strictly with the operation here.
            // This.Text returns the string for the operation-level attributes.
            // Set the doc element; if this isn't done first, there is no XmlElement in the
            // DocumentElement property.
            operation.Documentation = String.Empty;

            // Operation C# triple comments.
            XmlDocument owner = operation.DocumentationElement.OwnerDocument;
            XmlElement newSummaryElement = owner.CreateElement("summary");
            newSummaryElement.InnerText = this.Text;
            operation.DocumentationElement.AppendChild(newSummaryElement);
        }
    }
}
```  
  
 Se un'operazione viene esportata, l'esempio utilizza la reflection per ottenere qualsiasi valore `WsdlParamOrReturnDocumentationAttribute` per i parametri e i valori restituiti e li aggiunge agli elementi annotazione WSDL per tale operazione, come segue.  
  
```csharp
// Get returns information  
ParameterInfo returnValue = operationDescription.SyncMethod.ReturnParameter;  
object[] returnAttrs = returnValue.GetCustomAttributes(typeof(WsdlParamOrReturnDocumentationAttribute), false);  
if (returnAttrs.Length != 0)  
{  
    // <returns>text.</returns>  
    XmlElement returnsElement = owner.CreateElement("returns");  
    returnsElement.InnerText = ((WsdlParamOrReturnDocumentationAttribute)returnAttrs[0]).ParamComment;  
    operation.DocumentationElement.AppendChild(returnsElement);  
}  
  
// Get parameter information.  
ParameterInfo[] args = operationDescription.SyncMethod.GetParameters();  
for (int i = 0; i < args.Length; i++)  
{  
    object[] docAttrs = args[i].GetCustomAttributes(typeof(WsdlParamOrReturnDocumentationAttribute), false);  
    if (docAttrs.Length == 1)  
    {  
        // <param name="Int1">Text.</param>  
        XmlElement newParamElement = owner.CreateElement("param");  
        XmlAttribute paramName = owner.CreateAttribute("name");  
        paramName.Value = args[i].Name;  
        newParamElement.InnerText = ((WsdlParamOrReturnDocumentationAttribute)docAttrs[0]).ParamComment;  
        newParamElement.Attributes.Append(paramName);  
        operation.DocumentationElement.AppendChild(newParamElement);  
    }  
}  
```  
  
 Nell'esempio i metadati vengono quindi pubblicati nella modalità standard, utilizzando il file di configurazione seguente.  
  
```xml  
<services>  
  <service
      name="Microsoft.ServiceModel.Samples.CalculatorService"  
      behaviorConfiguration="CalculatorServiceBehavior">  
    <!-- ICalculator is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc  -->  
    <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    <!-- the mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->  
    <endpoint address="mex"  
              binding="mexHttpBinding"  
              contract="IMetadataExchange" />  
  </service>  
</services>  
  
<!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="svcutil-client"></a>Client Svcutil  
 In questo esempio non viene utilizzato Svcutil.exe. Il contratto viene fornito nel file generatedClient.cs in modo che dopo che la dimostrazione dell'importazione WSDL personalizzata e della generazione di codice nell'esempio, il servizio può essere richiamato. Per usare l'utilità di importazione WSDL personalizzata seguente per questo esempio, è possibile eseguire Svcutil.exe e specificare l'opzione `/svcutilConfig`, fornendo il percorso al file di configurazione client usato in questo esempio, che fa riferimento alla libreria `WsdlDocumentation.dll`. Per caricare `WsdlDocumentationImporter`, tuttavia, Svuctil.exe deve essere in grado di trovare e caricare la libreria `WsdlDocumentation.dll`, la quale deve pertanto essere registrata nella Global Assembly Cache nel percorso o essere inclusa nella stessa directory di Svcutil.exe. Per un esempio di base attinente, la procedura più facile consiste nel copiare Svcutil.exe e il file di configurazione client nella stessa directory di `WsdlDocumentation.dll` ed eseguirlo da quella posizione.  
  
## <a name="the-custom-wsdl-importer"></a>Unità di importazione WSDL personalizzata  
 L'oggetto <xref:System.ServiceModel.Description.IWsdlImportExtension> personalizzato, `WsdlDocumentationImporter`, implementa anche <xref:System.ServiceModel.Description.IContractBehavior> e <xref:System.ServiceModel.Description.IOperationBehavior> per essere aggiunto ai ServiceEndpoints importati e <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> e <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> per essere richiamato per modificare la generazione del codice quando viene creato il contratto o il codice dell'operazione.  
  
 Innanzitutto, con il metodo <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> viene determinato se l'annotazione WSDL è a livello del contratto o dell'operazione, e viene aggiunta come un comportamento all'ambito appropriato, passando il testo dell'annotazione importato al costruttore.  
  
```csharp
public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)  
{  
    // Contract Documentation  
    if (context.WsdlPortType.Documentation != null)  
    {  
        // System examines the contract behaviors to see whether any implement IWsdlImportExtension.  
        context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));  
    }  
    // Operation Documentation  
    foreach (Operation operation in context.WsdlPortType.Operations)  
    {  
        if (operation.Documentation != null)  
        {  
            OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);  
            if (operationDescription != null)  
            {  
                // System examines the operation behaviors to see whether any implement IWsdlImportExtension.  
                operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));  
            }  
        }  
    }  
}  
```  
  
 Quindi, quando il codice viene generato, il sistema richiama i metodi <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> e <xref:System.ServiceModel.Description.IOperationContractGenerationExtension.GenerateOperation%28System.ServiceModel.Description.OperationContractGenerationContext%29>, passando le informazioni di contesto appropriate. Le annotazioni WSDL personalizzate vengono formattate e inseriste come commenti in CodeDOM.  
  
```csharp
public void GenerateContract(ServiceContractGenerationContext context)  
{  
    Debug.WriteLine("In generate contract.");  
    context.ContractType.Comments.AddRange(FormatComments(text));  
}  
  
public void GenerateOperation(OperationContractGenerationContext context)  
{  
    context.SyncMethod.Comments.AddRange(FormatComments(text));  
    Debug.WriteLine("In generate operation.");  
}  
```  
  
## <a name="the-client-application"></a>Applicazione client  
 L'applicazione client carica l'unità di importazione WSDL personalizzata specificandola nel file di configurazione dell'applicazione.  
  
```xml  
<client>  
  <endpoint address="http://localhost/servicemodelsamples/service.svc"
  binding="wsHttpBinding"
  contract="ICalculator" />  
  <metadata>  
    <wsdlImporters>  
      <extension type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
    </wsdlImporters>  
  </metadata>  
</client>  
```  
  
 Una volta specificata l'utilità di importazione personalizzata, il sistema di metadati WCF carica l'utilità di importazione personalizzata in qualsiasi <xref:System.ServiceModel.Description.WsdlImporter> oggetto creato a tale scopo. In questo esempio viene utilizzato <xref:System.ServiceModel.Description.MetadataExchangeClient> per scaricare i metadati, l'elemento <xref:System.ServiceModel.Description.WsdlImporter> configurato correttamente per importare i metadati utilizzando l'unità di importazione personalizzata creata dall'esempio e <xref:System.ServiceModel.Description.ServiceContractGenerator> per compilare le informazioni del contratto modificate nel codice client Visual Basic e C# che possono essere utilizzate in Visual Studio per supportare Intellisense o possono essere compilate nella documentazione XML.  
  
```csharp
/// From WSDL Documentation:  
///
/// <summary>The ICalculator contract performs basic calculation
/// services.</summary>
///
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.ServiceModel.Samples", ConfigurationName="ICalculator")]  
public interface ICalculator  
{  
  
    /// From WSDL Documentation:  
    ///
    /// <summary>The Add operation adds two numbers and returns the
    /// result.</summary><returns>The result of adding the two arguments
    /// together.</returns><param name="n1">The first value to add.</param><param
    /// name="n2">The second value to add.</param>
    ///
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.ServiceModel.Samples/ICalculator/Add", ReplyAction="http://Microsoft.ServiceModel.Samples/ICalculator/AddResponse")]  
    double Add(double n1, double n2);  
  
    /// From WSDL Documentation:  
    ///
    /// <summary>The Subtract operation subtracts the second argument from the
    /// first.</summary><returns>The result of the second argument subtracted from the
    /// first.</returns><param name="n1">The value from which the second is
    /// subtracted.</param><param name="n2">The value that is subtracted from the
    /// first.</param>
    ///
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.ServiceModel.Samples/ICalculator/Subtract", ReplyAction="http://Microsoft.ServiceModel.Samples/ICalculator/SubtractResponse")]  
    double Subtract(double n1, double n2);  
  
    /// From WSDL Documentation:  
    ///
    /// <summary>The Multiply operation multiplies two values.</summary><returns>The
    /// result of multiplying the first and second arguments.</returns><param
    /// name="n1">The first value to multiply.</param><param name="n2">The second value
    /// to multiply.</param>
    ///
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.ServiceModel.Samples/ICalculator/Multiply", ReplyAction="http://Microsoft.ServiceModel.Samples/ICalculator/MultiplyResponse")]  
    double Multiply(double n1, double n2);  
  
    /// From WSDL Documentation:  
    ///
    /// <summary>The Divide operation returns the value of the first argument divided
    /// by the second argument.</summary><returns>The result of dividing the first
    /// argument by the second.</returns><param name="n1">The numerator.</param><param
    /// name="n2">The denominator.</param>
    ///
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.ServiceModel.Samples/ICalculator/Divide", ReplyAction="http://Microsoft.ServiceModel.Samples/ICalculator/DivideResponse")]  
    double Divide(double n1, double n2);  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Metadata\WsdlDocumentation`  
