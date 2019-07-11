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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5f38231eb6a5911527c21ee3304fc77cfcf8e90
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776527"
---
# <a name="validatorflags-enumeration"></a>Enumerazione ValidatorFlags
Contiene valori che indicano il tipo di convalida che deve essere eseguita in una chiamata per il [ICLRValidator](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) (metodo).  
  
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
|`VALIDATOR_CHECK_ILONLY`|Specifica che solo il Microsoft intermediate language (MSIL) nel file eseguibile deve essere convalidato.|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|Specifica che solo il formato del file eseguibile deve essere convalidato.|  
|`VALIDATOR_EXTRA_VERBOSE`|Specifica che tutti i tipi di convalida devono essere eseguiti e segnalati in.|  
|`VALIDATOR_NOCHECK_PEFORMAT`|Specifica che il formato del file eseguibile non deve essere convalidato.|  
|`VALIDATOR_SHOW_SOURCE_LINES`|Specifica che i messaggi di errore di convalida devono includere le righe di codice sorgente che generano errori di convalida. Questo valore del campo non è valido in .NET Framework versione 2.0.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** IValidator. idl, IValidator. H  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
