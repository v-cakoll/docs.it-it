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
ms.openlocfilehash: f14d00f17a61576a50e26d3cbcf734a10ed3c03a
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895011"
---
# <a name="guid_managedname-attribute"></a>Attributo GUID_ManagedName
Definisce un attributo di interfaccia personalizzato che specifica il nome dello spazio dei nomi gestito per una libreria COM (Component Object Model).  
  
## <a name="syntax"></a>Sintassi  
  
```idl
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a>Parametri  
 `value`  
 Nome dello spazio dei nomi gestito per la libreria.  
  
## <a name="definition"></a>Definizione  
 `GUID_ManagedName`è definito in cor. h come segue:  
  
```cpp
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>Note  
 Un attributo di interfaccia personalizzato definisce i metadati per un oggetto nella libreria dei tipi.  
  
 Utilizzare <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> o<xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> per recuperare il nome gestito dall'attributo.  
  
 Per ulteriori informazioni, vedere [attributi di interfaccia](/cpp/windows/attributes/interface-attributes) nella documentazione C++ di riferimento Visual.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una definizione di `GUID_ManagedName` libreria utilizzando l'attributo.  
  
```idl
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
