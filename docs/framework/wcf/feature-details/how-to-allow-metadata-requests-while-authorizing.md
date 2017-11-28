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
# <a name="how-to-allow-metadata-requests-while-authorizing"></a><span data-ttu-id="e91af-102">Procedura: consentire richieste di metadati durante l'autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e91af-102">How To: Allow Metadata Requests While Authorizing</span></span>
<span data-ttu-id="e91af-103">Durante l'autorizzazione personalizzata potrebbe essere necessario consentire l'elaborazione di una richiesta di metadati.</span><span class="sxs-lookup"><span data-stu-id="e91af-103">During custom authorization, it may be necessary to allow a request for metadata to be processed.</span></span> <span data-ttu-id="e91af-104">Nell'argomento seguente vengono dettagliati i passaggi necessari per convalidare tale richiesta.</span><span class="sxs-lookup"><span data-stu-id="e91af-104">The following topic walks through the steps to validate such a request.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="e91af-105">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] autorizzazione, vedere [autorizzazione](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="e91af-105"> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] authorization, see [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
### <a name="to-allow-metadata-requests-during-authorization"></a><span data-ttu-id="e91af-106">Per consentire richieste di metadati durante l'autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e91af-106">To allow metadata requests during authorization</span></span>  
  
1.  <span data-ttu-id="e91af-107">Creare un'estensione della classe <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="e91af-107">Create an extension of the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
2.  <span data-ttu-id="e91af-108">Eseguire l'override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="e91af-108">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="e91af-109">Il metodo restituisce `true` o `false` rispettivamente se l'autorizzazione è consentita o meno.</span><span class="sxs-lookup"><span data-stu-id="e91af-109">The method returns `true` or `false` depending on whether authorization is allowed.</span></span> <span data-ttu-id="e91af-110">Le informazioni sulla procedura corrente sono reperibili in <xref:System.ServiceModel.OperationContext> passato come parametro al metodo.</span><span class="sxs-lookup"><span data-stu-id="e91af-110">Information about the current procedure is found in the <xref:System.ServiceModel.OperationContext> passed as a parameter to the method.</span></span>  
  
3.  <span data-ttu-id="e91af-111">Durante l'override controllare il nome del contratto, lo spazio dei nomi e l'azione, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e91af-111">In the override, check the contract name, namespace, and the action as shown in the following example.</span></span> <span data-ttu-id="e91af-112">Se le condizioni sono valide, restituire `true.`.</span><span class="sxs-lookup"><span data-stu-id="e91af-112">If the conditions are valid, then return `true.`</span></span>  
  
4.  <span data-ttu-id="e91af-113">Utilizzare il punto di estendibilità per utilizzare la classe.</span><span class="sxs-lookup"><span data-stu-id="e91af-113">Use the extensibility point to employ the class.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="e91af-114">[Procedura: creare un gestore autorizzazioni personalizzato per un servizio](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="e91af-114"> [How to: Create a Custom Authorization Manager for a Service](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e91af-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="e91af-115">Example</span></span>  
 <span data-ttu-id="e91af-116">Nell'esempio seguente viene illustrato un override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="e91af-116">The following example shows an override of the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span>  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e91af-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e91af-117">See Also</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [<span data-ttu-id="e91af-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e91af-118">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="e91af-119">Gestione attestazioni e autorizzazioni con il modello di identità</span><span class="sxs-lookup"><span data-stu-id="e91af-119">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
