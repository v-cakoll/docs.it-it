---
title: Funzione _CorDllMain
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a02a899fd6fbffd04ef25913adb6a65ade27177
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755654"
---
# <a name="cordllmain-function"></a>\_CorDllMain (funzione)

Consente di inizializzare common language runtime (CLR), individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e inizia l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `hInst`  
 [in] L'handle di istanza del modulo caricato.  
  
 `dwReason`  
 [in] Indica il motivo per cui viene chiamata la funzione di punto di ingresso DLL. Questo parametro può essere uno dei valori seguenti: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH o DLL\_processo\_DETACH. Per una descrizione di questi valori, vedere il `DllMain` documentazione di Platform SDK.  
  
 `lpReserved`  
 [in] Non usato.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce `true` per l'esito positivo e `false` se si verifica un errore.  
  
## <a name="remarks"></a>Note  
 Questa funzione viene chiamata dal caricatore del sistema operativo per gli assembly DLL. Per gli assembly eseguibile, il caricatore chiama il [ \_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funzione.  
  
 Il caricatore del sistema operativo chiama questo metodo sia il punto di ingresso specificato nel file DLL.  
  
Il `_CorDllMain` funzione viene chiamata direttamente dal caricatore del sistema operativo.
  
 Per altre informazioni, vedere la sezione osservazioni nel [ \_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) argomento.  
  
## <a name="requirements"></a>Requisiti  

 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
