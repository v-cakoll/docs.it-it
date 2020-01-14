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
ms.openlocfilehash: 048286fb9e1af34cd964fb5b21892778f9575d2c
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938200"
---
# <a name="metahost_policy_flags-enumeration"></a>Enumerazione METAHOST_POLICY_FLAGS
Fornisce criteri di associazione comuni alla maggior parte degli host di Runtime. Questa enumerazione viene utilizzata dal metodo [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
|Member|Descrizione|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|Definisce i criteri di compatibilità elevata, che non considera alcun Common Language Runtime (CLR) caricato nel processo corrente. Considera invece solo i CLR installati e le preferenze del componente, come derivato dal file di assembly stesso, dalla versione predefinita dichiarata o dal file di configurazione.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|Applica i criteri di aggiornamento al risultato dell'associazione della versione quando non viene trovata una corrispondenza esatta, in base al contenuto di HKEY_LOCAL_MACHINE\\\SOFTWARE\Microsoft. NETFramework\Policy\Upgrades. Questa operazione ha lo stesso effetto di [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|I risultati dell'associazione vengono restituiti come se l'immagine fornita alla chiamata venisse avviata in un nuovo processo. Attualmente, `GetRequestedRuntime` ignora il set di Runtime caricabili e viene associato al set di runtime installati. Questo flag consente a un host di determinare a quale Runtime verrà associato un file EXE quando viene avviato.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|Se `GetRequestedRuntime` non è in grado di trovare un runtime compatibile con i parametri di input, viene visualizzata una finestra di dialogo di errore. A partire da .NET Framework 4,5, questa finestra di dialogo di errore può assumere il formato di una finestra di dialogo funzionalità di Windows che chiede se l'utente vuole abilitare la funzionalità appropriata.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime` usa l'immagine di processo (e qualsiasi file di configurazione corrispondente) come input aggiuntivo per il processo di associazione. Per impostazione predefinita, `GetRequestedRuntime` non viene eseguito il fallback al percorso dell'immagine del processo (in genere, il file EXE utilizzato per avviare il processo) quando si determina il runtime a cui eseguire l'associazione.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` necessario controllare se lo SKU appropriato viene installato quando nel file di configurazione non sono disponibili informazioni. In questo modo, le applicazioni che non dispongono di file di configurazione avranno esito negativo correttamente su SKU più piccoli rispetto all'installazione predefinita del .NET Framework. Per impostazione predefinita, `GetRequestedRuntime` non controlla se lo SKU appropriato è installato, a meno che l'attributo SKU non sia specificato nel file di configurazione `<supportedRuntime />` elemento.|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime` deve ignorare SEM_FAILCRITICALERRORS, che viene impostato chiamando la funzione [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) , e visualizzare la finestra di dialogo di errore. Per impostazione predefinita, SEM_FAILCRITICALERRORS elimina la finestra di dialogo di errore. Potrebbe essere stata ereditata da un altro processo e l'errore invisibile all'utente potrebbe essere indesiderato nello scenario.|  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [Metodo GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
