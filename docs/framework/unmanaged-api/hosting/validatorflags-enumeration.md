---
title: Enumerazione ValidatorFlags
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
ms.openlocfilehash: 61aafb8dc99bb908fc603945ff6ea74054f812c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141427"
---
# <a name="validatorflags-enumeration"></a>Enumerazione ValidatorFlags
Contiene valori che indicano il tipo di convalida da eseguire in una chiamata al metodo [ICLRValidator:: Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|Specifica che deve essere convalidato solo il codice MSIL (Microsoft Intermediate Language) nel file eseguibile.|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|Specifica che deve essere convalidato solo il formato del file eseguibile.|  
|`VALIDATOR_EXTRA_VERBOSE`|Specifica che tutti i tipi di convalida devono essere eseguiti e segnalati in.|  
|`VALIDATOR_NOCHECK_PEFORMAT`|Specifica che il formato del file eseguibile non deve essere convalidato.|  
|`VALIDATOR_SHOW_SOURCE_LINES`|Specifica che i messaggi di errore di convalida devono includere le righe del codice sorgente che generano errori di convalida. Il valore di questo campo non è valido nella versione .NET Framework 2,0.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** IValidator. idl, IValidator. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
