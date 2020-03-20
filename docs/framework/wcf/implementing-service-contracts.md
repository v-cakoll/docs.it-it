---
title: Implementazione dei contratti di servizio
ms.date: 03/30/2017
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
ms.openlocfilehash: aefe146a8941d98d7d9138e4ece83c330c967034
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183997"
---
# <a name="implementing-service-contracts"></a>Implementazione dei contratti di servizio
Un servizio è una classe che espone le funzionalità disponibili per i client a uno o più endpoint. Per creare un servizio, scrivere una classe che implementa un contratto Windows Communication Foundation (WCF). Questa operazione può essere eseguita in due modi. È possibile definire il contratto separatamente come un'interfaccia e quindi creare una classe che implementi tale interfaccia. In alternativa, è possibile creare direttamente la classe e il contratto posizionando l'attributo <xref:System.ServiceModel.ServiceContractAttribute> sulla classe e l'attributo <xref:System.ServiceModel.OperationContractAttribute> sui metodi disponibili per i client del servizio.  
  
## <a name="creating-a-service-class"></a>Creazione di una classe di servizio  
 Nell'esempio seguente viene illustrato un servizio che implementa un contratto `IMath` definito separatamente.  
  
```csharp  
// Define the IMath contract.  
[ServiceContract]  
public interface IMath  
{  
    [OperationContract]
    double Add(double A, double B);  
  
    [OperationContract]  
    double Multiply (double A, double B);  
}  
  
// Implement the IMath contract in the MathService class.  
public class MathService : IMath  
{  
    public double Add (double A, double B) { return A + B; }  
    public double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 In alternativa, un servizio può esporre direttamente un contratto. Nell'esempio seguente viene illustrata una classe di servizio che definisce e implementa un contratto `MathService`.  
  
```csharp  
// Define the MathService contract directly on the service class.  
[ServiceContract]  
class MathService  
{  
    [OperationContract]  
    public double Add(double A, double B) { return A + B; }  
    [OperationContract]  
    private double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 Si noti che i servizi precedenti espongono contratti diversi perché i nomi di contratto sono diversi. Nel primo caso, il contratto esposto è denominato "`IMath`" mentre nel secondo caso il contratto è denominato "`MathService`".  
  
 È possibile impostare alcuni aspetti a livello del servizio e dell'implementazione dell'operazione, ad esempio la concorrenza e la creazione di istanze. Per ulteriori informazioni, vedere [Progettazione e implementazione di servizi](designing-and-implementing-services.md).  
  
 Dopo avere implementato un contratto di servizio, è necessario creare uno o più endpoint per il servizio. Per ulteriori informazioni, vedere [Cenni preliminari sulla creazione di endpoint.](endpoint-creation-overview.md) Per ulteriori informazioni su come eseguire un servizio, vedere [Servizi di hosting](hosting-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Progettazione e implementazione di servizi](designing-and-implementing-services.md)
- [Procedura: creare un servizio con una classe Contract](./feature-details/how-to-create-a-wcf-contract-with-a-class.md)
- [Procedura: creare un servizio con un'interfaccia di contratto](./feature-details/how-to-create-a-service-with-a-contract-interface.md)
- [Specifica del comportamento in fase di esecuzione del servizio](specifying-service-run-time-behavior.md)
