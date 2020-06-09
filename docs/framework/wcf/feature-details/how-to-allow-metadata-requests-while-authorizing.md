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
# <a name="how-to-allow-metadata-requests-while-authorizing"></a><span data-ttu-id="c159c-102">Procedura: consentire richieste di metadati durante l'autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c159c-102">How To: Allow Metadata Requests While Authorizing</span></span>
<span data-ttu-id="c159c-103">Durante l'autorizzazione personalizzata potrebbe essere necessario consentire l'elaborazione di una richiesta di metadati.</span><span class="sxs-lookup"><span data-stu-id="c159c-103">During custom authorization, it may be necessary to allow a request for metadata to be processed.</span></span> <span data-ttu-id="c159c-104">Nell'argomento seguente vengono dettagliati i passaggi necessari per convalidare tale richiesta.</span><span class="sxs-lookup"><span data-stu-id="c159c-104">The following topic walks through the steps to validate such a request.</span></span>  
  
 <span data-ttu-id="c159c-105">Per ulteriori informazioni sull'autorizzazione Windows Communication Foundation (WCF), vedere [autorizzazione](authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="c159c-105">For more information about Windows Communication Foundation (WCF) authorization, see [Authorization](authorization-in-wcf.md).</span></span>  
  
### <a name="to-allow-metadata-requests-during-authorization"></a><span data-ttu-id="c159c-106">Per consentire richieste di metadati durante l'autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c159c-106">To allow metadata requests during authorization</span></span>  
  
1. <span data-ttu-id="c159c-107">Creare un'estensione della classe <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="c159c-107">Create an extension of the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
2. <span data-ttu-id="c159c-108">Eseguire l'override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> .</span><span class="sxs-lookup"><span data-stu-id="c159c-108">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="c159c-109">Il metodo restituisce `true` o `false` rispettivamente se l'autorizzazione è consentita o meno.</span><span class="sxs-lookup"><span data-stu-id="c159c-109">The method returns `true` or `false` depending on whether authorization is allowed.</span></span> <span data-ttu-id="c159c-110">Le informazioni sulla procedura corrente sono reperibili in <xref:System.ServiceModel.OperationContext> passato come parametro al metodo.</span><span class="sxs-lookup"><span data-stu-id="c159c-110">Information about the current procedure is found in the <xref:System.ServiceModel.OperationContext> passed as a parameter to the method.</span></span>  
  
3. <span data-ttu-id="c159c-111">Durante l'override controllare il nome del contratto, lo spazio dei nomi e l'azione, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c159c-111">In the override, check the contract name, namespace, and the action as shown in the following example.</span></span> <span data-ttu-id="c159c-112">Se le condizioni sono valide, restituire `true.`.</span><span class="sxs-lookup"><span data-stu-id="c159c-112">If the conditions are valid, then return `true.`</span></span>  
  
4. <span data-ttu-id="c159c-113">Utilizzare il punto di estendibilità per utilizzare la classe.</span><span class="sxs-lookup"><span data-stu-id="c159c-113">Use the extensibility point to employ the class.</span></span> <span data-ttu-id="c159c-114">Per altre informazioni, vedere [procedura: creare un gestore autorizzazioni personalizzato per un servizio](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="c159c-114">For more information, see [How to: Create a Custom Authorization Manager for a Service](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c159c-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="c159c-115">Example</span></span>  
 <span data-ttu-id="c159c-116">Nell'esempio seguente viene illustrato un override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="c159c-116">The following example shows an override of the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span>  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c159c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c159c-117">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [<span data-ttu-id="c159c-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c159c-118">Authorization</span></span>](authorization-in-wcf.md)
- [<span data-ttu-id="c159c-119">Gestione di attestazioni e autorizzazioni con il modello di identità</span><span class="sxs-lookup"><span data-stu-id="c159c-119">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
