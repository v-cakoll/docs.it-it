---
title: Enumerazione METAHOST_POLICY_FLAGS
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a96af0c66d85c7eec9a97be3ba8c756b1e91849
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516037"
---
# <a name="metahostpolicyflags-enumeration"></a>Enumerazione METAHOST_POLICY_FLAGS
Fornisce i criteri di associazione che sono comuni per la maggior parte degli host di runtime. Questa enumerazione viene utilizzata per la [ICLRMetaHostPolicy::](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) (metodo).  
  
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
|`METAHOST_POLICY_HIGHCOMPAT`|Definisce i criteri di compatibilità elevata, che non considera qualsiasi common language runtime (CLR) caricato nel processo corrente. Invece considera solo i runtime installati e le preferenze del componente, come derivata da file di assembly stesso, la versione compilata su dichiarata o il file di configurazione.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|Applica criteri di aggiornamento per il risultato di associazione di versione quando una corrispondenza esatta non viene trovata, in base al contenuto di HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\Policy\Upgrades. Ciò ha lo stesso effetto [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|Associazione di risultati viene restituita come se l'immagine fornita alla chiamata sono stata avviata in un nuovo processo. Attualmente, `GetRequestedRuntime` ignora i set di runtime può essere caricati e associa a fronte del set di runtime installati. Questo flag consente a un host determinare quale runtime di un file eseguibile verrà associato da quando viene avviata.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|Viene visualizzata una finestra di dialogo di errore se `GetRequestedRuntime` non riesce a trovare un runtime che è compatibile con i parametri di input. A partire dal [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], questa finestra di dialogo di errore può assumere la forma di una finestra di dialogo funzionalità Windows in cui viene chiesto se l'utente desidera abilitare la funzionalità appropriata.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime` Usa come input aggiuntivi per il processo di associazione dell'immagine del processo (e qualsiasi file di configurazione corrispondente). Per impostazione predefinita, `GetRequestedRuntime` non eseguire il fallback per il percorso dell'immagine processo (in genere, il file EXE che è stato usato per avviare il processo) quando si determina il runtime a cui associarsi.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` è necessario controllare se è installato lo SKU appropriato quando non sono disponibili informazioni nel file di configurazione. Ciò consente alle applicazioni che non dispongono di file di configurazione ha esito negativo correttamente sugli SKU inferiori rispetto all'installazione predefinita di .NET Framework. Per impostazione predefinita `GetRequestedRuntime` non verifica se è installato lo SKU appropriato, a meno che l'attributo SKU è specificato nel file di configurazione `<supportedRuntime />` elemento.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` è necessario controllare se è installato lo SKU appropriato quando non sono disponibili informazioni nel file di configurazione. Ciò consente alle applicazioni che non dispongono di file di configurazione ha esito negativo correttamente sugli SKU inferiori rispetto all'installazione predefinita di .NET Framework. Per impostazione predefinita `GetRequestedRuntime` non verifica se è installato lo SKU appropriato, a meno che l'attributo SKU è specificato nel file di configurazione `<supportedRuntime />` elemento.|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime` deve ignorare SEM_FAILCRITICALERRORS (che viene impostato chiamando il [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) funzione) e visualizzare la finestra di dialogo di errore. Per impostazione predefinita, SEM_FAILCRITICALERRORS Elimina la finestra di dialogo di errore. Sono stata ereditata da un altro processo e l'errore invisibile all'utente può essere inaccettabile nel proprio scenario.|  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [Metodo GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
