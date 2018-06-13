---
title: Metodo IValidator::Validate
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf2c343db459879ca95372e104aee68b22dee6b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440617"
---
# <a name="ivalidatorvalidate-method"></a>Metodo IValidator::Validate
Convalida lo specificato eseguibile portabile (PE) o un file Microsoft intermediate language (MSIL).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `veh`  
 [in] Un puntatore a un `IVEHandler` istanza che gestisce gli errori di convalida.  
  
 `pAppDomain`  
 [in] Un puntatore per il dominio dell'applicazione in cui viene caricato il file.  
  
 `ulFlags`  
 [in] Combinazione bit per bit di [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) valori, che indica le convalide che devono essere eseguite.  
  
 `ulMaxError`  
 [in] Il numero massimo di errori consentiti prima di disattivare la convalida.  
  
 `token`  
 [in] Non usato.  
  
 `fileName`  
 [in] Stringa che specifica il nome del file da convalidare.  
  
 `pe`  
 [in] Puntatore al buffer di memoria in cui è archiviato il file.  
  
 `ulSize`  
 [in] Le dimensioni in byte, del file da convalidare.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** IValidator. idl, IValidator.h  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 
