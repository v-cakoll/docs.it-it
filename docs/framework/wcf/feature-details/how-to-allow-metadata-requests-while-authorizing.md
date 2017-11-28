---
title: 'Procedura: consentire richieste di metadati durante l''autorizzazione'
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
helpviewer_keywords: allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 103aba5118810064c1cafb7c82634ef000ced667
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a>Procedura: consentire richieste di metadati durante l'autorizzazione
Durante l'autorizzazione personalizzata potrebbe essere necessario consentire l'elaborazione di una richiesta di metadati. Nell'argomento seguente vengono dettagliati i passaggi necessari per convalidare tale richiesta.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] autorizzazione, vedere [autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).  
  
### <a name="to-allow-metadata-requests-during-authorization"></a>Per consentire richieste di metadati durante l'autorizzazione  
  
1.  Creare un'estensione della classe <xref:System.ServiceModel.ServiceAuthorizationManager>.  
  
2.  Eseguire l'override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>. Il metodo restituisce `true` o `false` rispettivamente se l'autorizzazione è consentita o meno. Le informazioni sulla procedura corrente sono reperibili in <xref:System.ServiceModel.OperationContext> passato come parametro al metodo.  
  
3.  Durante l'override controllare il nome del contratto, lo spazio dei nomi e l'azione, come indicato nell'esempio seguente. Se le condizioni sono valide, restituire `true.`.  
  
4.  Utilizzare il punto di estendibilità per utilizzare la classe. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Procedura: creare un gestore autorizzazioni personalizzato per un servizio](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [Autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [Gestione attestazioni e autorizzazioni con il modello di identità](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
