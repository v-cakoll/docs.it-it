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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f9cff53b598d4e477488bcb5b5e87be62e78bb9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-service-that-requires-sessions"></a><span data-ttu-id="571f4-102">Procedura: creare un servizio che richiede sessioni</span><span class="sxs-lookup"><span data-stu-id="571f4-102">How to: Create a Service That Requires Sessions</span></span>
<span data-ttu-id="571f4-103">Le sessioni creano un stato condiviso tra due o più endpoint che abilita funzionalità utili quali i callback, la sicurezza multihop e le associazioni tra istanze di client e servizi.</span><span class="sxs-lookup"><span data-stu-id="571f4-103">Sessions create a shared state between two or more endpoints that enables useful features such as callbacks, multi-hop security, and associations between clients and service instances.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="571f4-104">le sessioni in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] applicazioni, vedere [utilizzando le sessioni](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="571f4-104"> sessions in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] applications, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a><span data-ttu-id="571f4-105">Per specificare che un contratto richiede l'associazione per supportare sessioni</span><span class="sxs-lookup"><span data-stu-id="571f4-105">To specify that a contract require its binding to support sessions</span></span>  
  
1.  <span data-ttu-id="571f4-106">Creare un contratto di servizio con almeno un'operazione.</span><span class="sxs-lookup"><span data-stu-id="571f4-106">Create a service contract with at least one operation.</span></span> <span data-ttu-id="571f4-107">Per un esempio di come creare un contratto di servizio, vedere [procedura: definire un contratto di servizio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="571f4-107">For an example of how to create a service contract, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2.  <span data-ttu-id="571f4-108">Modificare la classe <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> che dichiara il contratto impostando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> su uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="571f4-108">Modify the <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> that declares the contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> property to either:</span></span>  
  
    -   <span data-ttu-id="571f4-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>, se questo contratto deve essere eseguito all'interno di una sessione.</span><span class="sxs-lookup"><span data-stu-id="571f4-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType> if this contract must be run within a session.</span></span>  
  
    -   <span data-ttu-id="571f4-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType>, se questo contratto può essere eseguito all'interno di una sessione.</span><span class="sxs-lookup"><span data-stu-id="571f4-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType> if this contract can be run within a session.</span></span>  
  
    -   <span data-ttu-id="571f4-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType>, se questo contratto non deve essere eseguito all'interno di una sessione.</span><span class="sxs-lookup"><span data-stu-id="571f4-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType> if this contract must not be run within a session.</span></span>  
  
3.  <span data-ttu-id="571f4-112">Configurare l'endpoint del servizio per l'utilizzo di un'associazione che supporti sessioni.</span><span class="sxs-lookup"><span data-stu-id="571f4-112">Configure your service endpoint to use a binding that supports sessions.</span></span> <span data-ttu-id="571f4-113">Nell'esempio di configurazione seguente viene illustrato l'utilizzo di <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, che supporta una sessione di WS`-`ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="571f4-113">The following configuration example shows the use of the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, which supports a WS`-`ReliableMessaging session.</span></span>  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]   
  
## <a name="example"></a><span data-ttu-id="571f4-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="571f4-114">Example</span></span>  
 <span data-ttu-id="571f4-115">Nell'esempio di codice seguente viene illustrato come specificare un requisito di sessione a livello di contratto e utilizzare un file di configurazione per supportare tale requisito con l'associazione <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="571f4-115">The following example code shows how to specify a contract-level session requirement and use a configuration file to support that requirement with the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> binding.</span></span>  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)] 
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]      
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]     
  
## <a name="see-also"></a><span data-ttu-id="571f4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="571f4-116">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>  
 <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
