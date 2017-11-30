---
title: Attributo GUID_ManagedName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GUID_ManagedName
api_location: alink.dll
api_type: COM
f1_keywords: GUID_ManagedName
helpviewer_keywords: GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cf0facaa1107fcc6dcd93cbf0252024dc6f73b0a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="guidmanagedname-attribute"></a>Attributo GUID_ManagedName
Definisce un attributo di interfaccia personalizzata che specifica il nome di spazio dei nomi gestito per una libreria di componente oggetti modello (COM).  
  
## <a name="syntax"></a>Sintassi  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
#### <a name="parameters"></a>Parametri  
 `value`  
 Nome spazio dei nomi gestito per la raccolta.  
  
## <a name="definition"></a>Definizione  
 `GUID_ManagedName`viene definito come segue in Cor. h:  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>Note  
 Un attributo personalizzato dell'interfaccia definisce i metadati per un oggetto della libreria dei tipi.  
  
 Utilizzare <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> per recuperare il nome gestito dall'attributo.  
  
 Per ulteriori informazioni, vedere [gli attributi di interfaccia](/cpp/windows/interface-attributes) documentazione di riferimento in Visual C++.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una definizione di raccolta utilizzando la `GUID_ManagedName` attributo.  
  
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
