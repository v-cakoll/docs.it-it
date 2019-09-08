---
title: Funzione StrongNameSignatureVerificationEx
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08247c1ec5b868055e4836b3c0fb520a536374e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798925"
---
# <a name="strongnamesignatureverificationex-function"></a>Funzione StrongNameSignatureVerificationEx
Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.  
  
 Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszFilePath`  
 in Percorso del file eseguibile (exe o dll) portatile per l'assembly da verificare.  
  
 `fForceVerification`  
 in per eseguire la verifica, anche se è necessario eseguire l'override delle impostazioni del registro di sistema; in caso contrario, `false`. `true`  
  
 `pfWasVerified`  
 out Se la firma del nome sicuro è stata verificata; in caso contrario, `false`. `true` `pfWasVerified`viene anche impostato su `false` se la verifica ha avuto esito positivo a causa delle impostazioni del registro di sistema.  
  
## <a name="return-value"></a>Valore restituito  
 `true`Se la verifica ha avuto esito positivo; in caso `false`contrario,.  
  
## <a name="remarks"></a>Note  
 `StrongNameSignatureVerificationEx`fornisce una funzionalità simile alla funzione [StrongNameSignatureVerification](strongnamesignatureverification-function.md) . Tuttavia, il secondo parametro di input e il parametro di `StrongNameSignatureVerificationEx` output per sono `BOOLEAN` di tipo `DWORD`anziché.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria** Incluso come risorsa in mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [Metodo StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
