---
title: "Procedura: creare un servizio con un'interfaccia di contratto"
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b4af593edd355ed89da8c5b2c79a4c029b966fe4
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a>Procedura: creare un servizio con un'interfaccia di contratto
La modalità preferita per creare un contratto [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è tramite un'interfaccia. Questo contratto specifica la raccolta e la struttura dei messaggi necessari per accedere alle operazioni offerte dal servizio. Questa interfaccia definisce i tipi di input e output applicando la classe <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia e la classe <xref:System.ServiceModel.OperationContractAttribute> ai metodi che si desidera esporre.  
  
 Per ulteriori informazioni sui contratti di servizio, vedere [progettazione contratti di servizio](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a>Creazione di un contratto WCF con un'interfaccia  
  
1.  Creare una nuova interfaccia utilizzando Visual Basic, c# o qualsiasi altro linguaggio common language runtime.  
  
2.  Applicare la classe <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia.  
  
3.  Definire i metodi nell'interfaccia.  
  
4.  Applicare la classe <xref:System.ServiceModel.OperationContractAttribute> a ogni metodo che deve essere esposto come parte del contratto [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pubblico.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrata un'interfaccia che definisce un contratto di servizio.  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 I metodi a cui è applicata la classe <xref:System.ServiceModel.OperationContractAttribute> utilizzano per impostazione predefinita un modello di messaggio request/reply. Per ulteriori informazioni su questo modello di messaggio, vedere [procedura: creare un contratto Request/Reply](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). È anche possibile creare e usare altri modelli di messaggio impostando proprietà dell'attributo. Per ulteriori esempi, vedere [procedura: creare un contratto unidirezionale](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) e [procedura: creare un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
