---
title: 'Procedura: creare un contratto dati di base per una classe o una struttura'
description: Seguire questo esempio per informazioni su come creare un contratto dati usando una classe o una struttura in WCF usando l'attributo DataContractAttribute.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
ms.openlocfilehash: a45fde58795947c3e46fa45750ae1a3faddd8849
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247169"
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a>Procedura: creare un contratto dati di base per una classe o una struttura
In questo argomento vengono illustrati i passaggi di base per creare un contratto dati usando una classe o una struttura. Per ulteriori informazioni sui contratti dati e sul relativo utilizzo, vedere [Using Data Contracts](using-data-contracts.md).  
  
 Per un'esercitazione che illustra i passaggi per la creazione di un servizio e di un client di base Windows Communication Foundation (WCF), vedere l' [esercitazione Introduzione](../getting-started-tutorial.md). Per un'applicazione di esempio funzionante costituita da un servizio e un client di base, vedere [contratto dati di base](../samples/basic-data-contract.md).  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a>Per creare un contratto dati di base per una classe o una struttura  
  
1. Dichiarare che il tipo è associato a un contratto dati applicando l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> alla classe. Si noti che tutti i tipi pubblici, inclusi quelli senza attributi, sono serializzabili. Tramite <xref:System.Runtime.Serialization.DataContractSerializer> viene dedotto un contratto dati se è assente l'attributo <xref:System.Runtime.Serialization.DataContractAttribute>. Per ulteriori informazioni, vedere [tipi serializzabili](serializable-types.md).  
  
2. Definire i membri (proprietà, campi o eventi) serializzati applicando l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> a ogni membro. Questi membri vengono definiti membri dati. Per impostazione predefinita, tutti i tipi pubblici sono serializzabili. Per ulteriori informazioni, vedere [tipi serializzabili](serializable-types.md).  
  
    > [!NOTE]
    > È possibile applicare l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> ai campi privati, per esporre i dati ad altri utenti. Assicurarsi che il membro non contenga dati riservati.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare un contratto dati per il tipo `Person` applicando gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> alla classe e ai relativi membri.  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [Using Data Contracts](using-data-contracts.md)
- [Esercitazione Introduzione](../getting-started-tutorial.md)
- [Per iniziare](../samples/getting-started-sample.md)
