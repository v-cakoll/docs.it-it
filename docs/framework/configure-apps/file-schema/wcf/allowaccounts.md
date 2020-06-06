---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 74b9d51b7400469c96fc9c8b36e4b0fb1d46969b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398414"
---
# \<allowAccounts>
<span data-ttu-id="66b2f-101">Contiene una raccolta di elementi di configurazione che specificano gli account utente per i processi che ospitano i servizi Windows Communication Foundation (WCF) e a cui viene concesso l'accesso alla connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="66b2f-101">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a><span data-ttu-id="66b2f-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66b2f-102">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66b2f-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="66b2f-103">Attributes and Elements</span></span>  
 <span data-ttu-id="66b2f-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="66b2f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66b2f-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="66b2f-105">Attributes</span></span>  
 <span data-ttu-id="66b2f-106">No.</span><span class="sxs-lookup"><span data-stu-id="66b2f-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="66b2f-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="66b2f-107">Child Elements</span></span>  
  
|<span data-ttu-id="66b2f-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="66b2f-108">Attribute</span></span>|<span data-ttu-id="66b2f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66b2f-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|<span data-ttu-id="66b2f-110">Aggiunge un account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione</span><span class="sxs-lookup"><span data-stu-id="66b2f-110">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="66b2f-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="66b2f-111">Parent Elements</span></span>  
  
|<span data-ttu-id="66b2f-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="66b2f-112">Element</span></span>|<span data-ttu-id="66b2f-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66b2f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="66b2f-114">[\<net.pipe>](net-pipe.md)o[\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="66b2f-114">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="66b2f-115">Specifica impostazioni di configurazione per i servizi di condivisione Net Pipe o TCP.</span><span class="sxs-lookup"><span data-stu-id="66b2f-115">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66b2f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66b2f-116">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
