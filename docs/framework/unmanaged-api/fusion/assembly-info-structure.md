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
ms.openlocfilehash: a43d5e15c02a97ff10a6a5afd439cadebb6b33d2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109222"
---
# <a name="assembly_info-structure"></a>Struttura ASSEMBLY_INFO
Contiene informazioni su un assembly registrato nel Global Assembly Cache.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`cbAssemblyInfo`|Dimensione, in byte, della struttura. Questo campo è riservato per l'estendibilità futura.|  
|`dwAssemblyFlags`|Flag che indicano i dettagli di installazione dell'assembly. Sono supportati i valori seguenti:<br /><br /> : Valore ASSEMBLYINFO_FLAG_INSTALLED, che indica che l'assembly è installato. La versione corrente del .NET Framework imposta sempre `dwAssemblyFlags` su questo valore.<br />: Valore ASSEMBLYINFO_FLAG_PAYLOADRESIDENT, che indica che l'assembly è un payload residente. La versione corrente del .NET Framework non imposta mai `dwAssemblyFlags` su questo valore.|  
|`uliAssemblySizeInKB`|Dimensioni totali, in kilobyte, dei file contenuti nell'assembly.|  
|`pszCurrentAssemblyPathBuf`|Puntatore a un buffer di stringa che include il percorso corrente del file manifesto. Il percorso deve terminare con un carattere null.|  
|`cchBuf`|Numero di caratteri wide, incluso il terminatore null, che `pszCurrentAssemblyPathBuf` contiene.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture Fusion](fusion-structures.md)
- [Global Assembly Cache](../../app-domains/gac.md)
