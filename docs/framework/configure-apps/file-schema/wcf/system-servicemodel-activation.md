---
title: <system.serviceModel.activation>
ms.date: 03/30/2017
ms.assetid: c0cae85f-56cb-4030-8807-6f96edff8d2d
ms.openlocfilehash: e00bbad452398e7f8f4f50208da572986391fc9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399469"
---
# \<system.serviceModel.activation>
<span data-ttu-id="60713-102">Questa sezione di configurazione rappresenta le impostazioni di configurazione per lo strumento SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="60713-102">This configuration section represents the configuration settings for the SMSvcHost.exe tool.</span></span> <span data-ttu-id="60713-103">Gli elementi di configurazione che possono essere configurati nel file SMSvcHost.exe.config.</span><span class="sxs-lookup"><span data-stu-id="60713-103">The configuration elements can be configured in the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="60713-104">In particolare, include tutte le impostazioni che devono essere configurate a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="60713-104">Specifically, it includes all machine-wide settings that must be configured.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.serviceModel.activation>**  
  
## <a name="sample-configuration-file"></a><span data-ttu-id="60713-105">File di configurazione di esempio</span><span class="sxs-lookup"><span data-stu-id="60713-105">Sample Configuration File</span></span>  
 <span data-ttu-id="60713-106">Di seguito è mostrato un file di configurazione di esempio (SMSvcHost.exe.config), usato dal processo del listener SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="60713-106">The following is a sample configuration file (SMSvcHost.exe.config), which is used by the listener process SMSvcHost.exe.</span></span>  
  
```xml  
<configuration>
  <runtime>
    <gcConcurrent enabled="false" />
  </runtime>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="10"
             maxPendingAccepts="2"
             maxPendingConnections="100"
             receiveTimeout="00:00:10"
             teredoEnabled="false">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
    <net.pipe maxConnectionsPendingDispatch="100"
              maxPendingAccepts="2"
              receiveTimeout="00:00:10">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
    <diagnostics performanceCountersEnabled="true" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="60713-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60713-107">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration>
