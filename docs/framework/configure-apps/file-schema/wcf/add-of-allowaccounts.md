---
title: <add> di <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 02654b8ab198a2b161b3044c1f3aa452761a6a4c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398384"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="b2dc9-102">\<add> di \<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="b2dc9-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="b2dc9-103">Specifica un account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="b2dc9-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="b2dc9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2dc9-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2dc9-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b2dc9-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b2dc9-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b2dc9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2dc9-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="b2dc9-107">Attributes</span></span>  
  
|<span data-ttu-id="b2dc9-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="b2dc9-108">Attribute</span></span>|<span data-ttu-id="b2dc9-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2dc9-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b2dc9-110">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="b2dc9-110">securityIdentifier</span></span>|<span data-ttu-id="b2dc9-111">Stringa che specifica un identificatore univoco usato per identificare un account utente.</span><span class="sxs-lookup"><span data-stu-id="b2dc9-111">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="b2dc9-112">I valori predefiniti sono LocalSystem, Administrators, NS, LS e IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="b2dc9-112">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2dc9-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b2dc9-113">Child Elements</span></span>  
 <span data-ttu-id="b2dc9-114">No.</span><span class="sxs-lookup"><span data-stu-id="b2dc9-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2dc9-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b2dc9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b2dc9-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b2dc9-116">Element</span></span>|<span data-ttu-id="b2dc9-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2dc9-117">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="b2dc9-118">Raccolta di elementi di configurazione che contengono un `securityIdentifier` attributo per specificare gli account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="b2dc9-118">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b2dc9-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2dc9-119">Example</span></span>  
 <span data-ttu-id="b2dc9-120">Nell'esempio di configurazione seguente i cinque identificatori predefiniti per gli account utente vengono aggiunti a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="b2dc9-120">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2dc9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2dc9-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
