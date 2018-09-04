---
title: Esempio XmlSerializer
ms.date: 03/30/2017
ms.assetid: 7d134453-9a35-4202-ba77-9ca3a65babc3
ms.openlocfilehash: 7b43af08758de1d33bcc6ab8f477885c7ecc0825
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503090"
---
# <a name="xmlserializer-sample"></a><span data-ttu-id="d7c7c-102">Esempio XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="d7c7c-102">XMLSerializer Sample</span></span>
<span data-ttu-id="d7c7c-103">In questo esempio viene illustrato come serializzare e deserializzare tipi compatibili con la classe <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-103">This sample demonstrates how to serialize and deserialize types that are compatible with the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="d7c7c-104">Il formattatore di Windows Communication Foundation (WCF) predefinito è il <xref:System.Runtime.Serialization.DataContractSerializer> classe.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-104">The default Windows Communication Foundation (WCF) formatter is the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span> <span data-ttu-id="d7c7c-105">La classe <xref:System.Xml.Serialization.XmlSerializer> può essere utilizzata per serializzare e deserializzare tipi quando la classe <xref:System.Runtime.Serialization.DataContractSerializer> non può essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-105">The <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize and deserialize types when the <xref:System.Runtime.Serialization.DataContractSerializer> class cannot be used.</span></span> <span data-ttu-id="d7c7c-106">Spesso ciò accade quando è necessario un controllo preciso sul codice XML - ad esempio, se una porzione di dati deve essere un attributo XML e non un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-106">This is often the case when precise control over the XML is required - for example, if a piece of data must be an XML attribute and not an XML element.</span></span> <span data-ttu-id="d7c7c-107">Inoltre, il <xref:System.Xml.Serialization.XmlSerializer> spesso viene selezionata automaticamente durante la creazione di client di servizi non WCF.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-107">Also, the <xref:System.Xml.Serialization.XmlSerializer> often gets automatically selected when creating clients for non-WCF services.</span></span>  
  
 <span data-ttu-id="d7c7c-108">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d7c7c-108">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7c7c-109">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="d7c7c-110">Le classi <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.XmlSerializerFormatAttribute> devono essere applicate all'interfaccia come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-110">The <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.XmlSerializerFormatAttribute> must be applied to the interface as shown in the following sample code.</span></span>  
  
```csharp  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]  
public interface IXmlSerializerCalculator  
{  
    [OperationContract]  
    ComplexNumber Add(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2);  
}  
```  
  
 <span data-ttu-id="d7c7c-111">I membri pubblici della classe `ComplexNumber` vengono serializzati da <xref:System.Xml.Serialization.XmlSerializer> come attributi XML.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-111">The public members of `ComplexNumber` class are serialized by <xref:System.Xml.Serialization.XmlSerializer> as XML attributes.</span></span> <span data-ttu-id="d7c7c-112">È impossibile utilizzare la classe <xref:System.Runtime.Serialization.DataContractSerializer> per creare questo tipo di istanza XML.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-112">The <xref:System.Runtime.Serialization.DataContractSerializer> cannot be used to create this kind of XML instance.</span></span>  
  
```csharp  
public class ComplexNumber  
{  
    private double real;  
    private double imaginary;  
  
    [XmlAttribute]  
    public double Real  
    {  
        get { return real; }  
        set { real = value; }  
    }  
  
    [XmlAttribute]  
    public double Imaginary  
    {  
        get { return imaginary; }  
        set { imaginary = value; }  
    }  
  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
    public ComplexNumber()  
    {  
        this.Real = 0;  
        this.Imaginary = 0;  
    }  
  
}  
```  
  
 <span data-ttu-id="d7c7c-113">L'implementazione del servizio calcola e restituisce il risultato appropriato, accettando e restituendo valori di tipo `ComplexNumber`.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-113">The service implementation calculates and returns the appropriate result—accepting and returning values of the `ComplexNumber` type.</span></span>  
  
```csharp  
public class XmlSerializerCalculatorService : IXmlSerializerCalculator  
{  
    public ComplexNumber Add(ComplexNumber n1, ComplexNumber n2)  
    {  
        return new ComplexNumber(n1.Real + n2.Real, n1.Imaginary +  
                                                      n2.Imaginary);  
    }  
    …  
}  
```  
  
 <span data-ttu-id="d7c7c-114">Anche l'implementazione del client utilizza numeri complessi.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-114">The client implementation also uses complex numbers.</span></span> <span data-ttu-id="d7c7c-115">Il contratto di servizio e i tipi di dati sono definiti nel file di origine generatedClient.cs, generato dal [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) dai metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-115">Both the service contract and the data types are defined in the generatedClient.cs source file, which was generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from service metadata.</span></span> <span data-ttu-id="d7c7c-116">Svcutil.exe può rilevare quando un contratto non è serializzabile da <xref:System.Runtime.Serialization.DataContractSerializer> e, in questo caso, ritornare alla generazione di tipi `XmlSerializable`.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-116">Svcutil.exe can detect when a contract is not serializable by the <xref:System.Runtime.Serialization.DataContractSerializer> and reverts to emitting `XmlSerializable` types in this case.</span></span> <span data-ttu-id="d7c7c-117">Se si desidera forzare l'utilizzo di <xref:System.Xml.Serialization.XmlSerializer>, è possibile passare l'opzione di comando /serializer:XmlSerializer (utilizzare XmlSerializer) allo strumento Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-117">If you want to force the use of the <xref:System.Xml.Serialization.XmlSerializer>, you can pass the /serializer:XmlSerializer (use XmlSerializer) command option to the Svcutil.exe tool.</span></span>  
  
```csharp  
// Create a client.  
XmlSerializerCalculatorClient client = new  
                         XmlSerializerCalculatorClient();  
  
// Call the Add service operation.  
ComplexNumber value1 = new ComplexNumber();  
value1.Real = 1;  
value1.Imaginary = 2;  
ComplexNumber value2 = new ComplexNumber();  
value2.Real = 3;  
value2.Imaginary = 4;  
ComplexNumber result = client.Add(value1, value2);  
Console.WriteLine("Add({0} + {1}i, {2} + {3}i) = {4} + {5}i",  
    value1.Real, value1.Imaginary, value2.Real, value2.Imaginary,   
    result.Real, result.Imaginary);  
    …  
}  
```  
  
 <span data-ttu-id="d7c7c-118">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="d7c7c-119">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(1 + 2i, 3 + 4i) = 4 + 6i  
Subtract(1 + 2i, 3 + 4i) = -2 + -2i  
Multiply(2 + 3i, 4 + 7i) = -13 + 26i  
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 1.41379310344828i  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d7c7c-120">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="d7c7c-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d7c7c-121">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d7c7c-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="d7c7c-122">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d7c7c-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="d7c7c-123">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d7c7c-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d7c7c-124">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d7c7c-125">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d7c7c-126">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d7c7c-127">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="d7c7c-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\Interop\XmlSerializer`  
  
## <a name="see-also"></a><span data-ttu-id="d7c7c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7c7c-128">See Also</span></span>
