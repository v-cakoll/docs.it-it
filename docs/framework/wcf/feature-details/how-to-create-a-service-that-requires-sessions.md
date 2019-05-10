---
title: 'Procedura: Creare un servizio che richiede sessioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
ms.openlocfilehash: 246ff5dbb9bf76ad6a93c78815f2b3e39c4380aa
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64635620"
---
# <a name="how-to-create-a-service-that-requires-sessions"></a><span data-ttu-id="f9821-102">Procedura: Creare un servizio che richiede sessioni</span><span class="sxs-lookup"><span data-stu-id="f9821-102">How to: Create a Service That Requires Sessions</span></span>
<span data-ttu-id="f9821-103">Le sessioni creano un stato condiviso tra due o più endpoint che abilita funzionalità utili quali i callback, la sicurezza multihop e le associazioni tra istanze di client e servizi.</span><span class="sxs-lookup"><span data-stu-id="f9821-103">Sessions create a shared state between two or more endpoints that enables useful features such as callbacks, multi-hop security, and associations between clients and service instances.</span></span> <span data-ttu-id="f9821-104">Per altre informazioni sulle sessioni nelle applicazioni Windows Communication Foundation (WCF), vedere [utilizzando le sessioni](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="f9821-104">For more information about sessions in Windows Communication Foundation (WCF) applications, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a><span data-ttu-id="f9821-105">Per specificare che un contratto richiede l'associazione per supportare sessioni</span><span class="sxs-lookup"><span data-stu-id="f9821-105">To specify that a contract require its binding to support sessions</span></span>  
  
1. <span data-ttu-id="f9821-106">Creare un contratto di servizio con almeno un'operazione.</span><span class="sxs-lookup"><span data-stu-id="f9821-106">Create a service contract with at least one operation.</span></span> <span data-ttu-id="f9821-107">Per un esempio di come creare un contratto di servizio, vedere [come: Definire un contratto di servizio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="f9821-107">For an example of how to create a service contract, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2. <span data-ttu-id="f9821-108">Modificare la classe <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> che dichiara il contratto impostando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> su uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="f9821-108">Modify the <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> that declares the contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> property to either:</span></span>  
  
    - <span data-ttu-id="f9821-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>, se questo contratto deve essere eseguito all'interno di una sessione.</span><span class="sxs-lookup"><span data-stu-id="f9821-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType> if this contract must be run within a session.</span></span>  
  
    - <span data-ttu-id="f9821-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType>, se questo contratto può essere eseguito all'interno di una sessione.</span><span class="sxs-lookup"><span data-stu-id="f9821-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType> if this contract can be run within a session.</span></span>  
  
    - <span data-ttu-id="f9821-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType>, se questo contratto non deve essere eseguito all'interno di una sessione.</span><span class="sxs-lookup"><span data-stu-id="f9821-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType> if this contract must not be run within a session.</span></span>  
  
3. <span data-ttu-id="f9821-112">Configurare l'endpoint del servizio per l'utilizzo di un'associazione che supporti sessioni.</span><span class="sxs-lookup"><span data-stu-id="f9821-112">Configure your service endpoint to use a binding that supports sessions.</span></span> <span data-ttu-id="f9821-113">Nell'esempio di configurazione seguente viene illustrato l'utilizzo di <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, che supporta una sessione di WS`-`ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="f9821-113">The following configuration example shows the use of the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, which supports a WS`-`ReliableMessaging session.</span></span>  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]   
  
## <a name="example"></a><span data-ttu-id="f9821-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="f9821-114">Example</span></span>  
 <span data-ttu-id="f9821-115">Nell'esempio di codice seguente viene illustrato come specificare un requisito di sessione a livello di contratto e utilizzare un file di configurazione per supportare tale requisito con l'associazione <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f9821-115">The following example code shows how to specify a contract-level session requirement and use a configuration file to support that requirement with the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> binding.</span></span>  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)] 
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]      
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]     
  
## <a name="see-also"></a><span data-ttu-id="f9821-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9821-116">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
