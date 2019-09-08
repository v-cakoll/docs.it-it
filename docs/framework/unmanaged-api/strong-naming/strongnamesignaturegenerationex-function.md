---
title: Funzione StrongNameSignatureGenerationEx
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89398c221dcf9d6f89027f15da4062bc7ed67e3f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798979"
---
# <a name="strongnamesignaturegenerationex-function"></a>Funzione StrongNameSignatureGenerationEx
Genera una firma con nome sicuro per l'assembly specificato, in base ai flag specificati.  
  
 Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszFilePath`  
 in Percorso del file contenente il manifesto dell'assembly per il quale verrà generata la firma con nome sicuro.  
  
 `wszKeyContainer`  
 in Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.  
  
 Se `pbKeyBlob` è null, `wszKeyContainer` è necessario specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP). In questo caso, la coppia di chiavi archiviata nel contenitore viene usata per firmare il file.  
  
 Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nel BLOB (Binary Large Object) della chiave.  
  
 `pbKeyBlob`  
 in Puntatore alla coppia di chiavi pubblica/privata. Questa coppia è nel formato creato dalla funzione Win32 `CryptExportKey` . Se `pbKeyBlob` è null, si presuppone che il contenitore `wszKeyContainer` di chiavi specificato da contenga la coppia di chiavi.  
  
 `cbKeyBlob`  
 in Dimensione, in byte, di `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 out Puntatore alla posizione in cui il Common Language Runtime restituisce la firma. Se `ppbSignatureBlob` è null, il runtime archivia la firma nel file specificato da `wszFilePath`.  
  
 Se `ppbSignatureBlob` non è null, il Common Language Runtime alloca spazio per la restituzione della firma. Il chiamante deve liberare questo spazio usando la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .  
  
 `pcbSignatureBlob`  
 out Dimensione, in byte, della firma restituita.  
  
 `dwFlags`  
 in Uno o più dei valori seguenti:  
  
- `SN_SIGN_ALL_FILES`(0x00000001): Ricalcola tutti gli hash per i moduli collegati.  
  
- `SN_TEST_SIGN`(0x00000002)-test-firma l'assembly.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al completamento; in caso `false`contrario,.  
  
## <a name="remarks"></a>Note  
 Specificare null per `wszFilePath` per calcolare le dimensioni della firma senza creare la firma.  
  
 La firma può essere archiviata direttamente nel file o restituita al chiamante.  
  
 Se `SN_SIGN_ALL_FILES` viene specificato, ma non è inclusa una chiave pubblica ( `pbKeyBlob` sia `wszFilePath` che sono null), gli hash per i moduli collegati vengono ricalcolati, ma l'assembly non viene firmato nuovamente.  
  
 Se `SN_TEST_SIGN` si specifica, l'intestazione Common Language Runtime non viene modificata per indicare che l'assembly è firmato con un nome sicuro.  
  
 Se la `StrongNameSignatureGenerationEx` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [Metodo StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
