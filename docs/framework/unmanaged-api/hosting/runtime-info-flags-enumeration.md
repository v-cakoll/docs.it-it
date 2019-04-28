---
title: Enumerazione RUNTIME_INFO_FLAGS
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9483cf8671b7d3ad5430081d93925af30b3d8368
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765154"
---
# <a name="runtimeinfoflags-enumeration"></a>Enumerazione RUNTIME_INFO_FLAGS
Contiene valori che indicano le informazioni su common language runtime (CLR) devono essere restituite.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|Indica che non devono essere incluse informazioni di directory.|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|Indica che non devono essere incluse informazioni sulla versione.|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|Indica che non deve essere visualizzata una finestra di dialogo di errore in caso di errore.|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|Indica che gli effetti della chiamata al metodo il [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) funzione con il flag SEM_FAILCRITICALERRORS deve essere sottoposto a override. Vale a dire, una finestra di dialogo di installazione deve essere visualizzato in caso di errore, anziché da eliminare.|  
|`RUNTIME_INFO_REQUEST_AMD64`|Indica una richiesta per informazioni su una versione compatibile con 64 processori AMD del runtime.|  
|`RUNTIME_INFO_REQUEST_IA64`|Indica una richiesta per informazioni su una versione compatibile con IA-64 di runtime.|  
|`RUNTIME_INFO_REQUEST_X86`|Indica una richiesta per informazioni su una versione x86 compatibile di runtime.|  
|`RUNTIME_INFO_UPGRADE_VERSION`|Indica che devono essere incluse informazioni sull'aggiornamento di versione.|  
  
## <a name="remarks"></a>Note  
 I flag di architettura di piattaforma seguenti possono essere specificato solo uno alla volta e non possono essere combinati:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
