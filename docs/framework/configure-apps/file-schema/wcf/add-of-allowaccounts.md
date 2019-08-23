---
title: <add> di <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 1ed0b5025ab969c45d7440f2a209426c5c87f549
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920284"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="a2b98-102">\<aggiungere > di \<AllowAccounts ></span><span class="sxs-lookup"><span data-stu-id="a2b98-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="a2b98-103">Specifica un account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="a2b98-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="a2b98-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="a2b98-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2b98-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2b98-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2b98-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a2b98-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a2b98-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a2b98-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2b98-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="a2b98-108">Attributes</span></span>  
  
|<span data-ttu-id="a2b98-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="a2b98-109">Attribute</span></span>|<span data-ttu-id="a2b98-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2b98-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a2b98-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="a2b98-111">securityIdentifier</span></span>|<span data-ttu-id="a2b98-112">Stringa che specifica un identificatore univoco usato per identificare un account utente.</span><span class="sxs-lookup"><span data-stu-id="a2b98-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="a2b98-113">I valori predefiniti sono LocalSystem, Administrators, NS, LS e IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="a2b98-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2b98-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a2b98-114">Child Elements</span></span>  
 <span data-ttu-id="a2b98-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a2b98-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2b98-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a2b98-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a2b98-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="a2b98-117">Element</span></span>|<span data-ttu-id="a2b98-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2b98-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2b98-119">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="a2b98-119">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="a2b98-120">Raccolta di elementi di configurazione che contengono un `securityIdentifier` attributo per specificare gli account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="a2b98-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a2b98-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2b98-121">Example</span></span>  
 <span data-ttu-id="a2b98-122">Nell'esempio di configurazione seguente i cinque identificatori predefiniti per gli account utente vengono aggiunti a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="a2b98-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a2b98-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2b98-123">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
