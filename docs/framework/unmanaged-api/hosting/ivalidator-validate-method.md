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
ms.openlocfilehash: 688abd210cca193bf03c40f000b74ecb66eb8ede
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008547"
---
# <a name="ivalidatorvalidate-method"></a>Metodo IValidator::Validate
Convalida il file eseguibile portabile (PE) o il file MSIL (Microsoft Intermediate Language) specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="parameters"></a>Parametri  
 `veh`  
 in Puntatore a un' `IVEHandler` istanza di che gestisce gli errori di convalida.  
  
 `pAppDomain`  
 in Puntatore al dominio applicazione in cui viene caricato il file.  
  
 `ulFlags`  
 in Combinazione bit per bit di valori [ValidatorFlags](validatorflags-enumeration.md) , che indica le convalide da eseguire.  
  
 `ulMaxError`  
 in Numero massimo di errori da consentire prima di uscire dalla convalida.  
  
 `token`  
 [in] Non utilizzato.  
  
 `fileName`  
 in Stringa che specifica il nome del file da convalidare.  
  
 `pe`  
 in Puntatore al buffer di memoria in cui è archiviato il file.  
  
 `ulSize`  
 in Dimensione, in byte, del file da convalidare.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** IValidator. idl, IValidator. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
