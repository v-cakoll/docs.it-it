---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c62f29c53d807cab397ff09c6163d924a71ea319
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926608"
---
# <a name="allowaccounts"></a><span data-ttu-id="53efa-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="53efa-101">\<allowAccounts></span></span>
<span data-ttu-id="53efa-102">Contiene una raccolta di elementi di configurazione che specificano gli account utente per i processi che ospitano i servizi Windows Communication Foundation (WCF) e a cui viene concesso l'accesso alla connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="53efa-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="53efa-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="53efa-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53efa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53efa-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53efa-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="53efa-105">Attributes and Elements</span></span>  
 <span data-ttu-id="53efa-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="53efa-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53efa-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="53efa-107">Attributes</span></span>  
 <span data-ttu-id="53efa-108">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="53efa-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="53efa-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="53efa-109">Child Elements</span></span>  
  
|<span data-ttu-id="53efa-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="53efa-110">Attribute</span></span>|<span data-ttu-id="53efa-111">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="53efa-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="53efa-112">\<add></span><span class="sxs-lookup"><span data-stu-id="53efa-112">\<add></span></span>](add-of-allowaccounts.md)|<span data-ttu-id="53efa-113">Aggiunge un account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione</span><span class="sxs-lookup"><span data-stu-id="53efa-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53efa-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="53efa-114">Parent Elements</span></span>  
  
|<span data-ttu-id="53efa-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="53efa-115">Element</span></span>|<span data-ttu-id="53efa-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53efa-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53efa-117">NET. pipe > o [ \<](net-pipe.md) [ \<NET. TCP >](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="53efa-117">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="53efa-118">Specifica impostazioni di configurazione per i servizi di condivisione Net Pipe o TCP.</span><span class="sxs-lookup"><span data-stu-id="53efa-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53efa-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53efa-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
