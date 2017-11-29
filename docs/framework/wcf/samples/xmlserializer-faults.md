---
title: Errori di XmlSerializer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6b80f14-64f4-4162-ae76-71664cf42fd3
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 39a01bafb5ce07268b43c1f58a96be0813237891
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xmlserializer-faults"></a><span data-ttu-id="2fccc-102">Errori di XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="2fccc-102">XmlSerializer Faults</span></span>
<span data-ttu-id="2fccc-103">Nell'esempio di contratto di errore <xref:System.Xml.Serialization.XmlSerializer> viene illustrato come comunicare informazioni sugli errori da un servizio a un client usando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="2fccc-103">The <xref:System.Xml.Serialization.XmlSerializer> fault contract sample demonstrates how to communicate error information from a service to a client using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="2fccc-104">L'esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md), con altro codice aggiunto al servizio per convertire un errore di un'eccezione interna.</span><span class="sxs-lookup"><span data-stu-id="2fccc-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), with some additional code added to the service to convert an internal exception to a fault.</span></span> <span data-ttu-id="2fccc-105">Il client tenta di eseguire una divisione per zero per imporre una condizione di errore al servizio.</span><span class="sxs-lookup"><span data-stu-id="2fccc-105">The client attempts to perform division by zero to force an error condition on the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2fccc-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2fccc-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="2fccc-107">Il contratto della calcolatrice è stato modificato per includere un <xref:System.ServiceModel.FaultContractAttribute>, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2fccc-107">The calculator contract has been modified to include a <xref:System.ServiceModel.FaultContractAttribute> as shown in the following sample code.</span></span> <span data-ttu-id="2fccc-108"><xref:System.ServiceModel.XmlSerializerFormatAttribute> viene inoltre usato per abilitare la serializzazione usando <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="2fccc-108">Also, the <xref:System.ServiceModel.XmlSerializerFormatAttribute> is used to enable serialization using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="2fccc-109">La proprietà <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A> è impostata su `true` su questo attributo, che indica al serializzatore di usare <xref:System.Xml.Serialization.XmlSerializer> per la lettura e la scrittura degli errori.</span><span class="sxs-lookup"><span data-stu-id="2fccc-109">The <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A> property is set to `true` on this attribute, which instructs the serializer to use the <xref:System.Xml.Serialization.XmlSerializer> for reading and writing faults.</span></span>  
  
```  
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
  
 <span data-ttu-id="2fccc-110">Quando si genera codice per il proxy client, è necessario applicare il **/UseSerializerForFaults** flag [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="2fccc-110">When generating code for the client proxy, you must apply the **/UseSerializerForFaults** flag to [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2fccc-111">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="2fccc-111">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2fccc-112">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2fccc-112">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="2fccc-113">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2fccc-113">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="2fccc-114">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2fccc-114">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2fccc-115">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2fccc-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2fccc-116">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="2fccc-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2fccc-117">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2fccc-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2fccc-118">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="2fccc-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\XmlSerializerFaults`  
  
## <a name="see-also"></a><span data-ttu-id="2fccc-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fccc-119">See Also</span></span>  
 <xref:System.ServiceModel.XmlSerializerFormatAttribute>  
 <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A>
