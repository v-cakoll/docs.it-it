---
title: Struttura ASSEMBLY_INFO
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b69aa42fc2ebb9f59cbf699d83b521704805ea5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519749"
---
# <a name="assemblyinfo-structure"></a>Struttura ASSEMBLY_INFO
Contiene informazioni relative a un assembly registrato nella global assembly cache.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`cbAssemblyInfo`|Le dimensioni, in byte, della struttura. Questo campo è riservato per un'estendibilità futura.|  
|`dwAssemblyFlags`|Flag che indicano i dettagli di installazione sull'assembly. Sono supportati i valori seguenti:<br /><br /> -Il valore ASSEMBLYINFO_FLAG_INSTALLED, che indica che l'assembly è installato. Imposta sempre la versione corrente di .NET Framework `dwAssemblyFlags` a questo valore.<br />-Il valore ASSEMBLYINFO_FLAG_INSTALLED, che indica che l'assembly è un payload residente. La versione corrente di .NET Framework non viene mai `dwAssemblyFlags` a questo valore.|  
|`uliAssemblySizeInKB`|Dimensione totale, espressa in kilobyte, dei file che contiene l'assembly.|  
|`pszCurrentAssemblyPathBuf`|Puntatore a un buffer di stringa che contiene il percorso corrente per il file manifesto. Il percorso deve terminare con un carattere null.|  
|`cchBuf`|Il numero di caratteri "wide", incluso il carattere di terminazione null, che `pszCurrentAssemblyPathBuf` contiene.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Strutture Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [Global Assembly Cache](../../../../docs/framework/app-domains/gac.md)
