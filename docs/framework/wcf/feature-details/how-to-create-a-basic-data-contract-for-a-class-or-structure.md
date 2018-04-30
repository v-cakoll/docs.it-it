---
title: 'Procedura: creare un contratto dati di base per una classe o una struttura'
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
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 43fa318d2910fcd8b1d9ce75fc02d75bb39d4079
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a>Procedura: creare un contratto dati di base per una classe o una struttura
In questo argomento vengono illustrati i passaggi di base per creare un contratto dati usando una classe o una struttura. Per ulteriori informazioni sui contratti dati e modalità di utilizzo, vedere [utilizzando i contratti dati](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
 Per un'esercitazione che illustra i passaggi della creazione di base [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] servizio e client, vedere il [esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md). Per un'applicazione di esempio funzionante che è costituito da un servizio di base e un client, vedere [base contratto dati](../../../../docs/framework/wcf/samples/basic-data-contract.md).  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a>Per creare un contratto dati di base per una classe o una struttura  
  
1.  Dichiarare che il tipo è associato a un contratto dati applicando l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> alla classe. Si noti che tutti i tipi pubblici, inclusi quelli senza attributi, sono serializzabili. Tramite <xref:System.Runtime.Serialization.DataContractSerializer> viene dedotto un contratto dati se è assente l'attributo <xref:System.Runtime.Serialization.DataContractAttribute>. Per altre informazioni, vedere [tipi serializzabili](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
2.  Definire i membri (proprietà, campi o eventi) serializzati applicando l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> a ogni membro. Questi membri vengono definiti membri dati. Per impostazione predefinita, tutti i tipi pubblici sono serializzabili. Per altre informazioni, vedere [tipi serializzabili](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
    > [!NOTE]
    >  È possibile applicare l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> ai campi privati, per esporre i dati ad altri utenti. Assicurarsi che il membro non contenga dati riservati.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare un contratto dati per il tipo `Person` applicando gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> alla classe e ai relativi membri.  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [Uso di contratti di dati](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [Esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md)
