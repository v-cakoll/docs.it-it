---
title: 'Procedura: creare un contratto request/reply'
ms.date: 03/30/2017
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
ms.openlocfilehash: 8a09c265c77edc584b591477e64314f1e76e332b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593438"
---
# <a name="how-to-create-a-request-reply-contract"></a>Procedura: creare un contratto request/reply
Un contratto di tipo request/reply specifica un metodo che restituisce una risposta La replica deve essere inviata e correlata alla richiesta in base ai termini di questo contratto. Anche se il metodo non restituisce alcuna risposta (`void` in C# o `Sub` in Visual Basic), nell'infrastruttura viene creato e inviato un messaggio vuoto al chiamante. Per impedire l'invio di un messaggio di risposta vuoto, utilizzare un contratto unidirezionale per l'operazione.  
  
### <a name="to-create-a-request-reply-contract"></a>Per creare un contratto request/reply  
  
1. Creare un'interfaccia nel linguaggio di programmazione desiderato.  
  
2. Applicare l'attributo <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia.  
  
3. Applicare l'attributo <xref:System.ServiceModel.OperationContractAttribute> a ciascun metodo che i client possono richiamare.  
  
4. Facoltativa. Impostare il valore della proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> su `true` per impedire l'invio di un messaggio di risposta vuoto. Per impostazione predefinita, tutte le operazioni sono contratti di tipo request/reply.  
  
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
  
- Per ulteriori informazioni su come specificare i contratti di operazione, vedere la <xref:System.ServiceModel.OperationContractAttribute> classe e la <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> Proprietà.  
  
- L'applicazione degli attributi <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.OperationContractAttribute> determina la generazione automatica delle definizioni del contratto di servizio in un documento del linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language) dopo la distribuzione del servizio. Il documento viene scaricato aggiungendo l'elemento `?wsdl` all'indirizzo di base HTTP per il servizio, Ad esempio, usare `http://microsoft/CalculatorService?wsdl`  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.OperationContractAttribute>
- [Progettazione dei contratti di servizio](../designing-service-contracts.md)
- [Procedura: creare un contratto duplex](how-to-create-a-duplex-contract.md)
