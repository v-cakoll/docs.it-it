---
title: "Procedura: Controllare l'istanza del servizio"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
ms.openlocfilehash: e8efbc5a3dec5f60dbefc8f6dc377d97b29b7653
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699617"
---
# <a name="how-to-control-service-instancing"></a>Procedura: Controllare l'istanza del servizio
L'impostazione della modalità di istanza di un servizio consente di specificare quando vengono creati una classe <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> e il relativo oggetto servizio definito dall'utente associato. Per un elenco delle modalità possibili, vedere l'enumerazione <xref:System.ServiceModel.InstanceContextMode>. Per altre informazioni sui comportamenti, vedere [configurazione ed estensione del Runtime dei comportamenti](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md). Per alcuni esempi funzionanti, vedere [comportamenti](../../../../docs/framework/wcf/samples/behaviors.md).  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a>Per controllare la durata dell'istanza del servizio tramite codice  
  
1. Applicare la classe <xref:System.ServiceModel.ServiceBehaviorAttribute> alla classe di servizi.  
  
2. Impostare la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> su uno dei valori seguenti: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession> o <xref:System.ServiceModel.InstanceContextMode.Single>.  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente, la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> dell'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute> viene impostata su <xref:System.ServiceModel.InstanceContextMode.PerCall>.  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
- <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>
- <xref:System.ServiceModel.InstanceContextMode>
- [Servizio: Esempi di comportamenti](../samples/behaviors.md)
