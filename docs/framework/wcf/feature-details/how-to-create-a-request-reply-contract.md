---
title: 'Procedura: Creare un contratto Request/Reply'
ms.date: 03/30/2017
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
ms.openlocfilehash: 7a446db49dcc6a12b900292f1b19c9973835f2c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000987"
---
# <a name="how-to-create-a-request-reply-contract"></a>Procedura: Creare un contratto Request/Reply
Un contratto di tipo request/reply specifica un metodo che restituisce una risposta La replica deve essere inviata e correlata alla richiesta in base ai termini di questo contratto. Anche se il metodo non restituisce alcuna risposta (`void` in C# o `Sub` in Visual Basic), nell'infrastruttura viene creato e inviato un messaggio vuoto al chiamante. Per impedire l'invio di un messaggio di risposta vuoto, utilizzare un contratto unidirezionale per l'operazione.  
  
### <a name="to-create-a-request-reply-contract"></a>Per creare un contratto request/reply  
  
1. Creare un'interfaccia nel linguaggio di programmazione desiderato.  
  
2. Applicare l'attributo <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia.  
  
3. Applicare l'attributo <xref:System.ServiceModel.OperationContractAttribute> a ciascun metodo che i client possono richiamare.  
  
4. Facoltativo. Impostare il valore della proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> su `true` per impedire l'invio di un messaggio di risposta vuoto. Per impostazione predefinita, tutte le operazioni sono contratti di tipo request/reply.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è definito un contratto per un servizio calcolatrice che fornisce metodi `Add` e `Subtract`. Il metodo `Multiply` privato non fa parte del contratto perché non è contrassegnato dalla classe <xref:System.ServiceModel.OperationContractAttribute> e quindi non è accessibile ai client.  
  
```csharp
using System.ServiceModel;

[ServiceContract]
public interface ICalculator
{
    [OperationContract]
    // It would be equivalent to write explicitly:
    // [OperationContract(IsOneWay=false)]
    int Add(int a, int b);
    
    [OperationContract]
    int Subtract(int a, int b);
    
    int Multiply(int a, int b)
}
```
  
- Per altre informazioni su come specificare contratti di operazione, vedere la <xref:System.ServiceModel.OperationContractAttribute> classi e <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> proprietà.  
  
- L'applicazione degli attributi <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.OperationContractAttribute> determina la generazione automatica delle definizioni del contratto di servizio in un documento del linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language) dopo la distribuzione del servizio. Il documento viene scaricato aggiungendo l'elemento `?wsdl` all'indirizzo di base HTTP per il servizio, Ad esempio, `http://microsoft/CalculatorService?wsdl`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.OperationContractAttribute>
- [Progettazione dei contratti di servizio](../../../../docs/framework/wcf/designing-service-contracts.md)
- [Procedura: Creare un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
