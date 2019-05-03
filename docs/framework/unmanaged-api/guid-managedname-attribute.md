---
title: Attributo GUID_ManagedName
ms.date: 03/30/2017
api_name:
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48ad6e4d1d03d8362123e65f16907880b18893f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777910"
---
# <a name="guidmanagedname-attribute"></a>Attributo GUID_ManagedName
Definisce un attributo personalizzato dell'interfaccia che specifica il nome dello spazio dei nomi gestito per una raccolta di componenti oggetto model (COM).  
  
## <a name="syntax"></a>Sintassi  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a>Parametri  
 `value`  
 Il nome dello spazio dei nomi gestito per la libreria.  
  
## <a name="definition"></a>Definizione  
 `GUID_ManagedName` viene definita nel Cor. h come segue:  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>Note  
 Un attributo personalizzato dell'interfaccia definisce i metadati per un oggetto nella libreria dei tipi.  
  
 Uso <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> per recuperare il nome gestito dall'attributo.  
  
 Per altre informazioni, vedere [attributi di interfaccia](/cpp/windows/interface-attributes) in Visual C++ della documentazione di riferimento.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra una definizione di libreria usando la `GUID_ManagedName` attributo.  
  
```  
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** Cor. h
