---
title: Contratto dati di base
ms.date: 03/30/2017
helpviewer_keywords:
- Data Contract
ms.assetid: b124e9e0-cb73-4ae0-b9c3-e6cdf5eced98
ms.openlocfilehash: 66df6a1d7c2df17e79925490644891c0a536b1cd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585493"
---
# <a name="basic-data-contract"></a><span data-ttu-id="065e1-102">Contratto dati di base</span><span class="sxs-lookup"><span data-stu-id="065e1-102">Basic Data Contract</span></span>

<span data-ttu-id="065e1-103">In questo esempio viene illustrato come implementare un contratto dati.</span><span class="sxs-lookup"><span data-stu-id="065e1-103">This sample demonstrates how to implement a data contract.</span></span> <span data-ttu-id="065e1-104">I contratti dati consentono di passare dati strutturati a e da i servizi.</span><span class="sxs-lookup"><span data-stu-id="065e1-104">Data contracts allow you to pass structured data to and from services.</span></span> <span data-ttu-id="065e1-105">Questo esempio è basato sul [Introduzione](getting-started-sample.md) ma usa numeri complessi anziché tipi numerici di base.</span><span class="sxs-lookup"><span data-stu-id="065e1-105">This sample is based on the [Getting Started](getting-started-sample.md) but uses complex numbers instead of basic numeric types.</span></span>

<span data-ttu-id="065e1-106">In questo esempio, il servizio è ospitato da Internet Information Services (IIS) e il client è un'applicazione console (.exe).</span><span class="sxs-lookup"><span data-stu-id="065e1-106">In this sample, the service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>

> [!NOTE]
> <span data-ttu-id="065e1-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="065e1-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="065e1-108">Il contratto di servizio per questo servizio utilizza numeri complessi, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="065e1-108">The service contract for this service uses complex numbers, as shown in the following sample code.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
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

 <span data-ttu-id="065e1-109">Gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> sono stati applicati alla definizione della classe `ComplexNumber` per indicare quali campi della classe possono passare nella rete tra il client e il servizio, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="065e1-109">The <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes have been applied to the definition of the `ComplexNumber` class to indicate which fields of the class can be passed over the wire between the client and the service, as shown in the following sample code.</span></span>

```csharp
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public class ComplexNumber
{
    [DataMember]
    public double Real = 0.0D;
    [DataMember]
    public double Imaginary = 0.0D;

    public ComplexNumber(double real, double imaginary)
    {
        this.Real = real;
        this.Imaginary = imaginary;
    }
}
```

<span data-ttu-id="065e1-110">L'implementazione del servizio calcola e restituisce il risultato appropriato, accettando e restituendo numeri di tipo `ComplexNumber`.</span><span class="sxs-lookup"><span data-stu-id="065e1-110">The service implementation calculates and returns the appropriate result, accepting and returning numbers of the `ComplexNumber` type.</span></span>

```csharp
// This is the service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public ComplexNumber Add(ComplexNumber n1, ComplexNumber n2)
    {
        return new ComplexNumber(n1.Real + n2.Real, n1.Imaginary +
                                                      n2.Imaginary);
    }

    public ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2)
    {
        return new ComplexNumber(n1.Real - n2.Real, n1.Imaginary -
                                                     n2.Imaginary);
    }
    public ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2)
    {
        double real1 = n1.Real * n2.Real;
        double imaginary1 = n1.Real * n2.Imaginary;
        double imaginary2 = n2.Real * n1.Imaginary;
        double real2 = n1.Imaginary * n2.Imaginary * -1;
        return new ComplexNumber(real1 + real2, imaginary1 +
                                                 imaginary2);
    }

    public ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2)
    {
         ComplexNumber conjugate =
              new ComplexNumber(n2.Real, -1*n2.Imaginary);
         ComplexNumber numerator = Multiply(n1, conjugate);
         ComplexNumber denominator = Multiply(n2, conjugate);
         return new ComplexNumber(numerator.Real / denominator.Real,
                                               numerator.Imaginary);
    }
}
```

<span data-ttu-id="065e1-111">Anche l'implementazione del client utilizza numeri complessi.</span><span class="sxs-lookup"><span data-stu-id="065e1-111">The client implementation also uses complex numbers.</span></span> <span data-ttu-id="065e1-112">Il contratto di servizio e il contratto dati sono definiti nel file di origine generatedClient.cs, generato dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) dai metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="065e1-112">Both the service contract and the data contract are defined in the source file generatedClient.cs, which is generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) from service metadata.</span></span>

```csharp
// Create a client.
DataContractCalculatorClient client = new DataContractCalculatorClient();
// Call the Add service operation.
ComplexNumber value1 = new ComplexNumber()
                    {
                        Real = 1,
                        Imaginary = 2
                    };
ComplexNumber value2 = new ComplexNumber()
                    {
                        Real = 3,
                        Imaginary = 4
                    };
ComplexNumber result = proxy.Add(value1, value2);
Console.WriteLine("Add({0} + {1}i, {2} + {3}i) = {4} + {5}i",
      value1.Real, value1.Imaginary, value2.Real, value2.Imaginary,
      result.Real, result.Imaginary);
    …
}
```

<span data-ttu-id="065e1-113">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="065e1-113">When you run the sample, the requests and responses of the operation are displayed in the client console window.</span></span> <span data-ttu-id="065e1-114">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="065e1-114">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(1 + 2i, 3 + 4i) = 4 + 6i
Subtract(1 + 2i, 3 + 4i) = -2 + -2i
Multiply(2 + 3i, 4 + 7i) = -13 + 26i
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 41i

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="065e1-115">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="065e1-115">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="065e1-116">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="065e1-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="065e1-117">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="065e1-117">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="065e1-118">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="065e1-118">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="065e1-119">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="065e1-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="065e1-120">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="065e1-120">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="065e1-121">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="065e1-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="065e1-122">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="065e1-122">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\Basic`
