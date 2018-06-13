---
title: AssemblyAttributesGoHere
ms.date: 03/30/2017
api_name:
- AssemblyAttributesGoHere
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyAttributesGoHere
helpviewer_keywords:
- AssemblyAttributesGoHere type
- Alink API, AssemblyAttributesGoHere type
ms.assetid: 7b26fcb6-94f4-4f09-933e-b33efe451f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c24ca43f35e237b6387e108563b1f9c9ed432242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402395"
---
# <a name="assemblyattributesgohere"></a><span data-ttu-id="74ba8-102">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="74ba8-102">AssemblyAttributesGoHere</span></span>
<span data-ttu-id="74ba8-103">Usato da ALink come segnaposto per archiviare le informazioni sugli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="74ba8-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74ba8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74ba8-104">Syntax</span></span>  
  
```  
AssemblyAttributesGoHere  
```  
  
## <a name="remarks"></a><span data-ttu-id="74ba8-105">Note</span><span class="sxs-lookup"><span data-stu-id="74ba8-105">Remarks</span></span>  
 <span data-ttu-id="74ba8-106">I riferimenti a questo tipo potrebbero essere incorporati in netmodule le cui origini contengono attributi personalizzati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="74ba8-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="74ba8-107">Quando compila un manifesto di assembly da uno o più netmodule contenenti riferimenti a questi tipi, ALink usa le informazioni associate a tali riferimenti per generare i veri attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="74ba8-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="74ba8-108">Per questo tipo non viene pertanto mai creata un'istanza e i riferimenti a esso relativi vengono usati solo come parte del processo di compilazione e non hanno alcun ruolo nell'assembly finale.</span><span class="sxs-lookup"><span data-stu-id="74ba8-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="74ba8-109">I riferimenti a questo tipo indicano gli attributi personalizzati che non sono correlati alla sicurezza e non sono multiuso.</span><span class="sxs-lookup"><span data-stu-id="74ba8-109">References to this type indicate custom attributes that are not security related and are not multiple-use.</span></span>  
  
 <span data-ttu-id="74ba8-110">Tali tipi sono contrassegnati come "interni" in .NET Framework e sono disponibili in <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="74ba8-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74ba8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74ba8-111">Requirements</span></span>  
 <span data-ttu-id="74ba8-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="74ba8-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ba8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74ba8-113">See Also</span></span>  
 [<span data-ttu-id="74ba8-114">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="74ba8-114">AssemblyAttributesGoHereM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)  
 [<span data-ttu-id="74ba8-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="74ba8-115">AssemblyAttributesGoHereS</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)  
 [<span data-ttu-id="74ba8-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="74ba8-116">AssemblyAttributesGoHereSM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
