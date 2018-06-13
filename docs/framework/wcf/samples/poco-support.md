---
title: Supporto POCO
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: ab95469afa53bd0b27efc451875d4912db74a45a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33501986"
---
# <a name="poco-support"></a><span data-ttu-id="f2260-102">Supporto POCO</span><span class="sxs-lookup"><span data-stu-id="f2260-102">POCO Support</span></span>
<span data-ttu-id="f2260-103">In questo esempio viene illustrato il supporto di serializzazione per i tipi non contrassegnati, ovvero tipi ai quali non sono stati applicati attributi di serializzazione, definiti talvolta tipi di oggetto POCO (Plain Old CLR Object).</span><span class="sxs-lookup"><span data-stu-id="f2260-103">This sample demonstrates the serialization support for unmarked types; that is, types to which serialization attributes have not been applied, sometimes referred to as Plain Old CLR Object (POCO) types.</span></span> <span data-ttu-id="f2260-104">Tramite <xref:System.Runtime.Serialization.DataContractSerializer> viene dedotto un contratto dati per tutti i tipi contrassegnati pubblici che dispongono di un costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f2260-104">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract for all public unmarked types that have a default constructor.</span></span> <span data-ttu-id="f2260-105">I contratti dati consentono di passare dati strutturati a e da i servizi.</span><span class="sxs-lookup"><span data-stu-id="f2260-105">Data contracts allow you to pass structured data to and from services.</span></span> <span data-ttu-id="f2260-106">Per ulteriori informazioni sui tipi non contrassegnati, vedere [tipi serializzabili](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="f2260-106">For more information about unmarked types, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
 <span data-ttu-id="f2260-107">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md), ma utilizza numeri complessi anziché i tipi numerici primitivi.</span><span class="sxs-lookup"><span data-stu-id="f2260-107">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), but uses complex numbers instead of primitive numeric types.</span></span> <span data-ttu-id="f2260-108">È anche simile al [base contratto dati](../../../../docs/framework/wcf/samples/basic-data-contract.md) di esempio, con la differenza che il <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> non vengono utilizzati gli attributi.</span><span class="sxs-lookup"><span data-stu-id="f2260-108">It is also similar to the [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) sample, except that the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes are not used.</span></span>  
  
 <span data-ttu-id="f2260-109">Il servizio è ospitato da Internet Information Services (IIS) e il client è un'applicazione console (con estensione exe).</span><span class="sxs-lookup"><span data-stu-id="f2260-109">The service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2260-110">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f2260-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="f2260-111">La classe `ComplexNumber` viene utilizzata in `ServiceContract`.</span><span class="sxs-lookup"><span data-stu-id="f2260-111">The `ComplexNumber` class is used in the `ServiceContract`.</span></span> <span data-ttu-id="f2260-112">Il tipo `ComplexNumber` non dispone degli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute>, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f2260-112">The `ComplexNumber` type does not have the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes, as shown in the following sample code.</span></span> <span data-ttu-id="f2260-113">Per impostazione predefinita, le proprietà e i campi pubblici vengono serializzati.</span><span class="sxs-lookup"><span data-stu-id="f2260-113">By default, all public properties and fields are serialized.</span></span>  
  
```  
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f2260-114">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="f2260-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f2260-115">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f2260-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="f2260-116">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f2260-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="f2260-117">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f2260-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f2260-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="f2260-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f2260-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="f2260-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f2260-120">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="f2260-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f2260-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="f2260-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a><span data-ttu-id="f2260-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2260-122">See Also</span></span>  
 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>  
 [<span data-ttu-id="f2260-123">Tipi serializzabili</span><span class="sxs-lookup"><span data-stu-id="f2260-123">Serializable Types</span></span>](../../../../docs/framework/wcf/feature-details/serializable-types.md)
