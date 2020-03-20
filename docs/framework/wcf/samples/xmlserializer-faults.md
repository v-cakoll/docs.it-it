---
title: Errori di XmlSerializer
ms.date: 03/30/2017
ms.assetid: c6b80f14-64f4-4162-ae76-71664cf42fd3
ms.openlocfilehash: adb14fdb45aa71bbaf4585cbfba55059df7cddf7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183158"
---
# <a name="xmlserializer-faults"></a><span data-ttu-id="e1170-102">Errori di XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="e1170-102">XmlSerializer Faults</span></span>
<span data-ttu-id="e1170-103">Nell'esempio di contratto di errore <xref:System.Xml.Serialization.XmlSerializer> viene illustrato come comunicare informazioni sugli errori da un servizio a un client usando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="e1170-103">The <xref:System.Xml.Serialization.XmlSerializer> fault contract sample demonstrates how to communicate error information from a service to a client using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="e1170-104">L'esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md), con codice aggiuntivo aggiunto al servizio per convertire un'eccezione interna in un errore.</span><span class="sxs-lookup"><span data-stu-id="e1170-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), with some additional code added to the service to convert an internal exception to a fault.</span></span> <span data-ttu-id="e1170-105">Il client tenta di eseguire una divisione per zero per imporre una condizione di errore al servizio.</span><span class="sxs-lookup"><span data-stu-id="e1170-105">The client attempts to perform division by zero to force an error condition on the service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1170-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e1170-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e1170-107">Il contratto della calcolatrice è stato modificato per includere un <xref:System.ServiceModel.FaultContractAttribute>, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e1170-107">The calculator contract has been modified to include a <xref:System.ServiceModel.FaultContractAttribute> as shown in the following sample code.</span></span> <span data-ttu-id="e1170-108"><xref:System.ServiceModel.XmlSerializerFormatAttribute> viene inoltre usato per abilitare la serializzazione usando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="e1170-108">Also, the <xref:System.ServiceModel.XmlSerializerFormatAttribute> is used to enable serialization using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="e1170-109">La proprietà <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A> è impostata su `true` su questo attributo, che indica al serializzatore di usare <xref:System.Xml.Serialization.XmlSerializer> per la lettura e la scrittura degli errori.</span><span class="sxs-lookup"><span data-stu-id="e1170-109">The <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A> property is set to `true` on this attribute, which instructs the serializer to use the <xref:System.Xml.Serialization.XmlSerializer> for reading and writing faults.</span></span>  
  
```csharp
[XmlSerializerFormat(SupportFaults=true)]  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
  
    [OperationContract]  
    int Subtract(int n1, int n2);  
  
    [OperationContract]  
    int Multiply(int n1, int n2);  
  
    [OperationContract]  
    [FaultContract(typeof(MathFault))]  
    int Divide(int n1, int n2);  
}  
```  
  
 <span data-ttu-id="e1170-110">Quando si genera codice per il proxy client, è necessario applicare il flag **/UseSerializerForFaults** allo strumento [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e1170-110">When generating code for the client proxy, you must apply the **/UseSerializerForFaults** flag to [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e1170-111">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="e1170-111">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e1170-112">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e1170-112">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="e1170-113">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e1170-113">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="e1170-114">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e1170-114">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e1170-115">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="e1170-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e1170-116">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="e1170-116">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e1170-117">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e1170-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e1170-118">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="e1170-118">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\XmlSerializerFaults`  
  
## <a name="see-also"></a><span data-ttu-id="e1170-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1170-119">See also</span></span>

- <xref:System.ServiceModel.XmlSerializerFormatAttribute>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A>
