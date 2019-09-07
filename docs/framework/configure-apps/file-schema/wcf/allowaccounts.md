---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 74b9d51b7400469c96fc9c8b36e4b0fb1d46969b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398414"
---
# <a name="allowaccounts"></a><span data-ttu-id="b100c-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="b100c-101">\<allowAccounts></span></span>
<span data-ttu-id="b100c-102">Contiene una raccolta di elementi di configurazione che specificano gli account utente per i processi che ospitano i servizi Windows Communication Foundation (WCF) e a cui viene concesso l'accesso alla connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="b100c-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
<span data-ttu-id="b100c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b100c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b100c-104">&nbsp;&nbsp;[ **\<System. serviceModel. Activation >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="b100c-104">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="b100c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> NET. pipe**](net-pipe.md)</span><span class="sxs-lookup"><span data-stu-id="b100c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)</span></span>\
<span data-ttu-id="b100c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> allowAccounts**</span><span class="sxs-lookup"><span data-stu-id="b100c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b100c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b100c-107">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b100c-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b100c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b100c-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b100c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b100c-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b100c-110">Attributes</span></span>  
 <span data-ttu-id="b100c-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b100c-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b100c-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b100c-112">Child Elements</span></span>  
  
|<span data-ttu-id="b100c-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="b100c-113">Attribute</span></span>|<span data-ttu-id="b100c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b100c-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="b100c-115">\<add></span><span class="sxs-lookup"><span data-stu-id="b100c-115">\<add></span></span>](add-of-allowaccounts.md)|<span data-ttu-id="b100c-116">Aggiunge un account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione</span><span class="sxs-lookup"><span data-stu-id="b100c-116">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b100c-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b100c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b100c-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="b100c-118">Element</span></span>|<span data-ttu-id="b100c-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b100c-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b100c-120">NET. pipe > o [ \<](net-pipe.md) [ \<NET. TCP >](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="b100c-120">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="b100c-121">Specifica impostazioni di configurazione per i servizi di condivisione Net Pipe o TCP.</span><span class="sxs-lookup"><span data-stu-id="b100c-121">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b100c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b100c-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
