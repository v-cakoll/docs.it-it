---
title: Funzione StrongNameKeyGen
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f062f47790136e8cd39c6751b7c75eef660c2b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799143"
---
# <a name="strongnamekeygen-function"></a>Funzione StrongNameKeyGen
Crea una nuova coppia di chiavi pubblica/privata per l'uso come nome sicuro.  
  
 Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
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
  
 `ppbKeyBlob`  
 out Coppia di chiavi pubblica/privata restituita.  
  
 `pcbKeyBlob`  
 out Dimensione, in byte, di `ppbKeyBlob`.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al completamento; in caso `false`contrario,.  
  
## <a name="remarks"></a>Note  
 La `StrongNameKeyGen` funzione crea una chiave a 1024 bit. Dopo che la chiave è stata recuperata, è necessario chiamare la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) per rilasciare la memoria allocata.  
  
 Se la `StrongNameKeyGen` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [Metodo StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
