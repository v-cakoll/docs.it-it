---
title: Interfaccia IAssemblyCacheItem
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193604068e379d62107b25f2bc348cd7c8bc6e98
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796713"
---
# <a name="iassemblycacheitem-interface"></a>Interfaccia IAssemblyCacheItem
Rappresenta un singolo assembly nel Global Assembly Cache.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo AbortItem](iassemblycacheitem-abortitem-method.md)|Consente all'assembly nel Global Assembly Cache di eseguire operazioni di pulizia prima del rilascio.|  
|[Metodo Commit](iassemblycacheitem-commit-method.md)|Consente di eseguire il commit del riferimento all'assembly memorizzato nella cache nella memoria.|  
|[Metodo CreateStream](iassemblycacheitem-createstream-method.md)|Crea un flusso con il nome e il formato specificati.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
- [Global Assembly Cache](../../app-domains/gac.md)
- [Interfaccia IAssemblyCache](iassemblycache-interface.md)
