---
title: Enumerazione CorMethodAttr
ms.date: 03/30/2017
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 249de91483117db6b497fa8eae6f97c3eb0a0587
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176995"
---
# <a name="cormethodattr-enumeration"></a>Enumerazione CorMethodAttr
Contiene valori che descrivono le funzionalità di un metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`mdMemberAccessMask`|Specifica l'accesso al membro.|  
|`mdPrivateScope`|Specifica che il membro non è possibile fare riferimento.|  
|`mdPrivate`|Specifica che il membro è accessibile solo dal tipo padre.|  
|`mdFamANDAssem`|Specifica che il membro è accessibile dai sottotipi solo in questo assembly.|  
|`mdAssem`|Specifica che il membro è accessibile da tutti gli utenti nell'assembly.|  
|`mdFamily`|Specifica che il membro è accessibile solo dal tipo e sottotipi.|  
|`mdFamORAssem`|Specifica che il membro è accessibile dalle classi derivate e da altri tipi nell'assembly.|  
|`mdPublic`|Specifica che il membro è accessibile da tutti i tipi con accesso all'ambito.|  
|`mdStatic`|Specifica che il membro è definito come parte del tipo anziché come un membro di un'istanza.|  
|`mdFinal`|Specifica che il metodo non può essere sottoposto a override.|  
|`mdVirtual`|Specifica che il metodo può essere sottoposto a override.|  
|`mdHideBySig`|Specifica che il metodo è nascosto per nome e firma, anziché semplicemente dal nome.|  
|`mdVtableLayoutMask`|Specifica il layout di tabella virtuale.|  
|`mdReuseSlot`|Specifica che lo slot usato per questo metodo nella tabella virtuale è possibile riutilizzare. Questa è l'impostazione predefinita.|  
|`mdNewSlot`|Specifica che il metodo ottiene sempre un nuovo slot nella tabella virtuale.|  
|`mdCheckAccessOnOverride`|Specifica che il metodo può essere sostituito dagli stessi tipi a cui è visibile.|  
|`mdAbstract`|Specifica che il metodo non è implementato.|  
|`mdSpecialName`|Specifica che il metodo è speciale e che il relativo nome viene descritto come.|  
|`mdPinvokeImpl`|Specifica che l'implementazione del metodo è inoltrata tramite PInvoke.|  
|`mdUnmanagedExport`|Specifica che il metodo è un metodo gestito esportato in codice non gestito.|  
|`mdReservedMask`|Riservato per uso interno da common language runtime.|  
|`mdRTSpecialName`|Specifica che common language runtime deve verificare la codifica del nome del metodo.|  
|`mdHasSecurity`|Specifica che il metodo è associata una sicurezza.|  
|`mdRequireSecObject`|Specifica che il metodo chiama un altro metodo contenente codice di sicurezza.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
