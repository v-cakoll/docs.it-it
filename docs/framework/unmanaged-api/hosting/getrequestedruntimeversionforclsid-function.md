---
title: Funzione GetRequestedRuntimeVersionForCLSID
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e00bc95dd9b54d5451da65cefbfff13395e467f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511959"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>Funzione GetRequestedRuntimeVersionForCLSID
Ottiene le informazioni sulla versione di common language runtime (CLR) appropriata per la classe con l'oggetto specificato `CLSID`.  
  
 Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `rclsid`  
 [in]  Il `CLSID` del componente.  
  
 `pVersion`  
 [out]  Un buffer che contiene la stringa del numero di versione al completamento.  
  
 `cchBuffer`  
 [in]  Le dimensioni, in caratteri "wide", del `pVersion` buffer.  
  
 `dwLength`  
 [out] La lunghezza, espressa in byte, del buffer restituito.  
  
 `dwResolutionFlags`  
 [in]  Uno dei valori CLSID_RESOLUTION_FLAGS. Sono supportati i valori seguenti:  
  
-   CLSID_RESOLUTION_DEFAULT: (0x0) specifica che deve essere utilizzato il comportamento predefinito di interoperabilità.  
  
-   CLSID_RESOLUTION_REGISTERED: (0x1) consente di specificare che deve essere ricercato nel Registro di sistema e devono essere applicati criteri shim.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|La funzione ha restituito correttamente.|  
|E_INVALIDARG|Uno dei parametri è un formato o tipo non valido.|  
|ERROR_INSUFFICIENT_BUFFER|Il `pVersion` buffer non è sufficientemente grande da contenere l'intera stringa di versione.|  
|REGDB_E_CLASSNOTREG|Nessuna classe registrata con l'oggetto specificato `CLSID`.|  
|E_POINTER|`dwLength` è null, o `cchBuffer` sia abbastanza grande da contenere la stringa di versione, ma `pVersion` è null.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
