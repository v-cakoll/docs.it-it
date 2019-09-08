---
title: Funzione StrongNameGetPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae87ebd0b8225f14ca029fac80528d47f5a866cf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799068"
---
# <a name="strongnamegetpublickey-function"></a>Funzione StrongNameGetPublicKey
Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata. È possibile specificare la coppia di chiavi come nome del contenitore di chiavi all'interno di un provider del servizio di crittografia (CSP) o come raccolta di byte non elaborata.  
  
 Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szKeyContainer`  
 in Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata. Se `pbKeyBlob` è null, `szKeyContainer` è necessario specificare un contenitore valido all'interno del CSP. In questo caso, `StrongNameGetPublicKey` estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.  
  
 Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nel BLOB (Binary Large Object) della chiave.  
  
 Le chiavi devono essere chiavi di firma Rivest-Shamir-Adleman (RSA) a 1024 bit. Al momento non sono supportati altri tipi di chiavi.  
  
 `pbKeyBlob`  
 in Puntatore alla coppia di chiavi pubblica/privata. Questa coppia è nel formato creato dalla funzione Win32 `CryptExportKey` . Se `pbKeyBlob` è null, si presuppone che il contenitore `szKeyContainer` di chiavi specificato da contenga la coppia di chiavi.  
  
 `cbKeyBlob`  
 in Dimensione, in byte, di `pbKeyBlob`.  
  
 `ppbPublicKeyBlob`  
 out BLOB della chiave pubblica restituito. Il `ppbPublicKeyBlob` parametro viene allocato dal Common Language Runtime e restituito al chiamante. Il chiamante deve liberare la memoria tramite la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .  
  
 `pcbPublicKeyBlob`  
 out Dimensioni del BLOB della chiave pubblica restituito.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al completamento; in caso `false`contrario,.  
  
## <a name="remarks"></a>Note  
 La chiave pubblica è contenuta in una struttura [PublicKeyBlob](publickeyblob-structure.md) .  
  
 Se la `StrongNameGetPublicKey` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [Metodo StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
- [Struttura PublicKeyBlob](publickeyblob-structure.md)
