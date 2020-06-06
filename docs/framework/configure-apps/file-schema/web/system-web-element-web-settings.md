---
title: Elemento <system.web> (impostazioni Web)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152841"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="bbb75-102">Elemento \<system.web> (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="bbb75-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="bbb75-103">Contiene informazioni sul modo in cui il livello di hosting di ASP.NET gestisce il comportamento a livello di processo.</span><span class="sxs-lookup"><span data-stu-id="bbb75-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a><span data-ttu-id="bbb75-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bbb75-104">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bbb75-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bbb75-105">Attributes and Elements</span></span>  

<span data-ttu-id="bbb75-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bbb75-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bbb75-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="bbb75-107">Attributes</span></span>  

<span data-ttu-id="bbb75-108">No.</span><span class="sxs-lookup"><span data-stu-id="bbb75-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bbb75-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bbb75-109">Child Elements</span></span>  
  
|<span data-ttu-id="bbb75-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="bbb75-110">Element</span></span>|<span data-ttu-id="bbb75-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bbb75-111">Description</span></span>|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|<span data-ttu-id="bbb75-112">Specifica le impostazioni di configurazione per i pool di applicazioni IIS in un file Aspnet. config.</span><span class="sxs-lookup"><span data-stu-id="bbb75-112">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bbb75-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bbb75-113">Parent Elements</span></span>  
  
|<span data-ttu-id="bbb75-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="bbb75-114">Element</span></span>|<span data-ttu-id="bbb75-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bbb75-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="bbb75-116">Specifica l'elemento radice in ogni file di configurazione usato dalle applicazioni Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bbb75-116">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbb75-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="bbb75-117">Remarks</span></span>  

<span data-ttu-id="bbb75-118">L' `system.web` elemento e il relativo `applicationPool` elemento figlio sono stati aggiunti all'.NET Framework a partire da .NET Framework 3,5 SP1.</span><span class="sxs-lookup"><span data-stu-id="bbb75-118">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="bbb75-119">Quando si esegue IIS 7,0 o versioni successive in modalità integrata, questa combinazione di elementi consente di configurare il modo in cui ASP.NET gestisce i thread e come Accoda le richieste quando ASP.NET è ospitato in un pool di applicazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="bbb75-119">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="bbb75-120">Se si esegue IIS 7,0 o versioni successive in modalità classica o ISAPI, queste impostazioni verranno ignorate.</span><span class="sxs-lookup"><span data-stu-id="bbb75-120">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbb75-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbb75-121">Example</span></span>  

<span data-ttu-id="bbb75-122">Nell'esempio seguente viene illustrato come configurare il comportamento a livello di processo di ASP.NET nel file Aspnet. config quando ASP.NET è ospitato in un pool di applicazioni IIS.</span><span class="sxs-lookup"><span data-stu-id="bbb75-122">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="bbb75-123">Nell'esempio si presuppone che IIS sia in esecuzione in modalità integrata e che l'applicazione utilizzi la .NET Framework 3,5 SP1 o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="bbb75-123">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="bbb75-124">Questo comportamento non si verifica nelle versioni del .NET Framework precedenti al .NET Framework 3,5 SP1.</span><span class="sxs-lookup"><span data-stu-id="bbb75-124">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="bbb75-125">I valori nell'esempio sono i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="bbb75-125">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="bbb75-126">Informazioni sull'elemento</span><span class="sxs-lookup"><span data-stu-id="bbb75-126">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bbb75-127">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="bbb75-127">Namespace</span></span>||  
|<span data-ttu-id="bbb75-128">Schema Name</span><span class="sxs-lookup"><span data-stu-id="bbb75-128">Schema Name</span></span>||  
|<span data-ttu-id="bbb75-129">File di convalida</span><span class="sxs-lookup"><span data-stu-id="bbb75-129">Validation File</span></span>||  
|<span data-ttu-id="bbb75-130">Può essere vuoto</span><span class="sxs-lookup"><span data-stu-id="bbb75-130">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="bbb75-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="bbb75-131">See also</span></span>

- [<span data-ttu-id="bbb75-132">\<applicationPool>Elemento (impostazioni Web)</span><span class="sxs-lookup"><span data-stu-id="bbb75-132">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
