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
ms.openlocfilehash: b6936081ca3dbadb4f802a6856fafb53f6cef3fa
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008963"
---
# <a name="cortypeattr-enumeration"></a>Enumerazione CorTypeAttr
Contiene valori che indicano i metadati del tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`tdVisibilityMask`|Utilizzato per informazioni sulla visibilità del tipo.|  
|`tdNotPublic`|Specifica che il tipo non è nell'ambito pubblico.|  
|`tdPublic`|Specifica che il tipo è nell'ambito pubblico.|  
|`tdNestedPublic`|Specifica che il tipo è annidato con visibilità pubblica.|  
|`tdNestedPrivate`|Specifica che il tipo è annidato con visibilità privata.|  
|`tdNestedFamily`|Specifica che il tipo è annidato con visibilità della famiglia.|  
|`tdNestedAssembly`|Specifica che il tipo è annidato con visibilità dell'assembly.|  
|`tdNestedFamANDAssem`|Specifica che il tipo è annidato con visibilità della famiglia e dell'assembly.|  
|`tdNestedFamORAssem`|Specifica che il tipo è annidato con visibilità della famiglia o dell'assembly.|  
|`tdLayoutMask`|Ottiene le informazioni sul layout per il tipo.|  
|`tdAutoLayout`|Specifica che i campi di questo tipo vengono disposti automaticamente.|  
|`tdSequentialLayout`|Specifica che i campi di questo tipo sono disposti in sequenza.|  
|`tdExplicitLayout`|Specifica che il layout del campo viene fornito in modo esplicito.|  
|`tdClassSemanticsMask`|Ottiene le informazioni semantiche sul tipo.|  
|`tdClass`|Specifica che il tipo è una classe.|  
|`tdInterface`|Specifica che il tipo è un'interfaccia.|  
|`tdAbstract`|Specifica che il tipo è astratto.|  
|`tdSealed`|Specifica che il tipo non può essere esteso.|  
|`tdSpecialName`|Specifica che il nome della classe è speciale. Il nome descrive come.|  
|`tdImport`|Specifica che il tipo viene importato.|  
|`tdSerializable`|Specifica che il tipo è serializzabile.|  
|`tdWindowsRuntime`|Specifica che questo tipo è un tipo di Windows Runtime.|  
|`tdStringFormatMask`|Ottiene informazioni sul modo in cui le stringhe vengono codificate e formattate.|  
|`tdAnsiClass`|Specifica che questo tipo interpreta un LPTSTR come ANSI.|  
|`tdUnicodeClass`|Specifica che questo tipo interpreta un LPTSTR come Unicode.|  
|`tdAutoClass`|Specifica che questo tipo interpreta automaticamente un LPTSTR.|  
|`tdCustomFormatClass`|Specifica che il tipo ha una codifica non standard, come specificato da `CustomFormatMask` .|  
|`tdCustomFormatMask`|Usare questa maschera per ottenere informazioni di codifica non standard per l'interoperabilità nativa. Il significato dei valori di questi due bit non è specificato.|  
|`tdBeforeFieldInit`|Specifica che il tipo deve essere inizializzato prima del primo tentativo di accesso a un campo statico.|  
|`tdForwarder`|Specifica che il tipo viene esportato e un server d'avanzamento del tipo.|  
|`tdReservedMask`|Questo flag e i flag seguenti vengono usati internamente dal Common Language Runtime.|  
|`tdRTSpecialName`|Specifica che il Common Language Runtime deve controllare la codifica dei nomi.|  
|`tdHasSecurity`|Specifica che il tipo è associato alla sicurezza.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
