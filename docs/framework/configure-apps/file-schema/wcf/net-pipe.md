---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: 885cfad7be42f7c48b4c061f3293d667eb5d4ad8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103396"
---
# <a name="netpipe"></a><span data-ttu-id="4fe26-102">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="4fe26-102">\<net.pipe></span></span>
<span data-ttu-id="4fe26-103">Specifica impostazioni di configurazione per Named Pipe Activation Service, che gestisce la durata della connessione named pipe, nonché le richieste di attivazione che arrivano sulle named pipe.</span><span class="sxs-lookup"><span data-stu-id="4fe26-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
 <span data-ttu-id="4fe26-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="4fe26-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="4fe26-105">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="4fe26-105">\<net.pipe></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fe26-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4fe26-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.pipe maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              receiveTimeout="TimeSpan">
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
    </net.pipe>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="4fe26-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="4fe26-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fe26-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4fe26-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4fe26-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4fe26-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fe26-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="4fe26-110">Attributes</span></span>  
  
|<span data-ttu-id="4fe26-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="4fe26-111">Attribute</span></span>|<span data-ttu-id="4fe26-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4fe26-112">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="4fe26-113">Numero intero che specifica il massimo di thread di accettazione contemporaneamente in attesa sull'endpoint di ascolto per il servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="4fe26-113">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="4fe26-114">Il valore predefinito è 2.</span><span class="sxs-lookup"><span data-stu-id="4fe26-114">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="4fe26-115">Numero intero che specifica il numero massimo di connessioni che possono rimanere in attesa di invio.</span><span class="sxs-lookup"><span data-stu-id="4fe26-115">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="4fe26-116">Il valore predefinito è 100.</span><span class="sxs-lookup"><span data-stu-id="4fe26-116">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="4fe26-117"><xref:System.TimeSpan> che specifica il timeout per la lettura dei dati sui frame e per l'esecuzione dell'invio della connessione dalle connessioni sottostanti.</span><span class="sxs-lookup"><span data-stu-id="4fe26-117">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="4fe26-118">L'impostazione predefinita è "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="4fe26-118">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4fe26-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4fe26-119">Child Elements</span></span>  
  
|<span data-ttu-id="4fe26-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4fe26-120">Element</span></span>|<span data-ttu-id="4fe26-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4fe26-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fe26-122">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="4fe26-122">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="4fe26-123">Una raccolta di elementi di configurazione che contengono un `securityIdentifier` attributo per specificare gli account utente per processi che ospitano servizi WCF e vengono concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="4fe26-123">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4fe26-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4fe26-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4fe26-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="4fe26-125">Element</span></span>|<span data-ttu-id="4fe26-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4fe26-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fe26-127">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="4fe26-127">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="4fe26-128">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="4fe26-128">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4fe26-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fe26-129">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
