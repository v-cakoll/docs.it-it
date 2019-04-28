---
title: Classe AssemblyAttributesGoHere (CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHere
api_location:
- mscorlib.dll
api_type:
- Assembly
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
ms.openlocfilehash: 571c2f6723e827a1b385f77724c33703ae970ae3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775622"
---
# <a name="assemblyattributesgohere-class"></a><span data-ttu-id="dba9e-102">Classe AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="dba9e-102">AssemblyAttributesGoHere Class</span></span>

<span data-ttu-id="dba9e-103">Usato da ALink come segnaposto per archiviare le informazioni sugli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="dba9e-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="dba9e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dba9e-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHere
```

## <a name="remarks"></a><span data-ttu-id="dba9e-105">Note</span><span class="sxs-lookup"><span data-stu-id="dba9e-105">Remarks</span></span>

<span data-ttu-id="dba9e-106">I riferimenti a questo tipo potrebbero essere incorporati in netmodule le cui origini contengono attributi personalizzati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="dba9e-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="dba9e-107">Quando compila un manifesto di assembly da uno o più netmodule contenenti riferimenti a questi tipi, ALink usa le informazioni associate a tali riferimenti per generare i veri attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="dba9e-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="dba9e-108">Per questo tipo non viene pertanto mai creata un'istanza e i riferimenti a esso relativi vengono usati solo come parte del processo di compilazione e non hanno alcun ruolo nell'assembly finale.</span><span class="sxs-lookup"><span data-stu-id="dba9e-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="dba9e-109">I riferimenti a questo tipo indicano gli attributi personalizzati che non sono correlati alla sicurezza e non sono multiuso.</span><span class="sxs-lookup"><span data-stu-id="dba9e-109">References to this type indicate custom attributes that are not security related and are not multiple-use.</span></span>

<span data-ttu-id="dba9e-110">Questi tipi sono contrassegnati come "interni" all'interno di .NET Framework e si trovano nel <xref:System.Runtime.CompilerServices> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dba9e-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="dba9e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dba9e-111">Requirements</span></span>

<span data-ttu-id="dba9e-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="dba9e-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="dba9e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dba9e-113">See also</span></span>

- [<span data-ttu-id="dba9e-114">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="dba9e-114">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="dba9e-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="dba9e-115">AssemblyAttributesGoHereS</span></span>](assemblyattributesgoheres.md)
- [<span data-ttu-id="dba9e-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="dba9e-116">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)
