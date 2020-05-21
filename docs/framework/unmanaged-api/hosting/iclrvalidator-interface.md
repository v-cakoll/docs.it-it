---
title: Interfaccia ICLRValidator
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
ms.openlocfilehash: e071f9cba7e991c59bf697647e0e4badea57573a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762045"
---
# <a name="iclrvalidator-interface"></a>Interfaccia ICLRValidator
Fornisce metodi per convalidare immagini PE (Portable Executable) e segnalare errori di convalida.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo FormatEventInfo](iclrvalidator-formateventinfo-method.md)|Ottiene un messaggio dettagliato sull'errore di convalida specificato.|  
|[Metodo Validate](iclrvalidator-validate-method.md)|Convalida il file eseguibile portatile o MSIL (Microsoft Intermediate Language) nel file specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** IValidator. idl, IValidator. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
- [Coclasse CLRRuntimeHost](clrruntimehost-coclass.md)
