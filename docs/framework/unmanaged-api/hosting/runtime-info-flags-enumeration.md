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
ms.openlocfilehash: 9d505b917c343c40c7fa2a7aecf3466578ae0a8d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936633"
---
# <a name="runtime_info_flags-enumeration"></a>Enumerazione RUNTIME_INFO_FLAGS
Contiene valori che indicano quali informazioni relative al Common Language Runtime (CLR) devono essere restituite.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|Indica che le informazioni della directory non devono essere incluse.|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|Indica che le informazioni sulla versione non devono essere incluse.|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|Indica che non è possibile visualizzare una finestra di dialogo di errore in caso di errore.|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|Indica che è necessario eseguire l'override degli effetti della chiamata della funzione [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) con il flag SEM_FAILCRITICALERRORS. Ovvero una finestra di dialogo di installazione dovrebbe essere visualizzata in caso di errore, anziché essere eliminato.|  
|`RUNTIME_INFO_REQUEST_AMD64`|Indica una richiesta di informazioni su una versione compatibile con AMD-64 del runtime.|  
|`RUNTIME_INFO_REQUEST_IA64`|Indica una richiesta di informazioni su una versione compatibile con IA-64 del runtime.|  
|`RUNTIME_INFO_REQUEST_X86`|Indica una richiesta di informazioni su una versione compatibile x86 del runtime.|  
|`RUNTIME_INFO_UPGRADE_VERSION`|Indica che devono essere incluse le informazioni relative all'aggiornamento della versione.|  
  
## <a name="remarks"></a>Note  
 I flag di architettura della piattaforma seguenti possono essere specificati solo uno alla volta e non possono essere combinati:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
