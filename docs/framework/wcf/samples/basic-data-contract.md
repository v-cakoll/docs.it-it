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
# <a name="basic-data-contract"></a>Contratto dati di base

In questo esempio viene illustrato come implementare un contratto dati. I contratti dati consentono di passare dati strutturati a e da i servizi. Questo esempio è basato sul [Introduzione](getting-started-sample.md) ma usa numeri complessi anziché tipi numerici di base.

In questo esempio, il servizio è ospitato da Internet Information Services (IIS) e il client è un'applicazione console (.exe).

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

 Il contratto di servizio per questo servizio utilizza numeri complessi, come illustrato nell'esempio di codice seguente.

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

 Gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> sono stati applicati alla definizione della classe `ComplexNumber` per indicare quali campi della classe possono passare nella rete tra il client e il servizio, come illustrato nell'esempio di codice seguente.

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

L'implementazione del servizio calcola e restituisce il risultato appropriato, accettando e restituendo numeri di tipo `ComplexNumber`.

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

Anche l'implementazione del client utilizza numeri complessi. Il contratto di servizio e il contratto dati sono definiti nel file di origine generatedClient.cs, generato dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) dai metadati del servizio.

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

Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.

```console
Add(1 + 2i, 3 + 4i) = 4 + 6i
Subtract(1 + 2i, 3 + 4i) = -2 + -2i
Multiply(2 + 3i, 4 + 7i) = -13 + 26i
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 41i

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

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
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\Basic`
