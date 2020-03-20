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
# <a name="how-to-create-a-service-that-requires-sessions"></a><span data-ttu-id="9f238-102">Procedura: creare un servizio che richiede sessioni</span><span class="sxs-lookup"><span data-stu-id="9f238-102">How to: Create a Service That Requires Sessions</span></span>
<span data-ttu-id="9f238-103">Le sessioni creano un stato condiviso tra due o più endpoint che abilita funzionalità utili quali i callback, la sicurezza multihop e le associazioni tra istanze di client e servizi.</span><span class="sxs-lookup"><span data-stu-id="9f238-103">Sessions create a shared state between two or more endpoints that enables useful features such as callbacks, multi-hop security, and associations between clients and service instances.</span></span> <span data-ttu-id="9f238-104">Per ulteriori informazioni sulle sessioni nelle applicazioni Windows Communication Foundation (WCF), vedere [Utilizzo delle sessioni](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="9f238-104">For more information about sessions in Windows Communication Foundation (WCF) applications, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a><span data-ttu-id="9f238-105">Per specificare che un contratto richiede l'associazione per supportare sessioni</span><span class="sxs-lookup"><span data-stu-id="9f238-105">To specify that a contract require its binding to support sessions</span></span>  
  
1. <span data-ttu-id="9f238-106">Creare un contratto di servizio con almeno un'operazione.</span><span class="sxs-lookup"><span data-stu-id="9f238-106">Create a service contract with at least one operation.</span></span> <span data-ttu-id="9f238-107">Per un esempio di creazione di un contratto di assistenza, vedere [Procedura: definire un contratto](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)di assistenza .</span><span class="sxs-lookup"><span data-stu-id="9f238-107">For an example of how to create a service contract, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2. <span data-ttu-id="9f238-108">Modificare la classe <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> che dichiara il contratto impostando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> su uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="9f238-108">Modify the <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> that declares the contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> property to either:</span></span>  
  
    - <span data-ttu-id="9f238-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>, se questo contratto deve essere eseguito all'interno di una sessione.</span><span class="sxs-lookup"><span data-stu-id="9f238-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType> if this contract must be run within a session.</span></span>  
  
    - <span data-ttu-id="9f238-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType>, se questo contratto può essere eseguito all'interno di una sessione.</span><span class="sxs-lookup"><span data-stu-id="9f238-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType> if this contract can be run within a session.</span></span>  
  
    - <span data-ttu-id="9f238-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType>, se questo contratto non deve essere eseguito all'interno di una sessione.</span><span class="sxs-lookup"><span data-stu-id="9f238-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType> if this contract must not be run within a session.</span></span>  
  
3. <span data-ttu-id="9f238-112">Configurare l'endpoint del servizio per l'utilizzo di un'associazione che supporti sessioni.</span><span class="sxs-lookup"><span data-stu-id="9f238-112">Configure your service endpoint to use a binding that supports sessions.</span></span> <span data-ttu-id="9f238-113">Nell'esempio di configurazione seguente viene illustrato l'utilizzo di <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, che supporta una sessione di WS`-`ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="9f238-113">The following configuration example shows the use of the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, which supports a WS`-`ReliableMessaging session.</span></span>  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
  
## <a name="example"></a><span data-ttu-id="9f238-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f238-114">Example</span></span>  
 <span data-ttu-id="9f238-115">Nell'esempio di codice seguente viene illustrato come specificare un requisito di sessione a livello di contratto e utilizzare un file di configurazione per supportare tale requisito con l'associazione <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9f238-115">The following example code shows how to specify a contract-level session requirement and use a configuration file to support that requirement with the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> binding.</span></span>  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)]
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
  
## <a name="see-also"></a><span data-ttu-id="9f238-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f238-116">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
