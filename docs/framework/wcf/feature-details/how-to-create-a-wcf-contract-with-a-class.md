---
title: 'Procedura: creare un contratto Windows Communication Foundation con una classe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 296f500532040aaebf0f6d7d37a7a9aae99a3451
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491813"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Procedura: creare un contratto Windows Communication Foundation con una classe
La strategia ottimale di creazione di un contratto Windows Communication Foundation (WCF) consiste nell'utilizzare un'interfaccia. Per altre informazioni, vedere [procedura: definire un contratto di servizio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md). Un'alternativa, illustrata qui, consiste nel creare una classe e quindi nell'applicare l'attributo <xref:System.ServiceModel.ServiceContractAttribute> direttamente alla classe e l'attributo <xref:System.ServiceModel.OperationContractAttribute> a ognuno dei metodi nella classe che fanno parte del contratto.  
  
> [!WARNING]
>  `[ServiceContract]` e `[ServiceContractAttribute]` eseguono la stessa operazione. La stessa situazione è valida per `[OperationContract]` e `[OperationContractAttribute]`. In ogni caso il primo è l'abbreviazione del secondo.  
  
 Per ulteriori informazioni sui contratti di servizio, vedere [progettazione contratti di servizio](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Creazione di un contratto Windows Communication Foundation con una classe  
  
1.  Creare una nuova classe utilizzando Visual Basic, c# o qualsiasi altro linguaggio common language runtime.  
  
2.  Applicare la classe <xref:System.ServiceModel.ServiceContractAttribute> alla classe.  
  
3.  Creare metodi nella classe.  
  
4.  Applicare il <xref:System.ServiceModel.OperationContractAttribute> (classe) a ogni metodo che deve essere esposto come parte del contratto WCF pubblico.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrata una classe che definisce un contratto di servizio.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 I metodi a cui è applicata la classe <xref:System.ServiceModel.OperationContractAttribute> utilizzano per impostazione predefinita un modello di messaggio request/reply. Per ulteriori informazioni su questo modello di messaggio, vedere [procedura: creare un contratto Request/Reply](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). È anche possibile creare e usare altri modelli di messaggio impostando proprietà dell'attributo. Per ulteriori esempi, vedere [procedura: creare un contratto unidirezionale](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) e [procedura: creare un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
