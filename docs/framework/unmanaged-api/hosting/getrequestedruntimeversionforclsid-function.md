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
ms.openlocfilehash: ce0c6307defd93dcf63ac4e9051fc798041475f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127049"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>Funzione GetRequestedRuntimeVersionForCLSID
Ottiene le informazioni sulla versione di Common Language Runtime (CLR) appropriate per la classe con la `CLSID`specificata.  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `rclsid`  
 in  `CLSID` del componente.  
  
 `pVersion`  
 out  Buffer che contiene la stringa del numero di versione al completamento dell'operazione.  
  
 `cchBuffer`  
 in  Dimensione, in caratteri wide, del buffer `pVersion`.  
  
 `dwLength`  
 out Lunghezza, in byte, del buffer restituito.  
  
 `dwResolutionFlags`  
 in  Uno dei valori CLSID_RESOLUTION_FLAGS. Sono supportati i valori seguenti:  
  
- CLSID_RESOLUTION_DEFAULT: (0x0) specifica che deve essere utilizzato il comportamento di interoperabilità predefinito.  
  
- CLSID_RESOLUTION_REGISTERED: (0x1) specifica che deve essere eseguita la ricerca nel registro di sistema e applicare i criteri shim.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|La funzione ha restituito correttamente.|  
|E_INVALIDARG|Il tipo o il formato di uno dei parametri non è valido.|  
|ERROR_INSUFFICIENT_BUFFER|Il buffer di `pVersion` non è sufficientemente grande da mantenere l'intera stringa di versione.|  
|REGDB_E_CLASSNOTREG|Non è stata registrata alcuna classe con la `CLSID`specificata.|  
|E_POINTER|`dwLength` è null o `cchBuffer` è sufficientemente grande per poter essere contenuta nella stringa di versione, ma `pVersion` è null.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
