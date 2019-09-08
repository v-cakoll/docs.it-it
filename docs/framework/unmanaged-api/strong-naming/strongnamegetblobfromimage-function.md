---
title: Funzione StrongNameGetBlobFromImage
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86b99b29a85f498a6bfa0363a446bf589876bff9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799092"
---
# <a name="strongnamegetblobfromimage-function"></a>Funzione StrongNameGetBlobFromImage
Ottiene una rappresentazione binaria dell'immagine dell'assembly in corrispondenza dell'indirizzo di memoria specificato.  
  
 Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbBase`  
 in Indirizzo di memoria del manifesto dell'assembly mappato.  
  
 `dwLength`  
 in Dimensione, in byte, dell'immagine in corrispondenza `pbBase`di.  
  
 `pbBlob`  
 in Buffer che contiene la rappresentazione binaria dell'immagine.  
  
 `pcbBlob`  
 [in, out] Dimensione massima richiesta, in byte, di `pbBlob`. Al ritorno, le dimensioni effettive, in byte, `pbBlob`di.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al completamento; in caso `false`contrario,.  
  
## <a name="remarks"></a>Note  
 Se la `StrongNameGetBlobFromImage` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [Metodo StrongNameGetBlob](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
