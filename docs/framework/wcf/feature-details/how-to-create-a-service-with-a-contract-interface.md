---
title: "Procedura: creare un servizio con un'interfaccia di contratto"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
ms.openlocfilehash: c7d4bce174790b97db6b95aa5d15af455f261f82
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597163"
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a>Procedura: creare un servizio con un'interfaccia di contratto
Il modo migliore per creare un contratto di Windows Communication Foundation (WCF) consiste nell'usare un'interfaccia. Questo contratto specifica la raccolta e la struttura dei messaggi necessari per accedere alle operazioni offerte dal servizio. Questa interfaccia definisce i tipi di input e output applicando la classe <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia e la classe <xref:System.ServiceModel.OperationContractAttribute> ai metodi che si desidera esporre.  
  
 Per ulteriori informazioni sui contratti di servizio, vedere [progettazione di contratti di servizio](../designing-service-contracts.md).  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a>Creazione di un contratto WCF con un'interfaccia  
  
1. Creare una nuova interfaccia usando Visual Basic, C# o qualsiasi altro linguaggio Common Language Runtime.  
  
2. Applicare la classe <xref:System.ServiceModel.ServiceContractAttribute> all'interfaccia.  
  
3. Definire i metodi nell'interfaccia.  
  
4. Applicare la <xref:System.ServiceModel.OperationContractAttribute> classe a ogni metodo che deve essere esposto come parte del contratto WCF pubblico.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrata un'interfaccia che definisce un contratto di servizio.  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 I metodi a cui è applicata la classe <xref:System.ServiceModel.OperationContractAttribute> usano per impostazione predefinita un modello di messaggio request/reply. Per altre informazioni su questo modello di messaggio, vedere [procedura: creare un contratto request/reply](how-to-create-a-request-reply-contract.md). È anche possibile creare e utilizzare altri modelli di messaggio impostando proprietà dell'attributo. Per altri esempi, vedere [procedura: creare un contratto unidirezionale](how-to-create-a-one-way-contract.md) e [procedura: creare un contratto duplex](how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
