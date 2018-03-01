---
title: Funzione _CorValidateImage
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03deb62a84a1e9c6cee898fe0023c34b8c538ece
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parametri  
 `ImageBase`  
 [in] Puntatore alla posizione iniziale dell'immagine per convalidare come codice gestito. L'immagine deve essere già caricata in memoria.  
  
 `FileName`  
 [in] Il nome file dell'immagine.  
  
## <a name="return-value"></a>Valore restituito  
 Questa funzione restituisce i valori standard `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, e `E_FAIL`, nonché i valori seguenti.  
  
|Valore restituito|Descrizione|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|L'immagine non è valido. Questo valore HRESULT 0xC000007BL.|  
|`STATUS_SUCCESS`|L'immagine è valido. Questo valore HRESULT 0x00000000L.|  
  
## <a name="remarks"></a>Note  
 In Windows XP e versioni successive, il caricatore del sistema operativo controlla la presenza di moduli gestiti esaminando il bit di Directory descrittore COM nell'intestazione common object file formato COFF (). Un bit impostato indica un modulo gestito. Se il caricatore rileva un modulo gestito, carica MsCorEE.dll e chiama `_CorValidateImage`, che esegue le azioni seguenti:  
  
-   Conferma che l'immagine è un modulo gestito valido.  
  
-   Modifica il punto di ingresso nell'immagine per un punto di ingresso in common language runtime (CLR).  
  
-   Per le versioni a 64 bit di Windows, modifica l'immagine presente in memoria trasformandola dal formato PE32 al formato PE32 +.  
  
-   Restituisce un valore per il caricatore quando le immagini dei moduli gestiti caricati.  
  
 Per le immagini eseguibili, il caricatore del sistema operativo chiama quindi il [CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funzione, indipendentemente dal punto di ingresso specificato nel file eseguibile. Per le immagini di assembly DLL, il caricatore chiama la [CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) (funzione).  
  
 `_CorExeMain`o `_CorDllMain` esegue le azioni seguenti:  
  
-   Inizializza il CLR.  
  
-   Individua il punto di ingresso gestito dall'intestazione CLR dell'assembly.  
  
-   Inizia l'esecuzione.  
  
 Le chiamate del caricatore di [CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) funzione quando gestito immagini vengono scaricate. Tuttavia, questa funzione non esegue alcuna operazione. Restituisce solo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
