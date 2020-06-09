---
title: 'Procedura: creare un contratto Windows Communication Foundation con una classe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 0be2400ef3da5f0bbc218032ecd69af23f82cabd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597137"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Procedura: creare un contratto Windows Communication Foundation con una classe
Il modo migliore per creare un contratto di Windows Communication Foundation (WCF) consiste nell'usare un'interfaccia. Per altre informazioni, vedere [procedura: definire un contratto di servizio](../how-to-define-a-wcf-service-contract.md). Un'alternativa, illustrata qui, consiste nel creare una classe e quindi nell'applicare l'attributo <xref:System.ServiceModel.ServiceContractAttribute> direttamente alla classe e l'attributo <xref:System.ServiceModel.OperationContractAttribute> a ognuno dei metodi nella classe che fanno parte del contratto.  
  
> [!WARNING]
> `[ServiceContract]` e `[ServiceContractAttribute]` eseguono la stessa operazione. La stessa cosa è vera per `[OperationContract]` e `[OperationContractAttribute]` . In ogni caso, il primo è la sintassi abbreviata per quest'ultimo.  
  
 Per ulteriori informazioni sui contratti di servizio, vedere [progettazione di contratti di servizio](../designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Creazione di un contratto Windows Communication Foundation con una classe  
  
1. Creare una nuova classe utilizzando Visual Basic, C# o qualsiasi altro linguaggio Common Language Runtime.  
  
2. Applicare la classe <xref:System.ServiceModel.ServiceContractAttribute> alla classe.  
  
3. Creare metodi nella classe.  
  
4. Applicare la <xref:System.ServiceModel.OperationContractAttribute> classe a ogni metodo che deve essere esposto come parte del contratto WCF pubblico.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrata una classe che definisce un contratto di servizio.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 I metodi a cui è applicata la classe <xref:System.ServiceModel.OperationContractAttribute> usano per impostazione predefinita un modello di messaggio request/reply. Per altre informazioni su questo modello di messaggio, vedere [procedura: creare un contratto request/reply](how-to-create-a-request-reply-contract.md). È anche possibile creare e utilizzare altri modelli di messaggio impostando proprietà dell'attributo. Per altri esempi, vedere [procedura: creare un contratto unidirezionale](how-to-create-a-one-way-contract.md) e [procedura: creare un contratto duplex](how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
