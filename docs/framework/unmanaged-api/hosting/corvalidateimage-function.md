---
title: Funzione _CorValidateImage
ms.date: 03/30/2017
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c6d3b50cb3589dcd98c53e1abf0ce2be144d8f9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501994"
---
# <a name="corvalidateimage-function"></a>Funzione _CorValidateImage
Convalida delle immagini dei moduli gestiti e notifica al caricatore del sistema operativo dopo che sono stati caricati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ImageBase`  
 [in] Un puntatore alla posizione iniziale dell'immagine per convalidare come codice gestito. L'immagine deve essere già caricata in memoria.  
  
 `FileName`  
 [in] Nome file dell'immagine.  
  
## <a name="return-value"></a>Valore restituito  
 Questa funzione restituisce i valori standard `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, e `E_FAIL`, nonché i valori seguenti.  
  
|Valore restituito|Descrizione|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|L'immagine non è valido. Questo valore HRESULT 0xC000007BL.|  
|`STATUS_SUCCESS`|L'immagine è valida. Questo valore HRESULT 0x00000000L.|  
  
## <a name="remarks"></a>Note  
 In Windows XP e versioni successive, il caricatore del sistema operativo cerca moduli gestiti esaminando il bit COM descrittore Directory nell'intestazione common object file formato COFF (). Un bit impostato indica un modulo gestito. Se il caricatore rileva un modulo gestito, carica Mscoree. dll e chiamate `_CorValidateImage`, che consente di eseguire le azioni seguenti:  
  
-   Conferma che l'immagine è un modulo gestito valido.  
  
-   Modifica il punto di ingresso nell'immagine a un punto di ingresso in common language runtime (CLR).  
  
-   Per le versioni a 64 bit di Windows, consente di modificare l'immagine che si trova in memoria e trasformato dal formato PE32 al formato PE32 +.  
  
-   Notifica al caricatore quando vengono caricate le immagini dei moduli gestiti.  
  
 Per le immagini eseguibili, il caricatore del sistema operativo chiama quindi il [CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funzione, indipendentemente dal punto di ingresso specificato nel file eseguibile. Per le immagini di assembly DLL, il caricatore chiama il [CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) (funzione).  
  
 `_CorExeMain` o `_CorDllMain` esegue le azioni seguenti:  
  
-   Inizializza CLR.  
  
-   Individua il punto di ingresso gestito da un'intestazione CLR dell'assembly.  
  
-   Inizia l'esecuzione.  
  
 Le chiamate del caricatore il [CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) funzionino quando vengono gestiti vengono scaricate immagini dei moduli. Tuttavia, questa funzione non esegue alcuna operazione. Restituisce solo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
