---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: dd984b2ab89060451b1b2d02c324e803766908ce
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397719"
---
# \<net.pipe>
<span data-ttu-id="0e6c6-102">Specifica impostazioni di configurazione per Named Pipe Activation Service, che gestisce la durata della connessione named pipe, nonché le richieste di attivazione che arrivano sulle named pipe.</span><span class="sxs-lookup"><span data-stu-id="0e6c6-102">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.pipe>**  
  
## <a name="syntax"></a><span data-ttu-id="0e6c6-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e6c6-103">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="0e6c6-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="0e6c6-104">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e6c6-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0e6c6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0e6c6-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0e6c6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e6c6-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="0e6c6-107">Attributes</span></span>  
  
|<span data-ttu-id="0e6c6-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="0e6c6-108">Attribute</span></span>|<span data-ttu-id="0e6c6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e6c6-109">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="0e6c6-110">Numero intero che specifica il massimo di thread di accettazione contemporaneamente in attesa sull'endpoint di ascolto per il servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="0e6c6-110">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="0e6c6-111">Il valore predefinito è 2.</span><span class="sxs-lookup"><span data-stu-id="0e6c6-111">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="0e6c6-112">Numero intero che specifica il numero massimo di connessioni che possono rimanere in attesa di invio.</span><span class="sxs-lookup"><span data-stu-id="0e6c6-112">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="0e6c6-113">Il valore predefinito è 100.</span><span class="sxs-lookup"><span data-stu-id="0e6c6-113">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="0e6c6-114"><xref:System.TimeSpan> che specifica il timeout per la lettura dei dati sui frame e per l'esecuzione dell'invio della connessione dalle connessioni sottostanti.</span><span class="sxs-lookup"><span data-stu-id="0e6c6-114">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="0e6c6-115">L'impostazione predefinita è "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="0e6c6-115">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e6c6-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0e6c6-116">Child Elements</span></span>  
  
|<span data-ttu-id="0e6c6-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e6c6-117">Element</span></span>|<span data-ttu-id="0e6c6-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e6c6-118">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="0e6c6-119">Raccolta di elementi di configurazione che contengono un `securityIdentifier` attributo per specificare gli account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="0e6c6-119">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e6c6-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0e6c6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0e6c6-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e6c6-121">Element</span></span>|<span data-ttu-id="0e6c6-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e6c6-122">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="0e6c6-123">Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="0e6c6-123">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e6c6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e6c6-124">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
