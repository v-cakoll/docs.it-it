---
title: Metodo ICLRRuntimeInfo::GetVersionString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c80b85171ac9dab270a267cf2dd33a9f1c23d60
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650304"
---
# <a name="iclrruntimeinfogetversionstring-method"></a>Metodo ICLRRuntimeInfo::GetVersionString
Ottiene common language runtime (CLR) informazioni sulla versione associati con un determinato [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia.  
  
 Questo metodo sostituisce le funzioni seguenti:  
  
- [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
- [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzBuffer`  
 [out] La versione di compilazione di .NET Framework nel formato "v*un'*. *B*[. *X*] ". *Oggetto*, *B*, e *X* sono numeri decimali che corrispondono alla versione principale, la versione secondaria e il numero di build. *X* è facoltativo. Se *X* è non è presente, non è previsto alcun periodo finale.  
  
> [!NOTE]
>  Questo parametro deve corrispondere al nome di directory per la versione di .NET Framework, così come appare sotto C:\Windows\Microsoft.NET\Framework.  
  
 I valori di esempio sono "v1.0.3705", "v1.1.4322", "v2.0.50727" e "v4.0. *x*", dove *x* dipende dal numero di build installato. Si noti che il prefisso "v" è obbligatorio.  
  
 `pchBuffer`  
 [in, out] Specifica la dimensione del `pwzBuffer` per evitare i sovraccarichi del buffer. Se `pwzBuffer` viene `null`, `pchBuffer` restituisce la dimensione necessaria della `pwzBuffer` per consentire la preallocazione.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pwzBuffer` o `pchBuffer` è null.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
