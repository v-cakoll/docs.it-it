---
title: Supporto POCO
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: e94f6d9576ed96613d975a66c1965820002f94ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183420"
---
# <a name="poco-support"></a><span data-ttu-id="a1b3c-102">Supporto POCO</span><span class="sxs-lookup"><span data-stu-id="a1b3c-102">POCO Support</span></span>
<span data-ttu-id="a1b3c-103">In questo esempio viene illustrato il supporto di serializzazione per i tipi non contrassegnati, ovvero tipi ai quali non sono stati applicati attributi di serializzazione, definiti talvolta tipi di oggetto POCO (Plain Old CLR Object).</span><span class="sxs-lookup"><span data-stu-id="a1b3c-103">This sample demonstrates the serialization support for unmarked types; that is, types to which serialization attributes have not been applied, sometimes referred to as Plain Old CLR Object (POCO) types.</span></span> <span data-ttu-id="a1b3c-104">L'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> deduce un contratto dati per tutti i tipi pubblici non contrassegnati che dispongono di un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="a1b3c-104">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract for all public unmarked types that have a parameterless constructor.</span></span> <span data-ttu-id="a1b3c-105">I contratti dati consentono di passare dati strutturati a e da i servizi.</span><span class="sxs-lookup"><span data-stu-id="a1b3c-105">Data contracts allow you to pass structured data to and from services.</span></span> <span data-ttu-id="a1b3c-106">Per ulteriori informazioni sui tipi non [contrassegnati, vedere Tipi serializzabili](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="a1b3c-106">For more information about unmarked types, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
 <span data-ttu-id="a1b3c-107">Questo esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md), ma utilizza numeri complessi anziché tipi numerici primitivi.</span><span class="sxs-lookup"><span data-stu-id="a1b3c-107">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), but uses complex numbers instead of primitive numeric types.</span></span> <span data-ttu-id="a1b3c-108">È anche simile all'esempio [Basic Data Contract,](../../../../docs/framework/wcf/samples/basic-data-contract.md) ad eccezione del fatto che gli <xref:System.Runtime.Serialization.DataContractAttribute> attributi e <xref:System.Runtime.Serialization.DataMemberAttribute> non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="a1b3c-108">It is also similar to the [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) sample, except that the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes are not used.</span></span>  
  
 <span data-ttu-id="a1b3c-109">Il servizio è ospitato da Internet Information Services (IIS) e il client è un'applicazione console (con estensione exe).</span><span class="sxs-lookup"><span data-stu-id="a1b3c-109">The service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1b3c-110">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a1b3c-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="a1b3c-111">La classe `ComplexNumber` viene utilizzata in `ServiceContract`.</span><span class="sxs-lookup"><span data-stu-id="a1b3c-111">The `ComplexNumber` class is used in the `ServiceContract`.</span></span> <span data-ttu-id="a1b3c-112">Il tipo `ComplexNumber` non dispone degli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute>, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a1b3c-112">The `ComplexNumber` type does not have the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes, as shown in the following sample code.</span></span> <span data-ttu-id="a1b3c-113">Per impostazione predefinita, le proprietà e i campi pubblici vengono serializzati.</span><span class="sxs-lookup"><span data-stu-id="a1b3c-113">By default, all public properties and fields are serialized.</span></span>  
  
```csharp
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
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a1b3c-114">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="a1b3c-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a1b3c-115">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a1b3c-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="a1b3c-116">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a1b3c-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="a1b3c-117">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a1b3c-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a1b3c-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="a1b3c-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a1b3c-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a1b3c-119">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a1b3c-120">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a1b3c-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a1b3c-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="a1b3c-121">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a><span data-ttu-id="a1b3c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1b3c-122">See also</span></span>

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- [<span data-ttu-id="a1b3c-123">Tipi serializzabili</span><span class="sxs-lookup"><span data-stu-id="a1b3c-123">Serializable Types</span></span>](../../../../docs/framework/wcf/feature-details/serializable-types.md)
