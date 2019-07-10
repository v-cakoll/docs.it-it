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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1bfc503bfc2b278d7a7344b94cb089cd8e019890
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747761"
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="4762d-102">Metodo ICorDebugClass2::GetParameterizedType</span><span class="sxs-lookup"><span data-stu-id="4762d-102">ICorDebugClass2::GetParameterizedType Method</span></span>
<span data-ttu-id="4762d-103">Ottiene la dichiarazione del tipo per questa classe.</span><span class="sxs-lookup"><span data-stu-id="4762d-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4762d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4762d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4762d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4762d-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="4762d-106">[in] Valore dell'enumerazione CorElementType che specifica il tipo di elemento per questa classe: Impostare questo valore su ELEMENT_TYPE_VALUETYPE se questo ICorDebugClass2 rappresenta un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="4762d-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="4762d-107">Impostare questo valore su ELEMENT_TYPE_CLASS se questa `ICorDebugClass2` rappresenta un tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="4762d-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="4762d-108">[in] Il numero di parametri di tipo, se il tipo è generico.</span><span class="sxs-lookup"><span data-stu-id="4762d-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="4762d-109">Il numero di parametri di tipo (se presente) deve corrispondere al numero richiesto dalla classe.</span><span class="sxs-lookup"><span data-stu-id="4762d-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="4762d-110">[in] Una matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="4762d-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="4762d-111">Se la classe non generica, questo valore è null.</span><span class="sxs-lookup"><span data-stu-id="4762d-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="4762d-112">[out] Un puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta la dichiarazione del tipo.</span><span class="sxs-lookup"><span data-stu-id="4762d-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="4762d-113">Questo oggetto è equivalente a un <xref:System.Type> oggetto nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="4762d-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4762d-114">Note</span><span class="sxs-lookup"><span data-stu-id="4762d-114">Remarks</span></span>  
 <span data-ttu-id="4762d-115">Se la classe non generica, vale a dire, se non ha parametri di tipo, `GetParameterizedType` semplicemente Ottiene l'oggetto di tipo runtime corrispondente alla classe.</span><span class="sxs-lookup"><span data-stu-id="4762d-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="4762d-116">Il `elementType` parametro deve essere impostato per il tipo di elemento corretto per la classe: ELEMENT_TYPE_VALUETYPE se la classe è un tipo di valore. in caso contrario, ELEMENT_TYPE_CLASS.</span><span class="sxs-lookup"><span data-stu-id="4762d-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="4762d-117">Se la classe accetta i parametri di tipo (ad esempio, `ArrayList<T>`), è possibile usare `GetParameterizedType` per costruire un oggetto di tipo per un tipo con istanze, ad esempio `ArrayList<int>`.</span><span class="sxs-lookup"><span data-stu-id="4762d-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="4762d-118">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="4762d-118">Background Information</span></span>  
 <span data-ttu-id="4762d-119">Nelle versioni 1.0 e 1.1 di .NET Framework, ogni tipo nei metadati è stato possibile eseguire direttamente il mapping a un tipo di processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4762d-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="4762d-120">Di conseguenza, un tipo di metadati e un tipo di runtime aveva una sola rappresentazione nel processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4762d-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="4762d-121">Tuttavia, un tipo generico nei metadati può essere mappato a molte istanze diverse del tipo nel processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4762d-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="4762d-122">Ad esempio, il tipo di metadati `SortedList<K,V>` può eseguire il mapping a `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`e così via.</span><span class="sxs-lookup"><span data-stu-id="4762d-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="4762d-123">Di conseguenza, è necessario un modo per gestire l'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="4762d-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="4762d-124">.NET Framework versione 2.0 introduce il `ICorDebugType` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4762d-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="4762d-125">Per un tipo generico, un `ICorDebugClass` oppure `ICorDebugClass2` rappresenta il tipo privo di istanze (`SortedList<K,V>`) e un `ICorDebugType` oggetto rappresenta i vari tipi di istanziati.</span><span class="sxs-lookup"><span data-stu-id="4762d-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="4762d-126">Dato un `ICorDebugClass` oppure `ICorDebugClass2` dell'oggetto, è possibile creare un `ICorDebugType` oggetto per ogni istanza creata chiamando il `ICorDebugClass2::GetParameterizedType` (metodo).</span><span class="sxs-lookup"><span data-stu-id="4762d-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="4762d-127">È anche possibile creare un `ICorDebugType` oggetto per un tipo semplice, ad esempio Int32, o per un tipo non generico.</span><span class="sxs-lookup"><span data-stu-id="4762d-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="4762d-128">L'introduzione del `ICorDebugType` oggetto per rappresentare la nozione di fase di esecuzione di un tipo ha un effetto domino in tutta l'API.</span><span class="sxs-lookup"><span data-stu-id="4762d-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="4762d-129">Funzioni che in passato richiedeva un `ICorDebugClass` oppure `ICorDebugClass2` dell'oggetto o persino una `CorElementType` valore sono generalizzati per sfruttare un `ICorDebugType` oggetto.</span><span class="sxs-lookup"><span data-stu-id="4762d-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4762d-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4762d-130">Requirements</span></span>  
 <span data-ttu-id="4762d-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4762d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4762d-132">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4762d-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4762d-133">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4762d-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4762d-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4762d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
