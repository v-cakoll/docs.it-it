---
title: Enumerazione ECustomDumpFlavor
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
ms.openlocfilehash: 9b4c1187945b4c243375a3096c3a8a3b22599aef
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616281"
---
# <a name="ecustomdumpflavor-enumeration"></a>Enumerazione ECustomDumpFlavor
Contiene valori che indicano quali elementi includere in un subset personalizzato di un dump dell'heap quando si segnalano errori.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Description|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|Specifica che il dump dell'heap personalizzato deve iniziare come minidump e includere dati aggiuntivi specificati da qualsiasi istanza di [CustomDumpItem](customdumpitem-structure.md) passata allo stesso metodo.|  
|`DUMP_FLAVOR_NonHeapCLRState`|Specifica che il dump dell'heap personalizzato deve raccogliere tutti i dati sullo stato della fase di esecuzione che non sono stati allocati in modo dinamico.|  
  
## <a name="remarks"></a>Osservazioni  
 Un parametro di tipo `ECustomDumpFlavor` viene passato al metodo [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md)
- [Interfaccia ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)
- [Enumerazioni di hosting](hosting-enumerations.md)
