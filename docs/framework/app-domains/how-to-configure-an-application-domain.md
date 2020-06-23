---
title: "Procedura: Configurare un dominio dell'applicazione"
description: Configurare un dominio applicazione in .NET. È possibile fornire a CLR le informazioni di configurazione per un nuovo dominio applicazione usando la classe AppDomainSetup.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
ms.openlocfilehash: 27afcf161bec74143fafb5dceb20597de73e23d4
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104855"
---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="579f2-104">Procedura: Configurare un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="579f2-104">How to: Configure an Application Domain</span></span>
<span data-ttu-id="579f2-105">La classe <xref:System.AppDomainSetup> consente di specificare Common Language Runtime con informazioni di configurazione per un nuovo dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="579f2-105">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="579f2-106">Quando si creano domini dell'applicazione, la proprietà fondamentale è <xref:System.AppDomainSetup.ApplicationBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="579f2-106">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="579f2-107">Le altre proprietà **AppDomainSetup** vengono usate principalmente dagli host di runtime per configurare un particolare dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="579f2-107">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="579f2-108">La proprietà **ApplicationBase** definisce la directory radice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="579f2-108">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="579f2-109">Quando riceve una richiesta di tipo, il runtime prova a individuare l'assembly contenente il tipo nella directory specificata dalla proprietà **ApplicationBase**.</span><span class="sxs-lookup"><span data-stu-id="579f2-109">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="579f2-110">Un nuovo dominio applicazione eredita solo la proprietà **ApplicationBase** del creatore.</span><span class="sxs-lookup"><span data-stu-id="579f2-110">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="579f2-111">L'esempio seguente crea un'istanza della classe **AppDomainSetup**, usa la classe per creare un nuovo dominio dell'applicazione, scrive le informazioni nella console, quindi scarica il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="579f2-111">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="579f2-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="579f2-112">Example</span></span>  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="579f2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="579f2-113">See also</span></span>

- [<span data-ttu-id="579f2-114">Programmazione con i domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="579f2-114">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="579f2-115">Uso dei domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="579f2-115">Using Application Domains</span></span>](use.md)
