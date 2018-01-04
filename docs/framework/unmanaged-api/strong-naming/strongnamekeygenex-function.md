---
title: Funzione StrongNameKeyGenEx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyGenEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyGenEx
helpviewer_keywords: StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae564f7c4e8333e33b2f2f6229034c3a1396a687
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamekeygenex-function"></a>Funzione StrongNameKeyGenEx
Genera una nuova coppia di chiavi pubblica/privata con la dimensione della chiave specificata, per l'utilizzo con nome sicuro.  
  
 Questa funzione è stata deprecata. Utilizzare il [:: StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `wszKeyContainer`  
 [in] Il nome di contenitore di chiavi richiesto. `wszKeyContainer`deve essere una stringa non vuota o null per generare un nome temporaneo.  
  
 `dwFlags`  
 [in] Specifica se mantenere la chiave registrata. Sono supportati i seguenti valori:  
  
-   0x00000000 - utilizzato quando `wszKeyContainer` è null per generare un nome di contenitore di chiavi temporaneo.  
  
-   0x00000001 (`SN_LEAVE_KEY`)-specifica che la chiave deve essere registrata a sinistra.  
  
 `dwKeySize`  
 [in] La dimensione richiesta della chiave in bit.  
  
 `ppbKeyBlob`  
 [out] La coppia di chiavi pubblica/privata restituita.  
  
 `pcbKeyBlob`  
 [out] Le dimensioni, in byte, di `ppbKeyBlob`.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al termine dell'esecuzione; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Le versioni di .NET Framework 1.0 e 1.1 richiedono un `dwKeySize` pari a 1024 bit per firmare un assembly con un nome sicuro; versione 2.0 include il supporto per le chiavi a 2048 bit.  
  
 Dopo il recupero della chiave, è necessario chiamare il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) funzione per rilasciare la memoria allocata.  
  
 Se il `StrongNameKeyGenEx` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [Metodo StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
