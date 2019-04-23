---
title: Enumerazione CorTypeAttr
ms.date: 03/30/2017
api_name:
- CorTypeAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTypeAttr
helpviewer_keywords:
- CorTypeAttr enumeration [.NET Framework metadata]
ms.assetid: 9bede0ec-5fdf-42a2-b5b7-bee64056acb6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 43e7c973ee22350f26b4f86bcc8b4c4c727291ef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087287"
---
# <a name="cortypeattr-enumeration"></a>Enumerazione CorTypeAttr
Contiene valori che indicano i metadati del tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorTypeAttr {  
  
    tdVisibilityMask        =   0x00000007,  
    tdNotPublic             =   0x00000000,  
    tdPublic                =   0x00000001,  
    tdNestedPublic          =   0x00000002,  
    tdNestedPrivate         =   0x00000003,  
    tdNestedFamily          =   0x00000004,  
    tdNestedAssembly        =   0x00000005,  
    tdNestedFamANDAssem     =   0x00000006,  
    tdNestedFamORAssem      =   0x00000007,  
  
    tdLayoutMask            =   0x00000018,  
    tdAutoLayout            =   0x00000000,  
    tdSequentialLayout      =   0x00000008,  
    tdExplicitLayout        =   0x00000010,  
  
    tdClassSemanticsMask    =   0x00000020,  
    tdClass                 =   0x00000000,  
    tdInterface             =   0x00000020,  
  
    tdAbstract              =   0x00000080,  
    tdSealed                =   0x00000100,  
    tdSpecialName           =   0x00000400,  
  
    tdImport                =   0x00001000,  
    tdSerializable          =   0x00002000,  
    tdWindowsRuntime        =   0x00004000,  
  
    tdStringFormatMask      =   0x00030000,  
    tdAnsiClass             =   0x00000000,  
    tdUnicodeClass          =   0x00010000,  
    tdAutoClass             =   0x00020000,  
    tdCustomFormatClass     =   0x00030000,  
    tdCustomFormatMask      =   0x00C00000,  
  
    tdBeforeFieldInit       =   0x00100000,  
    tdForwarder             =   0x00200000,  
  
    tdReservedMask          =   0x00040800,  
    tdRTSpecialName         =   0x00000800,  
    tdHasSecurity           =   0x00040000,  
  
} CorTypeAttr;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`tdVisibilityMask`|Utilizzato per informazioni sul tipo di visibilità.|  
|`tdNotPublic`|Specifica che il tipo non è in ambito pubblico.|  
|`tdPublic`|Specifica che il tipo sia in ambito pubblico.|  
|`tdNestedPublic`|Specifica che il tipo è annidato e con visibilità pubblica.|  
|`tdNestedPrivate`|Specifica che il tipo è annidato e con visibilità privata.|  
|`tdNestedFamily`|Specifica che il tipo è annidato e con visibilità della famiglia.|  
|`tdNestedAssembly`|Specifica che il tipo è annidato e con visibilità dell'assembly.|  
|`tdNestedFamANDAssem`|Specifica che il tipo è annidato e con visibilità dell'assembly e della famiglia.|  
|`tdNestedFamORAssem`|Specifica che il tipo è annidato e con visibilità dell'assembly o della famiglia.|  
|`tdLayoutMask`|Ottiene le informazioni sul layout per il tipo.|  
|`tdAutoLayout`|Specifica che i campi di questo tipo vengono disposti automaticamente.|  
|`tdSequentialLayout`|Specifica che i campi di questo tipo vengono disposti in ordine sequenziale.|  
|`tdExplicitLayout`|Specifica che il layout campo viene fornito in modo esplicito.|  
|`tdClassSemanticsMask`|Ottiene informazioni semantiche sul tipo.|  
|`tdClass`|Specifica che il tipo è una classe.|  
|`tdInterface`|Specifica che il tipo è un'interfaccia.|  
|`tdAbstract`|Specifica che il tipo è astratto.|  
|`tdSealed`|Specifica che il tipo non può essere estesa.|  
|`tdSpecialName`|Specifica che il nome della classe è speciale. Viene descritto il relativo nome come.|  
|`tdImport`|Specifica che il tipo viene importato.|  
|`tdSerializable`|Specifica che il tipo è serializzabile.|  
|`tdWindowsRuntime`|Specifica che questo tipo è un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo.|  
|`tdStringFormatMask`|Ottiene informazioni su come le stringhe vengono codificate e formattate.|  
|`tdAnsiClass`|Specifica che questo tipo interpreta LPTSTR come ANSI.|  
|`tdUnicodeClass`|Specifica che questo tipo interpreta LPTSTR come Unicode.|  
|`tdAutoClass`|Specifica che questo tipo interpreta LPTSTR automaticamente.|  
|`tdCustomFormatClass`|Specifica che il tipo ha una codifica non standard, come specificato da `CustomFormatMask`.|  
|`tdCustomFormatMask`|Usare questa maschera per ottenere informazioni di codifica non standard per l'interoperabilità nativa. Il significato dei valori di questi due bit non è specificato.|  
|`tdBeforeFieldInit`|Specifica che il tipo deve essere inizializzato prima del primo tentativo di accedere a un campo statico.|  
|`tdForwarder`|Specifica che il tipo viene esportato e un server d'inoltro.|  
|`tdReservedMask`|Questo flag e i flag seguenti vengono utilizzati internamente da common language runtime.|  
|`tdRTSpecialName`|Specifica che common language runtime deve verificare la codifica dei nomi.|  
|`tdHasSecurity`|Specifica che il tipo è associata una sicurezza.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
