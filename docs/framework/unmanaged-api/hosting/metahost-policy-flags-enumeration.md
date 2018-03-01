---
title: Enumerazione METAHOST_POLICY_FLAGS
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 80abed08cc7659d4218dce445be81481bb5a665b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="metahostpolicyflags-enumeration"></a>Enumerazione METAHOST_POLICY_FLAGS
Fornisce criteri di associazione che sono comuni per la maggior parte degli host di runtime. Questa enumerazione viene utilizzata per la [ICLRMetaHostPolicy::](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|Definisce i criteri di compatibilità elevata, che non vengono considerate qualsiasi common language runtime (CLR) caricato nel processo corrente. Invece presi in considerazione solo i runtime installati e le preferenze del componente, derivato da file di assembly stesso, la versione compilata contro dichiarata o il file di configurazione.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|Applica i criteri di aggiornamento per il risultato di associazione della versione quando una corrispondenza esatta non viene trovata, in base al contenuto di HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\Policy\Upgrades. Questo è lo stesso effetto [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|Associazione vengono restituiti come se l'immagine fornita per la chiamata avviata in un nuovo processo. Attualmente, `GetRequestedRuntime` ignora il set di runtime caricabili e associazioni rispetto al set dei runtime installati. Questo flag consente a un host determinare il runtime a cui verrà associato a un EXE quando viene avviata.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|Viene visualizzata una finestra di dialogo di errore se `GetRequestedRuntime` non riesce a trovare un runtime che è compatibile con i parametri di input. A partire dal [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], questa finestra di dialogo di errore può essere in forma di una finestra di dialogo per la funzionalità Windows in cui viene chiesto se si desidera abilitare la funzionalità appropriata.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime`Usa l'immagine del processo (e qualsiasi file di configurazione corrispondente) come input aggiuntivi per il processo di associazione. Per impostazione predefinita, `GetRequestedRuntime` non eseguire il fallback per il percorso dell'immagine di processo (in genere, il file EXE che è stato utilizzato per avviare il processo) quando si determina il runtime da associare.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime`è necessario controllare se è installata la SKU appropriata quando non sono disponibili informazioni nel file di configurazione. Ciò consente alle applicazioni che non contengono i file di configurazione avrà esito negativo normalmente SKU più piccoli rispetto all'installazione predefinita di .NET Framework. Per impostazione predefinita, `GetRequestedRuntime` non verifica se è installata la SKU appropriata, a meno che l'attributo SKU è specificato nel file di configurazione `<supportedRuntime />` elemento.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime`è necessario controllare se è installata la SKU appropriata quando non sono disponibili informazioni nel file di configurazione. Ciò consente alle applicazioni che non contengono i file di configurazione avrà esito negativo normalmente SKU più piccoli rispetto all'installazione predefinita di .NET Framework. Per impostazione predefinita, `GetRequestedRuntime` non verifica se è installata la SKU appropriata, a meno che l'attributo SKU è specificato nel file di configurazione `<supportedRuntime />` elemento.|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime`deve essere ignorato SEM_FAILCRITICALERRORS (che viene impostato chiamando la [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) funzione) e visualizzare la finestra di dialogo di errore. Per impostazione predefinita, SEM_FAILCRITICALERRORS Elimina la finestra di dialogo di errore. Sono stata ereditata da un altro processo e l'errore invisibile all'utente potrebbe essere indesiderata nello scenario.|  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [Metodo GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
