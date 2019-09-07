---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: dd984b2ab89060451b1b2d02c324e803766908ce
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397719"
---
# <a name="netpipe"></a><span data-ttu-id="21fa1-102">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="21fa1-102">\<net.pipe></span></span>
<span data-ttu-id="21fa1-103">Specifica impostazioni di configurazione per Named Pipe Activation Service, che gestisce la durata della connessione named pipe, nonché le richieste di attivazione che arrivano sulle named pipe.</span><span class="sxs-lookup"><span data-stu-id="21fa1-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
<span data-ttu-id="21fa1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="21fa1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="21fa1-105">&nbsp;&nbsp;[ **\<System. serviceModel. Activation >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="21fa1-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="21fa1-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> NET. pipe**</span><span class="sxs-lookup"><span data-stu-id="21fa1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<net.pipe>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21fa1-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21fa1-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="21fa1-108">Type</span><span class="sxs-lookup"><span data-stu-id="21fa1-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21fa1-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="21fa1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="21fa1-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="21fa1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21fa1-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="21fa1-111">Attributes</span></span>  
  
|<span data-ttu-id="21fa1-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="21fa1-112">Attribute</span></span>|<span data-ttu-id="21fa1-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="21fa1-113">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="21fa1-114">Numero intero che specifica il massimo di thread di accettazione contemporaneamente in attesa sull'endpoint di ascolto per il servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="21fa1-114">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="21fa1-115">Il valore predefinito è 2.</span><span class="sxs-lookup"><span data-stu-id="21fa1-115">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="21fa1-116">Numero intero che specifica il numero massimo di connessioni che possono rimanere in attesa di invio.</span><span class="sxs-lookup"><span data-stu-id="21fa1-116">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="21fa1-117">Il valore predefinito è 100.</span><span class="sxs-lookup"><span data-stu-id="21fa1-117">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="21fa1-118"><xref:System.TimeSpan> che specifica il timeout per la lettura dei dati sui frame e per l'esecuzione dell'invio della connessione dalle connessioni sottostanti.</span><span class="sxs-lookup"><span data-stu-id="21fa1-118">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="21fa1-119">L'impostazione predefinita è "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="21fa1-119">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21fa1-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="21fa1-120">Child Elements</span></span>  
  
|<span data-ttu-id="21fa1-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="21fa1-121">Element</span></span>|<span data-ttu-id="21fa1-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21fa1-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21fa1-123">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="21fa1-123">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="21fa1-124">Raccolta di elementi di configurazione che contengono un `securityIdentifier` attributo per specificare gli account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="21fa1-124">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="21fa1-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="21fa1-125">Parent Elements</span></span>  
  
|<span data-ttu-id="21fa1-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="21fa1-126">Element</span></span>|<span data-ttu-id="21fa1-127">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="21fa1-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21fa1-128">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="21fa1-128">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="21fa1-129">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="21fa1-129">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21fa1-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21fa1-130">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
