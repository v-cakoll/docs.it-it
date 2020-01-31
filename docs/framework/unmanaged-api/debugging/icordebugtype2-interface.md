---
title: Interfaccia ICorDebugType2
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
ms.openlocfilehash: e90952a92c408762a98a2bfcb91b6aeb72052df1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791215"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="67612-102">Interfaccia ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="67612-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="67612-103">Estende l'interfaccia ICorDebugType per recuperare l'identificatore di tipo di un tipo di base o di un tipo complesso (definito dall'utente).</span><span class="sxs-lookup"><span data-stu-id="67612-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67612-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="67612-104">Methods</span></span>  
  
|<span data-ttu-id="67612-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="67612-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="67612-106">Metodo GetTypeID</span><span class="sxs-lookup"><span data-stu-id="67612-106">GetTypeID Method</span></span>](icordebugtype2-gettypeid-method.md)|<span data-ttu-id="67612-107">Ottiene un [COR_TYPEID](cor-typeid-structure.md) per questo tipo.</span><span class="sxs-lookup"><span data-stu-id="67612-107">Gets a [COR_TYPEID](cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67612-108">Note</span><span class="sxs-lookup"><span data-stu-id="67612-108">Remarks</span></span>  
 <span data-ttu-id="67612-109">Questa interfaccia è un'estensione logica dell'interfaccia ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="67612-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67612-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="67612-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67612-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="67612-111">Example</span></span>  
 <span data-ttu-id="67612-112">Il frammento di codice seguente illustra l'uso del metodo [Metodo icordebugtype2:: GetTypeID](icordebugtype2-gettypeid-method.md) .</span><span class="sxs-lookup"><span data-stu-id="67612-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```cpp  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="67612-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="67612-113">Requirements</span></span>  
 <span data-ttu-id="67612-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67612-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67612-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67612-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67612-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67612-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67612-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67612-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67612-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67612-118">See also</span></span>

- [<span data-ttu-id="67612-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="67612-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
