---
title: 'Procedura: configurare un dominio applicazione'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d8db75edec8e80e0e137593a424f12575cfc747b
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="d8751-102">Procedura: configurare un dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="d8751-102">How to: Configure an Application Domain</span></span>
<span data-ttu-id="d8751-103">La classe <xref:System.AppDomainSetup> consente di specificare Common Language Runtime con informazioni di configurazione per un nuovo dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8751-103">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="d8751-104">Quando si creano domini dell'applicazione, la proprietà fondamentale è <xref:System.AppDomainSetup.ApplicationBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8751-104">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="d8751-105">Le altre proprietà **AppDomainSetup** vengono usate principalmente dagli host di runtime per configurare un particolare dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8751-105">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="d8751-106">La proprietà **ApplicationBase** definisce la directory radice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8751-106">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="d8751-107">Quando riceve una richiesta di tipo, il runtime prova a individuare l'assembly contenente il tipo nella directory specificata dalla proprietà **ApplicationBase**.</span><span class="sxs-lookup"><span data-stu-id="d8751-107">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8751-108">Un nuovo dominio applicazione eredita solo la proprietà **ApplicationBase** del creatore.</span><span class="sxs-lookup"><span data-stu-id="d8751-108">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="d8751-109">L'esempio seguente crea un'istanza della classe **AppDomainSetup**, usa la classe per creare un nuovo dominio dell'applicazione, scrive le informazioni nella console, quindi scarica il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d8751-109">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8751-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8751-110">Example</span></span>  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d8751-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8751-111">See Also</span></span>  
 [<span data-ttu-id="d8751-112">Programmazione con i domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d8751-112">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)  
 [<span data-ttu-id="d8751-113">Uso dei domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d8751-113">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
