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
ms.openlocfilehash: 3dd1038fdc8b22b99e1c8c7b753b46b9ce877355
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496443"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a>Metodo ICLRDebuggingLibraryProvider::ProvideLibrary
Ottiene un provider di librerie di interfaccia di callback che consente a common language runtime (CLR) le librerie di debug specifiche della versione di individuare e caricare su richiesta.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwszFilename`  
 [in] Nome del modulo richiesto.  
  
 `dwTimestamp`  
 [in] Timestamp data archiviato nell'intestazione COFF dei file PE.  
  
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
 `ProvideLibrary` consente al debugger fornire i moduli necessari per il debug di file specifici di CLR, ad esempio mscordbi. dll e mscordacwks. Gli handle del modulo devono rimanere validi fino a una chiamata per il [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) metodo indica che essi possono essere liberate, a questo punto è responsabilità del chiamante liberare l'handle.  
  
 Il debugger può usare qualsiasi strumento disponibile per individuare oppure ottenere il modulo di debug.  
  
> [!IMPORTANT]
>  Questa funzionalità consente al chiamante di API fornire i moduli che contengono codice eseguibile e potenzialmente dannoso. Come precauzione di sicurezza, il chiamante non deve utilizzare `ProvideLibrary` per distribuire qualsiasi codice che non è disposto da eseguire se stesso.  
>   
>  Se viene rilevato un problema serio di protezione in una libreria già rilasciata, ad esempio mscordbi. dll o mscordacwks, lo shim può essere corretto in modo che riconosca le versioni dei file non valide. Lo shim può quindi inviare le richieste per le versioni con patch dei file e rifiutare le versioni non sicure, se vengono forniti in risposta a tutte le richieste. Ciò può verificarsi solo se l'utente è applicata una patch a una nuova versione dello shim. Le versioni patch rimane vulnerabile.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
