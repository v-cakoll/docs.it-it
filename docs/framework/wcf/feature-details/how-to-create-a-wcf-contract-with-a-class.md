---
title: 'Procedura: Creare un contratto di Windows Communication Foundation con una classe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 2cd757107d9f62ce749d98db1d4968c02a09c5d2
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988749"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Procedura: Creare un contratto di Windows Communication Foundation con una classe
Il modo migliore per creare un contratto di Windows Communication Foundation (WCF) consiste nell'usare un'interfaccia. Per altre informazioni, vedere [Procedura: Definire un contratto](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)di servizio. Un'alternativa, illustrata qui, consiste nel creare una classe e quindi nell'applicare l'attributo <xref:System.ServiceModel.ServiceContractAttribute> direttamente alla classe e l'attributo <xref:System.ServiceModel.OperationContractAttribute> a ognuno dei metodi nella classe che fanno parte del contratto.  
  
> [!WARNING]
> `[ServiceContract]` e `[ServiceContractAttribute]` eseguono la stessa operazione. La stessa cosa è vera per `[OperationContract]` e `[OperationContractAttribute]`. In ogni caso, il primo è la sintassi abbreviata per quest'ultimo.  
  
 Per ulteriori informazioni sui contratti di servizio, vedere [progettazione di contratti di servizio](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Creazione di un contratto Windows Communication Foundation con una classe  
  
1. Creare una nuova classe utilizzando Visual Basic, C#o qualsiasi altra lingua del Common Language Runtime.  
  
2. Applicare la classe <xref:System.ServiceModel.ServiceContractAttribute> alla classe.  
  
3. Creare metodi nella classe.  
  
4. Applicare la <xref:System.ServiceModel.OperationContractAttribute> classe a ogni metodo che deve essere esposto come parte del contratto WCF pubblico.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrata una classe che definisce un contratto di servizio.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 I metodi a cui è applicata la classe <xref:System.ServiceModel.OperationContractAttribute> usano per impostazione predefinita un modello di messaggio request/reply. Per ulteriori informazioni su questo modello di messaggio, [vedere Procedura: Creare un contratto](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)Request/Reply. È anche possibile creare e utilizzare altri modelli di messaggio impostando proprietà dell'attributo. Per altri esempi, vedere [Procedura: Creazione di un contratto](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) unidirezionale e [procedura: Creazione di un contratto](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)duplex.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
