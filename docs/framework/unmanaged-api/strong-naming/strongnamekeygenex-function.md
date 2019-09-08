---
title: Funzione StrongNameKeyGenEx
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9ab908866402bd7a883114466f32921321a5ee6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799008"
---
# <a name="strongnamekeygenex-function"></a>Funzione StrongNameKeyGenEx
Genera una nuova coppia di chiavi pubblica/privata con la dimensione della chiave specificata, per l'uso del nome sicuro.  
  
 Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszKeyContainer`  
 in Nome del contenitore di chiavi richiesto. `wszKeyContainer`deve essere una stringa non vuota o null per generare un nome temporaneo.  
  
 `dwFlags`  
 in Specifica se lasciare la chiave registrata. Sono supportati i valori seguenti:  
  
- 0x00000000: viene usato `wszKeyContainer` quando è null per generare un nome del contenitore di chiavi temporaneo.  
  
- 0x00000001 (`SN_LEAVE_KEY`): specifica che la chiave deve essere lasciata registrata.  
  
 `dwKeySize`  
 in Dimensioni richieste della chiave, in bit.  
  
 `ppbKeyBlob`  
 out Coppia di chiavi pubblica/privata restituita.  
  
 `pcbKeyBlob`  
 out Dimensione, in byte, di `ppbKeyBlob`.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al completamento; in caso `false`contrario,.  
  
## <a name="remarks"></a>Note  
 Per la firma di un assembly con un `dwKeySize` nome sicuro, le versioni di .NET Framework 1,0 e 1,1 richiedono un valore di 1024 bit. la versione 2,0 aggiunge i supporti per le chiavi a 2048 bit.  
  
 Dopo che la chiave è stata recuperata, è necessario chiamare la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) per rilasciare la memoria allocata.  
  
 Se la `StrongNameKeyGenEx` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [Metodo StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
