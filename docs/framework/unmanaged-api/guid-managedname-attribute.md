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
ms.openlocfilehash: 110d6eb0abcf4b4ce73f1ee9d27e27122f360270
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374434"
---
# <a name="guid_managedname-attribute"></a><span data-ttu-id="78d8f-102">Attributo GUID_ManagedName</span><span class="sxs-lookup"><span data-stu-id="78d8f-102">GUID_ManagedName Attribute</span></span>
<span data-ttu-id="78d8f-103">Definisce un attributo di interfaccia personalizzato che specifica il nome dello spazio dei nomi gestito per una libreria COM (Component Object Model).</span><span class="sxs-lookup"><span data-stu-id="78d8f-103">Defines a custom interface attribute that specifies the managed namespace name for a component object model (COM) library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78d8f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78d8f-104">Syntax</span></span>  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a><span data-ttu-id="78d8f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="78d8f-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="78d8f-106">Nome dello spazio dei nomi gestito per la libreria.</span><span class="sxs-lookup"><span data-stu-id="78d8f-106">The managed namespace name for the library.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="78d8f-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="78d8f-107">Definition</span></span>  
 <span data-ttu-id="78d8f-108">`GUID_ManagedName`è definito in cor. h come segue:</span><span class="sxs-lookup"><span data-stu-id="78d8f-108">`GUID_ManagedName` is defined in Cor.h as follows:</span></span>  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a><span data-ttu-id="78d8f-109">Note</span><span class="sxs-lookup"><span data-stu-id="78d8f-109">Remarks</span></span>  
 <span data-ttu-id="78d8f-110">Un attributo di interfaccia personalizzato definisce i metadati per un oggetto nella libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="78d8f-110">A custom interface attribute defines metadata for an object in the type library.</span></span>  
  
 <span data-ttu-id="78d8f-111">Utilizzare <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> o<xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> per recuperare il nome gestito dall'attributo.</span><span class="sxs-lookup"><span data-stu-id="78d8f-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> to retrieve the managed name from the attribute.</span></span>  
  
 <span data-ttu-id="78d8f-112">Per ulteriori informazioni, vedere [attributi di interfaccia](/cpp/windows/attributes/interface-attributes) nella documentazione C++ di riferimento Visual.</span><span class="sxs-lookup"><span data-stu-id="78d8f-112">For more information, see [Interface Attributes](/cpp/windows/attributes/interface-attributes) in the Visual C++ reference documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78d8f-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="78d8f-113">Example</span></span>  
 <span data-ttu-id="78d8f-114">Nell'esempio seguente viene illustrata una definizione di `GUID_ManagedName` libreria utilizzando l'attributo.</span><span class="sxs-lookup"><span data-stu-id="78d8f-114">The following example shows a library definition using the `GUID_ManagedName` attribute.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="78d8f-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="78d8f-115">Requirements</span></span>  
 <span data-ttu-id="78d8f-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="78d8f-116">**Header:** Cor.h</span></span>
