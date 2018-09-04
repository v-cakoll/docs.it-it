---
title: Sessione
ms.date: 03/30/2017
helpviewer_keywords:
- Sessions
ms.assetid: 36e1db50-008c-4b32-8d09-b56e790b8417
ms.openlocfilehash: ce91adbb5156eef09221a76773e5a9551f0e8440
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517892"
---
# <a name="session"></a>Sessione
Nell'esempio della sessione viene illustrato come implementare un contratto che richiede una sessione. Una sessione fornisce il contesto per l'esecuzione di più operazioni. Ciò consente a un servizio di associare lo stato a una sessione specifica, in modo che le operazioni successive possano utilizzare lo stato di un'operazione precedente. In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md), che implementa un servizio di calcolatrice. Il contratto `ICalculator` è stato modificato per consentire l'esecuzione di un insieme di operazioni aritmetiche, mantenendo il risultato parziale. Questa funzionalità è definita dal contratto `ICalculatorSession`. Il servizio gestisce lo stato di un client mentre vengono chiamate più operazioni del servizio per eseguire un calcolo. Il client può recuperare il risultato corrente chiamando `Result()` e azzerare il risultato chiamando `Clear()`.  
  
 In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 L'impostazione di <xref:System.ServiceModel.SessionMode> del contratto su `Required` assicura che, quando il contratto viene esposto su una particolare associazione, l'associazione supporti le sessioni. Se l'associazione non supporta le sessioni viene generata un'eccezione. L'interfaccia `ICalculatorSession` è definita in modo che possono essere chiamate una o più operazioni, aspetto che modifica un risultato parziale, come illustrato dal codice di esempio seguente.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface ICalculatorSession  
{  
    [OperationContract(IsOneWay=true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 Il servizio utilizza un <xref:System.ServiceModel.InstanceContextMode> di <xref:System.ServiceModel.InstanceContextMode.PerSession> per associare un determinato contesto dell'istanza del servizio a ogni sessione in ingresso. Questo consente al servizio di gestire il risultato parziale per ogni sessione in una variabile membro locale.  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorSession  
{  
    double result = 0.0D;  
  
    public void Clear()  
    {  result = 0.0D; }  
  
    public void AddTo(double n)  
    {  result += n;   }  
  
    public void SubtractFrom(double n)  
    {  result -= n;   }  
  
    public void MultiplyBy(double n)  
    {  result *= n;   }  
  
    public void DivideBy(double n)  
    {  result /= n;   }  
  
    public double Result()  
    {  return result; }  
}  
```  
  
 Quando si esegue l'esempio, il client esegue molte richieste al server e richiede il risultato, che viene quindi visualizzato nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.  
  
```  
(((0 + 100) - 50) * 17.65) / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Session`  
  
## <a name="see-also"></a>Vedere anche
