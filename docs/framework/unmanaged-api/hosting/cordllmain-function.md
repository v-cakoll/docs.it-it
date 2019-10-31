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
ms.openlocfilehash: f60f159ab4770023cee7123b39109040243e1ccd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136971"
---
# <a name="_cordllmain-function"></a>\_funzione CorDllMain

Inizializza il Common Language Runtime (CLR), individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e avvia l'esecuzione.  
  
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
 in Handle dell'istanza del modulo caricato.  
  
 `dwReason`  
 in Indica il motivo per cui viene chiamata la funzione del punto di ingresso della DLL. Questo parametro può essere uno dei valori seguenti: DLL\_PROCESS_ATTACH, DLL\_THREAD\_collegamento, DLL\_THREAD\_collegamento o DLL\_processo\_SCOLLEGAmento. Per una descrizione di questi valori, vedere la documentazione di `DllMain` in Platform SDK.  
  
 `lpReserved`  
 in Inutilizzati.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce `true` per l'esito positivo e `false` se si verifica un errore.  
  
## <a name="remarks"></a>Note  
 Questa funzione viene chiamata dal caricatore del sistema operativo per gli assembly DLL. Per gli assembly eseguibili, il caricatore chiama invece la [\_funzione CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) .  
  
 Il caricatore del sistema operativo chiama questo metodo indipendentemente dal punto di ingresso specificato nel file DLL.  
  
La funzione `_CorDllMain` viene chiamata direttamente dal caricatore del sistema operativo.
  
 Per ulteriori informazioni, vedere la sezione osservazioni nell'argomento [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Requisiti  

 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
