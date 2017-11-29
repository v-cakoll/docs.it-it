---
title: Metodo ICLRRuntimeInfo::GetVersionString
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetVersionString
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 170b144c642463f6030e033cb5f5aaaf9755d4e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetversionstring-method"></a>Metodo ICLRRuntimeInfo::GetVersionString
Ottiene common language runtime (CLR) informazioni sulla versione associate a un determinato [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia.  
  
 Questo metodo sostituisce le funzioni seguenti:  
  
-   [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
-   [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pwzBuffer`  
 [out] La versione di compilazione di .NET Framework nel formato "v*A*. *B*[. *X*] ". *Oggetto*, *B*, e *X* sono numeri decimali che corrispondono alla versione principale, la versione secondaria e il numero di build. *X* è facoltativo. Se *X* è non è presente, non è il punto finale.  
  
> [!NOTE]
>  Questo parametro deve corrispondere al nome di directory per la versione di .NET Framework, così come viene visualizzato in C:\Windows\Microsoft.NET\Framework.  
  
 I valori di esempio sono "v 1.0.3705", "ASP.NET v 1.1.4322", "v 2.0.50727" e "v 4.0. *x*", dove *x* dipende dal numero di build installato. Si noti che il prefisso "v" è obbligatorio.  
  
 `pchBuffer`  
 [in, out] Specifica le dimensioni di `pwzBuffer` per evitare sovraccarichi del buffer. Se `pwzBuffer` è `null`, `pchBuffer` restituisce le dimensioni necessarie di `pwzBuffer` per consentire la preallocazione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pwzBuffer` o `pchBuffer` è null.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICLRRuntimeInfo (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Interfacce di Hosting CLR aggiunte in .NET Framework 4 e 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
