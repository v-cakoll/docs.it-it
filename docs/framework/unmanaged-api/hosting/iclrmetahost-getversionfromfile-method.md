---
title: Metodo ICLRMetaHost::GetVersionFromFile
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
ms.openlocfilehash: 40efc256dde13d645d43f50bb574d73b5668919c
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703734"
---
# <a name="iclrmetahostgetversionfromfile-method"></a>Metodo ICLRMetaHost::GetVersionFromFile
Ottiene la versione di compilazione .NET Framework originale di un assembly (archiviata nei metadati), dato il percorso del file. Questo metodo sostituisce la funzione [GetFileVersion](getfileversion-function.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzFilePath`  
 in Percorso completo del file di assembly.  
  
 `pwzbuffer`  
 out La versione di compilazione .NET Framework archiviata nei metadati, nel formato "v*a*. *B*[.* X*] ". *A*, *B*e *X* sono numeri decimali che corrispondono alla versione principale, alla versione secondaria e al numero di Build. La lunghezza di questa stringa è limitata a MAX_PATH.  
  
> [!NOTE]
> Questo output corrisponde al nome della directory per la versione .NET Framework, così come viene visualizzato in C:\Windows\Microsoft.NET\Framework.  
  
 I valori di esempio sono "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" e "v 4.0. *X*", dove *x* dipende dal numero di build installato. Si noti che il prefisso "v" è obbligatorio.  
  
 `pcchBuffer`  
 [in, out] Dimensioni di `pwzbuffer` per evitare sovraccarichi del buffer.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pwzbuffer` o `pcchBuffer` è null.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|Il buffer è troppo piccolo.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRMetaHost](iclrmetahost-interface.md)
- [Hosting](index.md)
