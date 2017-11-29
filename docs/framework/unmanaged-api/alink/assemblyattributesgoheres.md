---
title: AssemblyAttributesGoHereS
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyAttributesGoHereS
api_location: alink.dll
api_type: COM
f1_keywords: AssemblyAttributesGoHereS
helpviewer_keywords:
- AssemblyAttributesGoHereS type
- Alink API, AssemblyAttributesGoHereS type
ms.assetid: 4e817f35-a2bc-4403-9e6f-f731e6b9fe23
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8ed5e0ee6559747604a3bd060386c65548460b37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyattributesgoheres"></a><span data-ttu-id="cfd77-102">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="cfd77-102">AssemblyAttributesGoHereS</span></span>
<span data-ttu-id="cfd77-103">Usato da ALink come segnaposto per archiviare le informazioni sugli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="cfd77-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfd77-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfd77-104">Syntax</span></span>  
  
```  
AssemblyAttributesGoHereS  
```  
  
## <a name="remarks"></a><span data-ttu-id="cfd77-105">Note</span><span class="sxs-lookup"><span data-stu-id="cfd77-105">Remarks</span></span>  
 <span data-ttu-id="cfd77-106">I riferimenti a questo tipo potrebbero essere incorporati in netmodule le cui origini contengono attributi personalizzati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="cfd77-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="cfd77-107">Quando compila un manifesto di assembly da uno o più netmodule contenenti riferimenti a questi tipi, ALink usa le informazioni associate a tali riferimenti per generare i veri attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="cfd77-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="cfd77-108">Per questo tipo non viene pertanto mai creata un'istanza e i riferimenti a esso relativi vengono usati solo come parte del processo di compilazione e non hanno alcun ruolo nell'assembly finale.</span><span class="sxs-lookup"><span data-stu-id="cfd77-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="cfd77-109">I riferimenti a questo tipo indicano gli attributi personalizzati che sono correlati alla sicurezza e non sono multiuso.</span><span class="sxs-lookup"><span data-stu-id="cfd77-109">References to this type indicate custom attributes that are security related and are not multiple-use.</span></span>  
  
 <span data-ttu-id="cfd77-110">Tali tipi sono contrassegnati come "interni" in .NET Framework e sono disponibili in <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="cfd77-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfd77-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cfd77-111">Requirements</span></span>  
 <span data-ttu-id="cfd77-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="cfd77-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfd77-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfd77-113">See Also</span></span>  
 [<span data-ttu-id="cfd77-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="cfd77-114">AssemblyAttributesGoHere</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgohere.md)  
 [<span data-ttu-id="cfd77-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="cfd77-115">AssemblyAttributesGoHereM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)  
 [<span data-ttu-id="cfd77-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="cfd77-116">AssemblyAttributesGoHereSM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
