---
title: "Procedura: Creare un servizio con un'interfaccia di contratto"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
ms.openlocfilehash: 0aa5429d771aeda0b392b89ec4cc1a07de30973f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772895"
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a>Procedura: Creare un servizio con un'interfaccia di contratto
Il modo migliore per creare un contratto Windows Communication Foundation (WCF) consiste nell'usare un'interfaccia. Questo contratto specifica la raccolta e la struttura dei messaggi necessari per accedere alle operazioni offerte dal servizio. Questa interfaccia definisce i tipi di input e output applicando la classe <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia e la classe <xref:System.ServiceModel.OperationContractAttribute> ai metodi che si desidera esporre.  
  
 Per altre informazioni sui contratti di servizio, vedere [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a>Creazione di un contratto WCF con un'interfaccia  
  
1. Creare una nuova interfaccia utilizzando Visual Basic, C#, o qualsiasi altro linguaggio common language runtime.  
  
2. Applicare la classe <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia.  
  
3. Definire i metodi nell'interfaccia.  
  
4. Applicare il <xref:System.ServiceModel.OperationContractAttribute> classe a ogni metodo che deve essere esposto come parte del contratto pubblico di WCF.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrata un'interfaccia che definisce un contratto di servizio.  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 I metodi a cui è applicata la classe <xref:System.ServiceModel.OperationContractAttribute> usano per impostazione predefinita un modello di messaggio request/reply. Per altre informazioni su questo modello di messaggio, vedere [come: Creare un contratto Request / Reply](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). È anche possibile creare e utilizzare altri modelli di messaggio impostando proprietà dell'attributo. Per altri esempi, vedere [Procedura: Creare un contratto unidirezionale](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) e [come: Creare un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
