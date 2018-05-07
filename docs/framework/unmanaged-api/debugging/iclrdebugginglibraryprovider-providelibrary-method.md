---
title: Metodo ICLRDebuggingLibraryProvider::ProvideLibrary
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0644258eb1622f388f55d0657c8922079fe4dc1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a>Metodo ICLRDebuggingLibraryProvider::ProvideLibrary
Ottiene un provider di librerie di interfaccia di callback che consente a common language runtime (CLR) librerie di debug specifiche della versione di individuare e caricare su richiesta.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pwszFilename`  
 [in] Il nome del modulo richiesto.  
  
 `dwTimestamp`  
 [in] Timestamp data archiviato nell'intestazione COFF file del file PE.  
  
 `pLibraryProvider`  
 [in] Il `SizeOfImage` campo archiviato nell'intestazione COFF file facoltativo del file PE.  
  
 `hModule`  
 [out] L'handle del modulo richiesto.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 `ProvideLibrary` consente al debugger di fornire i moduli che sono necessari per il debug di file specifici di CLR, ad esempio mscordbi. dll e mscordacwks. dll. Gli handle del modulo devono rimanere validi fino a quando una chiamata al [ICLRDebugging:: CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) metodo indica che possono essere liberati, a quel punto è responsabilità del chiamante liberare l'handle.  
  
 Il debugger può utilizzare qualsiasi strumento disponibile per individuare oppure ottenere il modulo di debug.  
  
> [!IMPORTANT]
>  Questa funzionalità consente al chiamante di API fornire i moduli che contengono codice eseguibile e potenzialmente dannoso. Come misura di sicurezza, il chiamante non deve utilizzare `ProvideLibrary` per distribuire qualsiasi codice che non è disposto a eseguire se stesso.  
>   
>  Se viene rilevato un problema serio di protezione in una libreria già rilasciata, ad esempio mscordaccore.dll o mscordacwks.dll, è possibile applicare patch lo shim per riconoscere le versioni dei file non valide. Lo shim, eseguire le richieste per le versioni dei file di patch e rifiutare le versioni non sicure se vengono forniti in risposta a qualsiasi richiesta. Ciò può verificarsi solo se l'utente è stato aggiornato a una nuova versione dello shim. Le versioni senza patch rimane vulnerabile.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
