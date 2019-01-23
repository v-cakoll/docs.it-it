---
title: Interfaccia IAppDomainSetup
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef967039450c77b5927d501de63d53a245c90be0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509831"
---
# <a name="iappdomainsetup-interface"></a>Interfaccia IAppDomainSetup
Fornisce proprietà che consentono all'host configurare un <xref:System.AppDomain?displayProperty=nameWithType> tipo prima di chiamare il [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) metodo per la sua creazione.  
  
## <a name="properties"></a>Proprietà  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|Ottiene o imposta il nome della directory che contiene l'applicazione.|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|Ottiene o imposta il nome dell'applicazione.|  
|<xref:System.AppDomainSetup.CachePath%2A>|Ottiene o imposta il nome di un'area specifica per l'applicazione, in cui i file sono una copia shadow.|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|Ottiene o imposta il nome del file di configurazione per un'applicazione.|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|Ottiene o imposta il nome della directory in cui i file generati dinamicamente sono archiviati e accessibili.|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|Ottiene o imposta il percorso del file di licenza che è associato a questo dominio.|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|Ottiene o imposta l'elenco delle directory combinato con il <xref:System.AppDomainSetup.ApplicationBase%2A> directory per verificare la presenza di assembly privati.|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|Ottiene o imposta un valore stringa che include o esclude <xref:System.AppDomainSetup.ApplicationBase%2A> dal percorso di ricerca per l'applicazione.|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|Ottiene o imposta i nomi delle directory contenenti gli assembly per la copia shadow.|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|Ottiene o imposta una stringa che indica se la copia shadow è attivata o disattivata. I valori validi sono "true" o "false".|  
  
## <a name="remarks"></a>Note  
 Il `IAppDomainSetup` interfaccia corrisponde a quella gestita <xref:System.IAppDomainSetup> un'interfaccia, quale la <xref:System.AppDomainSetup> il tipo implementa. Vedere <xref:System.IAppDomainSetup?displayProperty=nameWithType> per una descrizione dettagliata delle relative proprietà.  
  
 `IAppDomainSetup` rappresenta le informazioni di associazione di assembly che possono essere aggiunti a un <xref:System.AppDomain> istanza prima della sua creazione. Ad esempio, un host può impostare il <xref:System.AppDomainSetup.ApplicationBase%2A> proprietà per stabilire una directory radice in cui i probe di common language runtime (CLR) per gli assembly gestiti.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
