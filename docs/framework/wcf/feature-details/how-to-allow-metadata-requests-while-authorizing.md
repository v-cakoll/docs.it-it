---
title: "Procedura: consentire richieste di metadati durante l'autorizzazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
ms.openlocfilehash: 2f855080cf3ba4cee08470af77c52945e47a2ec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a>Procedura: consentire richieste di metadati durante l'autorizzazione
Durante l'autorizzazione personalizzata potrebbe essere necessario consentire l'elaborazione di una richiesta di metadati. Nell'argomento seguente vengono dettagliati i passaggi necessari per convalidare tale richiesta.  
  
 Per ulteriori informazioni sull'autorizzazione di Windows Communication Foundation (WCF), vedere [autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).  
  
### <a name="to-allow-metadata-requests-during-authorization"></a>Per consentire richieste di metadati durante l'autorizzazione  
  
1.  Creare un'estensione della classe <xref:System.ServiceModel.ServiceAuthorizationManager>.  
  
2.  Eseguire l'override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>. Il metodo restituisce `true` o `false` rispettivamente se l'autorizzazione è consentita o meno. Le informazioni sulla procedura corrente sono reperibili in <xref:System.ServiceModel.OperationContext> passato come parametro al metodo.  
  
3.  Durante l'override controllare il nome del contratto, lo spazio dei nomi e l'azione, come indicato nell'esempio seguente. Se le condizioni sono valide, restituire `true.`.  
  
4.  Utilizzare il punto di estendibilità per utilizzare la classe. Per altre informazioni, vedere [procedura: creare un gestore autorizzazioni personalizzato per un servizio](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [Autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [Gestione delle attestazioni e dell'autorizzazione con il modello di identità](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
