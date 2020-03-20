---
title: Contratto di errore
ms.date: 03/30/2017
ms.assetid: b31b140e-dc3b-408b-b3c7-10b6fe769725
ms.openlocfilehash: c8e93f73d150132c9d6750b81ba2ade944808d40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183658"
---
# <a name="fault-contract"></a>Contratto di errore
Nell'esempio di contratto di errore viene illustrato come comunicare informazioni relative all'errore da un servizio a un client. L'esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md), con codice aggiuntivo aggiunto al servizio per convertire un'eccezione interna in un errore. Il client tenta di eseguire una divisione per zero per imporre una condizione di errore al servizio.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Il contratto della calcolatrice è stato modificato per includere un <xref:System.ServiceModel.FaultContractAttribute>, come illustrato nell'esempio di codice seguente.  
  
```csharp
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
  
 L'attributo <xref:System.ServiceModel.FaultContractAttribute> indica che l'operazione `Divide` può restituire un errore di tipo `MathFault`. Un errore può essere di qualsiasi tipo che può essere serializzato. In questo caso, `MathFault` è un contratto dati, come segue:  
  
```csharp
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class MathFault  
{
    private string operation;  
    private string problemType;  
  
    [DataMember]  
    public string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [DataMember]
    public string ProblemType  
    {  
        get { return problemType; }  
        set { problemType = value; }  
    }  
}  
```  
  
 Il metodo `Divide` genera un'eccezione <xref:System.ServiceModel.FaultException%601> quando si verifica un'eccezione di divisione per zero, come illustrato nell'esempio di codice seguente. Questa eccezione comporta che un errore venga inviato al client.  
  
```csharp
public int Divide(int n1, int n2)  
{  
    try  
    {  
        return n1 / n2;  
    }  
    catch (DivideByZeroException)  
    {  
        MathFault mf = new MathFault();  
        mf.operation = "division";  
        mf.problemType = "divide by zero";  
        throw new FaultException<MathFault>(mf);  
    }  
}  
```  
  
 Il codice client forza un errore richiedendo una divisione per zero. Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Viene visualizzata la divisione per zero segnalata come un errore. Premere INVIO nella finestra del client per arrestare il client.  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
FaultException<MathFault>: Math fault while doing division. Problem: divide by zero  
  
Press <ENTER> to terminate client.  
```  
  
 Il client esegue questa operazione rilevando l'eccezione `FaultException<MathFault>` appropriata:  
  
```csharp
catch (FaultException<MathFault> e)  
{  
    Console.WriteLine("FaultException<MathFault>: Math fault while doing " + e.Detail.operation + ". Problem: " + e.Detail.problemType);  
    client.Abort();  
}  
```  
  
 Per impostazione predefinita, i dettagli delle eccezioni impreviste non vengono inviati al client per evitare che i dettagli dell'implementazione del servizio escano dal limite protetto del servizio. `FaultContract` rappresenta un modo per descrivere gli errori di un contratto e contrassegnare certi tipi di eccezioni come appropriati per essere trasmessi al client. `FaultException<T>` rappresenta il meccanismo in fase di esecuzione per l'invio di errori agli utenti.  
  
 È anche utile per visualizzare i dettagli interni di un errore del servizio durante l'esecuzione del debug. Per disattivare il comportamento protetto precedentemente descritto, è possibile indicare che i dettagli di ogni eccezione non gestita del server devono essere inclusi nell'errore inviato al client. Questa operazione viene eseguita impostando <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A> su `true`. È possibile impostarlo nel codice o nella configurazione, come illustrato nell'esempio seguente.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="True" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Inoltre, il comportamento deve essere associato `behaviorConfiguration` al servizio impostando l'attributo del servizio nel file di configurazione su "CalculatorServiceBehavior".  
  
 Per intercettare questi errori nel client, è necessario intercettare l'oggetto <xref:System.ServiceModel.FaultException> non generico.  
  
 Questo comportamento deve essere usato solo a scopo di debug e non deve essere mai attivato in produzione.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Faults`  
