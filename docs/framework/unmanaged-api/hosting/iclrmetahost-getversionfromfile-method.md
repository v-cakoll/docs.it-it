---
title: Metodo ICLRMetaHost::GetVersionFromFile
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 61e6cd1c83cc369e06099c72a6012eb448d6d37a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostgetversionfromfile-method"></a>Metodo ICLRMetaHost::GetVersionFromFile
Ottiene .NET Framework versione di compilazione originale un assembly (archiviato nei metadati), dato il percorso del file. Questo metodo sostituisce il [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) (funzione).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pwzFilePath`  
 [in] Il percorso completo dell'assembly.  
  
 `pwzbuffer`  
 [out] La versione di compilazione di .NET Framework archiviata nei metadati, nel formato "v*A*. *B*[. *X*] ". *Oggetto*, *B*, e *X* sono numeri decimali che corrispondono alla versione principale, la versione secondaria e il numero di build. La lunghezza di questa stringa è limitata a MAX_PATH.  
  
> [!NOTE]
>  Questo output corrisponde al nome di directory per la versione di .NET Framework, così come viene visualizzato in C:\Windows\Microsoft.NET\Framework.  
  
 I valori di esempio sono "v 1.0.3705", "ASP.NET v 1.1.4322", "v 2.0.50727" e "v 4.0. *X*", dove *X* dipende dal numero di build installato. Si noti che il prefisso "v" è obbligatorio.  
  
 `pcchBuffer`  
 [in, out] Le dimensioni di `pwzbuffer` per evitare sovraccarichi del buffer.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pwzbuffer` o `pcchBuffer` è null.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|Il buffer è troppo piccolo.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
