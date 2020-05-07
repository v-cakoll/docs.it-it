---
title: Metodo ICorDebugClass2::GetParameterizedType
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
ms.openlocfilehash: 329bcee441b395982a8a8b539c0a938fa8170b14
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894050"
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="acad3-102">Metodo ICorDebugClass2::GetParameterizedType</span><span class="sxs-lookup"><span data-stu-id="acad3-102">ICorDebugClass2::GetParameterizedType Method</span></span>
<span data-ttu-id="acad3-103">Ottiene la dichiarazione del tipo per questa classe.</span><span class="sxs-lookup"><span data-stu-id="acad3-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acad3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="acad3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acad3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="acad3-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="acad3-106">in Valore dell'enumerazione CorElementType che specifica il tipo di elemento per questa classe: impostare questo valore su ELEMENT_TYPE_VALUETYPE se il ICorDebugClass2 rappresenta un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="acad3-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="acad3-107">Impostare questo valore su ELEMENT_TYPE_CLASS se l' `ICorDebugClass2` oggetto rappresenta un tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="acad3-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="acad3-108">in Il numero di parametri di tipo, se il tipo è generico.</span><span class="sxs-lookup"><span data-stu-id="acad3-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="acad3-109">Il numero di parametri di tipo (se presente) deve corrispondere al numero richiesto dalla classe.</span><span class="sxs-lookup"><span data-stu-id="acad3-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="acad3-110">in Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="acad3-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="acad3-111">Se la classe non è generica, questo valore è null.</span><span class="sxs-lookup"><span data-stu-id="acad3-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="acad3-112">out Puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta la dichiarazione del tipo.</span><span class="sxs-lookup"><span data-stu-id="acad3-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="acad3-113">Questo oggetto è equivalente a un <xref:System.Type> oggetto nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="acad3-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acad3-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="acad3-114">Remarks</span></span>  
 <span data-ttu-id="acad3-115">Se la classe non è generica, ovvero se non ha parametri di tipo, `GetParameterizedType` ottiene semplicemente l'oggetto di tipo runtime corrispondente alla classe.</span><span class="sxs-lookup"><span data-stu-id="acad3-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="acad3-116">Il `elementType` parametro deve essere impostato sul tipo di elemento corretto per la classe: ELEMENT_TYPE_VALUETYPE se la classe è un tipo di valore. in caso contrario, ELEMENT_TYPE_CLASS.</span><span class="sxs-lookup"><span data-stu-id="acad3-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="acad3-117">Se la classe accetta parametri di tipo (ad esempio `ArrayList<T>`,), è possibile `GetParameterizedType` usare per costruire un oggetto tipo per un tipo di cui è `ArrayList<int>`stata creata un'istanza, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="acad3-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="acad3-118">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="acad3-118">Background Information</span></span>  
 <span data-ttu-id="acad3-119">Nelle versioni .NET Framework 1,0 e 1,1, è possibile eseguire il mapping diretto di ogni tipo nei metadati a un tipo del processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="acad3-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="acad3-120">Pertanto, un tipo di metadati e un tipo di runtime hanno una sola rappresentazione nel processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="acad3-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="acad3-121">Tuttavia, è possibile eseguire il mapping di un tipo generico nei metadati a numerose creazioni di istanze diverse del tipo nel processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="acad3-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="acad3-122">Ad esempio, `SortedList<K,V>` il tipo di metadati può essere `SortedList<String, EmployeeRecord>`mappato a, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`e così via.</span><span class="sxs-lookup"><span data-stu-id="acad3-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="acad3-123">Pertanto, è necessario un modo per gestire la creazione dell'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="acad3-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="acad3-124">Il .NET Framework versione 2,0 introduce l' `ICorDebugType` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="acad3-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="acad3-125">Per un tipo generico, un `ICorDebugClass` oggetto `ICorDebugClass2` o rappresenta il tipo privo di istanze`SortedList<K,V>`() e un `ICorDebugType` oggetto rappresenta i vari tipi di cui è stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="acad3-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="acad3-126">Dato un `ICorDebugClass` oggetto `ICorDebugClass2` o, è possibile creare un `ICorDebugType` oggetto per qualsiasi creazione di istanza chiamando il `ICorDebugClass2::GetParameterizedType` metodo.</span><span class="sxs-lookup"><span data-stu-id="acad3-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="acad3-127">È anche possibile creare un `ICorDebugType` oggetto per un tipo semplice, ad esempio Int32, o per un tipo non generico.</span><span class="sxs-lookup"><span data-stu-id="acad3-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="acad3-128">L'introduzione dell' `ICorDebugType` oggetto per rappresentare la nozione di runtime di un tipo ha un effetto ripple nell'API.</span><span class="sxs-lookup"><span data-stu-id="acad3-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="acad3-129">Le funzioni che in precedenza `ICorDebugClass` accettano `ICorDebugClass2` un oggetto o o `CorElementType` addirittura un valore sono generalizzate per `ICorDebugType` l'esecuzione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="acad3-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acad3-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="acad3-130">Requirements</span></span>  
 <span data-ttu-id="acad3-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acad3-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acad3-132">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acad3-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acad3-133">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acad3-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acad3-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acad3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
