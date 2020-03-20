---
title: 'Procedura: creare un servizio che richiede sessioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
ms.openlocfilehash: 495de5a926cfc0c5aab88337f5f33b991c49e71a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184985"
---
# <a name="how-to-create-a-service-that-requires-sessions"></a>Procedura: creare un servizio che richiede sessioni
Le sessioni creano un stato condiviso tra due o più endpoint che abilita funzionalità utili quali i callback, la sicurezza multihop e le associazioni tra istanze di client e servizi. Per ulteriori informazioni sulle sessioni nelle applicazioni Windows Communication Foundation (WCF), vedere [Utilizzo delle sessioni](../../../../docs/framework/wcf/using-sessions.md).  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a>Per specificare che un contratto richiede l'associazione per supportare sessioni  
  
1. Creare un contratto di servizio con almeno un'operazione. Per un esempio di creazione di un contratto di assistenza, vedere [Procedura: definire un contratto](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)di assistenza .  
  
2. Modificare la classe <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> che dichiara il contratto impostando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> su uno dei seguenti elementi:  
  
    - <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>, se questo contratto deve essere eseguito all'interno di una sessione.  
  
    - <xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType>, se questo contratto può essere eseguito all'interno di una sessione.  
  
    - <xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType>, se questo contratto non deve essere eseguito all'interno di una sessione.  
  
3. Configurare l'endpoint del servizio per l'utilizzo di un'associazione che supporti sessioni. Nell'esempio di configurazione seguente viene illustrato l'utilizzo di <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, che supporta una sessione di WS`-`ReliableMessaging.  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come specificare un requisito di sessione a livello di contratto e utilizzare un file di configurazione per supportare tale requisito con l'associazione <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>.  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)]
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
