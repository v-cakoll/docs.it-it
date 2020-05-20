---
title: Interfaccia ICLRErrorReportingManager
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
ms.openlocfilehash: dbe4129cf4160a1a9b31bc6f418095ea4b392d57
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616996"
---
# <a name="iclrerrorreportingmanager-interface"></a>Interfaccia ICLRErrorReportingManager
Fornisce metodi che consentono all'host di configurare dump di stack personalizzati per la segnalazione degli errori.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md)|Specifica la configurazione dei dump dello stack personalizzati per la segnalazione degli errori.|  
|[Metodo EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md)|Cancella la configurazione del dump dello stack personalizzato impostata da una chiamata precedente a `BeginCustomDump` .|  
|[Metodo GetBucketParametersForCurrentException](iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Ottiene il bucket Watson per l'eccezione corrente nel thread chiamante.|  
  
## <a name="remarks"></a>Osservazioni  
 Il `BeginCustomDump` metodo imposta la configurazione del dump dello stack personalizzato. Il `EndCustomDump` metodo cancella la configurazione del dump dello stack personalizzato e libera qualsiasi stato associato. Deve essere chiamato dopo il completamento del dump personalizzato.  
  
> [!IMPORTANT]
> La mancata chiamata `EndCustomDump` causa la perdita della memoria.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md)
- [Interfacce di hosting](hosting-interfaces.md)
