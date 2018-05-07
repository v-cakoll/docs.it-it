---
title: Struttura CoreClrDebugProcInfo
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9d4b27ca0bf454b42f15b849008e5a3019bb09a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="coreclrdebugprocinfo-structure"></a>Struttura CoreClrDebugProcInfo
Rappresenta un processo in esecuzione in un computer remoto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`m_dwPID`|Identificatore di processo assegnato dal sistema operativo.|  
|`m_dwInternalID`|Identificatore di processo assegnato dal proxy di debug remoto in esecuzione sul computer di destinazione. Questo identificatore esegue il riciclo meno frequentemente rispetto all'identificatore del sistema operativo.|  
|`m_wszName`|Riga di comando del processo. Questo membro può essere troncato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** coreclrremotedebugginginterfaces. H  
  
 **Libreria:** mscordbi_macx86.dll  
  
 **Versioni di .NET framework:** 3.5 SP1
