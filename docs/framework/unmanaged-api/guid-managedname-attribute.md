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
# <a name="guidmanagedname-attribute"></a><span data-ttu-id="973fe-102">Attributo GUID_ManagedName</span><span class="sxs-lookup"><span data-stu-id="973fe-102">GUID_ManagedName Attribute</span></span>
<span data-ttu-id="973fe-103">Definisce un attributo personalizzato dell'interfaccia che specifica il nome dello spazio dei nomi gestito per una raccolta di componenti oggetto model (COM).</span><span class="sxs-lookup"><span data-stu-id="973fe-103">Defines a custom interface attribute that specifies the managed namespace name for a component object model (COM) library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="973fe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="973fe-104">Syntax</span></span>  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a><span data-ttu-id="973fe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="973fe-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="973fe-106">Il nome dello spazio dei nomi gestito per la libreria.</span><span class="sxs-lookup"><span data-stu-id="973fe-106">The managed namespace name for the library.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="973fe-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="973fe-107">Definition</span></span>  
 <span data-ttu-id="973fe-108">`GUID_ManagedName` viene definita nel Cor. h come segue:</span><span class="sxs-lookup"><span data-stu-id="973fe-108">`GUID_ManagedName` is defined in Cor.h as follows:</span></span>  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a><span data-ttu-id="973fe-109">Note</span><span class="sxs-lookup"><span data-stu-id="973fe-109">Remarks</span></span>  
 <span data-ttu-id="973fe-110">Un attributo personalizzato dell'interfaccia definisce i metadati per un oggetto nella libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="973fe-110">A custom interface attribute defines metadata for an object in the type library.</span></span>  
  
 <span data-ttu-id="973fe-111">Uso <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> per recuperare il nome gestito dall'attributo.</span><span class="sxs-lookup"><span data-stu-id="973fe-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> to retrieve the managed name from the attribute.</span></span>  
  
 <span data-ttu-id="973fe-112">Per altre informazioni, vedere [attributi di interfaccia](/cpp/windows/interface-attributes) in Visual C++ della documentazione di riferimento.</span><span class="sxs-lookup"><span data-stu-id="973fe-112">For more information, see [Interface Attributes](/cpp/windows/interface-attributes) in the Visual C++ reference documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="973fe-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="973fe-113">Example</span></span>  
 <span data-ttu-id="973fe-114">L'esempio seguente illustra una definizione di libreria usando la `GUID_ManagedName` attributo.</span><span class="sxs-lookup"><span data-stu-id="973fe-114">The following example shows a library definition using the `GUID_ManagedName` attribute.</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="973fe-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="973fe-115">Requirements</span></span>  
 <span data-ttu-id="973fe-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="973fe-116">**Header:** Cor.h</span></span>
