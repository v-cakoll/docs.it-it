---
title: "Procedura: consentire richieste di metadati durante l'autorizzazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
ms.openlocfilehash: 6d172f9b659804179d23fb382376f83f4898edc5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601309"
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a>Procedura: consentire richieste di metadati durante l'autorizzazione
Durante l'autorizzazione personalizzata potrebbe essere necessario consentire l'elaborazione di una richiesta di metadati. Nell'argomento seguente vengono dettagliati i passaggi necessari per convalidare tale richiesta.  
  
 Per ulteriori informazioni sull'autorizzazione Windows Communication Foundation (WCF), vedere [autorizzazione](authorization-in-wcf.md).  
  
### <a name="to-allow-metadata-requests-during-authorization"></a>Per consentire richieste di metadati durante l'autorizzazione  
  
1. Creare un'estensione della classe <xref:System.ServiceModel.ServiceAuthorizationManager>.  
  
2. Eseguire l'override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> . Il metodo restituisce `true` o `false` rispettivamente se l'autorizzazione è consentita o meno. Le informazioni sulla procedura corrente sono reperibili in <xref:System.ServiceModel.OperationContext> passato come parametro al metodo.  
  
3. Durante l'override controllare il nome del contratto, lo spazio dei nomi e l'azione, come indicato nell'esempio seguente. Se le condizioni sono valide, restituire `true.`.  
  
4. Utilizzare il punto di estendibilità per utilizzare la classe. Per altre informazioni, vedere [procedura: creare un gestore autorizzazioni personalizzato per un servizio](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [Autorizzazione](authorization-in-wcf.md)
- [Gestione di attestazioni e autorizzazioni con il modello di identità](managing-claims-and-authorization-with-the-identity-model.md)
