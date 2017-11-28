---
title: 'Procedura: creare un servizio che richiede sessioni'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2e238598ccd33d9e6e77a2d09ea3b19fdefcefbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-service-that-requires-sessions"></a>Procedura: creare un servizio che richiede sessioni
Le sessioni creano un stato condiviso tra due o più endpoint che abilita funzionalità utili quali i callback, la sicurezza multihop e le associazioni tra istanze di client e servizi. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]le sessioni in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] applicazioni, vedere [utilizzando le sessioni](../../../../docs/framework/wcf/using-sessions.md).  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a>Per specificare che un contratto richiede l'associazione per supportare sessioni  
  
1.  Creare un contratto di servizio con almeno un'operazione. Per un esempio di come creare un contratto di servizio, vedere [procedura: definire un contratto di servizio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).  
  
2.  Modificare la classe <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> che dichiara il contratto impostando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> su uno dei seguenti elementi:  
  
    -   <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>, se questo contratto deve essere eseguito all'interno di una sessione.  
  
    -   <xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType>, se questo contratto può essere eseguito all'interno di una sessione.  
  
    -   <xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType>, se questo contratto non deve essere eseguito all'interno di una sessione.  
  
3.  Configurare l'endpoint del servizio per l'utilizzo di un'associazione che supporti sessioni. Nell'esempio di configurazione seguente viene illustrato l'utilizzo di <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, che supporta una sessione di WS`-`ReliableMessaging.  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]   
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come specificare un requisito di sessione a livello di contratto e utilizzare un file di configurazione per supportare tale requisito con l'associazione <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>.  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)] 
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]      
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]     
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>  
 <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
