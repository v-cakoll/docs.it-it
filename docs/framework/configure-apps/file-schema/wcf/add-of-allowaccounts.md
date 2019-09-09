---
title: <add> di <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 02654b8ab198a2b161b3044c1f3aa452761a6a4c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398384"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="743fe-102">\<aggiungere > di \<AllowAccounts ></span><span class="sxs-lookup"><span data-stu-id="743fe-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="743fe-103">Specifica un account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="743fe-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
<span data-ttu-id="743fe-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="743fe-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="743fe-105">&nbsp;&nbsp;[ **\<System. serviceModel. Activation >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="743fe-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="743fe-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> NET. pipe**](net-pipe.md)</span><span class="sxs-lookup"><span data-stu-id="743fe-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)</span></span>\
<span data-ttu-id="743fe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> allowAccounts**](allowaccounts.md)</span><span class="sxs-lookup"><span data-stu-id="743fe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)</span></span>\
<span data-ttu-id="743fe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="743fe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="743fe-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="743fe-109">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="743fe-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="743fe-110">Attributes and Elements</span></span>  
 <span data-ttu-id="743fe-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="743fe-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="743fe-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="743fe-112">Attributes</span></span>  
  
|<span data-ttu-id="743fe-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="743fe-113">Attribute</span></span>|<span data-ttu-id="743fe-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="743fe-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="743fe-115">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="743fe-115">securityIdentifier</span></span>|<span data-ttu-id="743fe-116">Stringa che specifica un identificatore univoco usato per identificare un account utente.</span><span class="sxs-lookup"><span data-stu-id="743fe-116">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="743fe-117">I valori predefiniti sono LocalSystem, Administrators, NS, LS e IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="743fe-117">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="743fe-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="743fe-118">Child Elements</span></span>  
 <span data-ttu-id="743fe-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="743fe-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="743fe-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="743fe-120">Parent Elements</span></span>  
  
|<span data-ttu-id="743fe-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="743fe-121">Element</span></span>|<span data-ttu-id="743fe-122">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="743fe-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="743fe-123">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="743fe-123">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="743fe-124">Raccolta di elementi di configurazione che contengono un `securityIdentifier` attributo per specificare gli account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="743fe-124">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="743fe-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="743fe-125">Example</span></span>  
 <span data-ttu-id="743fe-126">Nell'esempio di configurazione seguente i cinque identificatori predefiniti per gli account utente vengono aggiunti a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="743fe-126">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>
  <!-- LocalSystem account -->
  <add securityIdentifier="S-1-5-18" />
  <!-- LocalService account -->
  <add securityIdentifier="S-1-5-19" />
  <!-- Administrators account -->
  <add securityIdentifier="S-1-5-20" />
  <!-- Network Service account -->
  <add securityIdentifier="S-1-5-32-544" />
  <!-- IIS_IUSRS account (Vista only) -->
  <add securityIdentifier="S-1-5-32-568" />
</allowAccounts>
```  
  
## <a name="see-also"></a><span data-ttu-id="743fe-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="743fe-127">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
