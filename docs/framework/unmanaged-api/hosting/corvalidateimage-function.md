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
ms.openlocfilehash: 42da5bb761ba8ce388bd41d46e8fdc4561ad0290
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136880"
---
# <a name="_corvalidateimage-function"></a>Funzione _CorValidateImage
Convalida le immagini del modulo gestito e invia una notifica al caricatore del sistema operativo dopo che sono state caricate.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ImageBase`  
 in Puntatore alla posizione iniziale dell'immagine da convalidare come codice gestito. L'immagine deve essere già caricata in memoria.  
  
 `FileName`  
 in Nome file dell'immagine.  
  
## <a name="return-value"></a>Valore restituito  
 Questa funzione restituisce i valori standard `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`e `E_FAIL`, nonché i valori seguenti.  
  
|Valore restituito|Descrizione|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|L'immagine non è valida. Questo valore dispone del valore HRESULT 0xC000007BL.|  
|`STATUS_SUCCESS`|L'immagine è valida. Questo valore dispone del valore HRESULT 0x00000000L.|  
  
## <a name="remarks"></a>Note  
 In Windows XP e versioni successive, il caricatore del sistema operativo controlla la presenza di moduli gestiti esaminando il bit di directory del descrittore COM nell'intestazione Common Object File Format (COFF). Un bit set indica un modulo gestito. Se il caricatore rileva un modulo gestito, carica MsCorEE. dll e chiama `_CorValidateImage`, che esegue le azioni seguenti:  
  
- Conferma che l'immagine è un modulo gestito valido.  
  
- Modifica il punto di ingresso nell'immagine in un punto di ingresso nel Common Language Runtime (CLR).  
  
- Per le versioni a 64 bit di Windows, modifica l'immagine in memoria mediante la trasformazione da PE32 a PE32 + format.  
  
- Torna al caricatore quando vengono caricate le immagini del modulo gestito.  
  
 Per le immagini eseguibili, il caricatore del sistema operativo chiama la funzione [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) , indipendentemente dal punto di ingresso specificato nell'eseguibile. Per le immagini di assembly DLL, il caricatore chiama la funzione [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) .  
  
 `_CorExeMain` o `_CorDllMain` esegue le azioni seguenti:  
  
- Inizializza CLR.  
  
- Individua il punto di ingresso gestito dall'intestazione CLR dell'assembly.  
  
- Inizia l'esecuzione.  
  
 Il caricatore chiama la funzione [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) quando vengono scaricate le immagini del modulo gestito. Questa funzione, tuttavia, non esegue alcuna azione. restituisce semplicemente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
