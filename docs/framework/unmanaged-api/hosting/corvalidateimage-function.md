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
ms.openlocfilehash: 3a6da0e845fa50d090cdf0808b211a5806c40961
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178222"
---
# <a name="_corvalidateimage-function"></a>Funzione _CorValidateImage
Convalida le immagini dei moduli gestiti e notifica al caricatore del sistema operativo dopo che sono state caricate.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ImageBase`  
 [in] Puntatore alla posizione iniziale dell'immagine da convalidare come codice gestito. L'immagine deve essere già caricata in memoria.  
  
 `FileName`  
 [in] Nome file dell'immagine.  
  
## <a name="return-value"></a>Valore restituito  
 Questa funzione restituisce `E_INVALIDARG` `E_OUTOFMEMORY`i `E_UNEXPECTED`valori `E_FAIL`standard , , e , nonché i valori seguenti.  
  
|Valore restituito|Descrizione|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|L'immagine non è valida. Questo valore ha HRESULT 0xC000007BL.|  
|`STATUS_SUCCESS`|L'immagine è valida. Questo valore ha HRESULT 0x00000000L.|  
  
## <a name="remarks"></a>Osservazioni  
 In Windows XP e versioni successive, il caricatore del sistema operativo verifica la presenza di moduli gestiti esaminando il bit directory dei descrittori COM nell'intestazione COFF (Common Object File Format). Un bit set indica un modulo gestito. Se il caricatore rileva un modulo gestito, carica MsCorEE.dll e chiama `_CorValidateImage`, che esegue le seguenti azioni:  
  
- Conferma che l'immagine è un modulo gestito valido.  
  
- Modifica il punto di ingresso nell'immagine in un punto di ingresso in Common Language Runtime (CLR).  
  
- Per le versioni a 64 bit di Windows, modifica l'immagine presente in memoria trasformandola dal formato PE32 al formato PE32.  
  
- Torna al caricatore quando vengono caricate le immagini dei moduli gestiti.  
  
 Per le immagini eseguibili, il caricatore del sistema operativo chiama quindi la funzione [_CorExeMain,](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) indipendentemente dal punto di ingresso specificato nell'eseguibile. Per le immagini di assembly DLL, il caricatore chiama la funzione [_CorDllMain.](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
  
 `_CorExeMain`o `_CorDllMain` esegue le seguenti azioni:  
  
- Inizializza CLR.  
  
- Individua il punto di ingresso gestito dall'intestazione CLR dell'assembly.  
  
- Inizia l'esecuzione.  
  
 Il caricatore chiama la funzione [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) quando le immagini dei moduli gestiti vengono scaricate. Tuttavia, questa funzione non esegue alcuna azione; ritorna e basta.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
