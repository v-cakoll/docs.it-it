---
title: Funzioni statiche globali di debug
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2403d736d031aab52525fc12b5071e764a8bde1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698525"
---
# <a name="debugging-global-static-functions"></a><span data-ttu-id="4884d-102">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="4884d-102">Debugging Global Static Functions</span></span>
<span data-ttu-id="4884d-103">Questa sezione descrive le funzioni statiche globali non gestite usate dall'API di debug.</span><span class="sxs-lookup"><span data-stu-id="4884d-103">This section describes the unmanaged global static functions that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4884d-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="4884d-104">In This Section</span></span>  
 [<span data-ttu-id="4884d-105">Funzione _EFN_GetManagedExcepStack</span><span class="sxs-lookup"><span data-stu-id="4884d-105">_EFN_GetManagedExcepStack Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedexcepstack-function.md)  
 <span data-ttu-id="4884d-106">Restituisce una versione stringa della traccia dello stack contenuta internamente, dato l'indirizzo di un oggetto eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="4884d-106">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
 [<span data-ttu-id="4884d-107">Funzione _EFN_GetManagedObjectFieldInfo</span><span class="sxs-lookup"><span data-stu-id="4884d-107">_EFN_GetManagedObjectFieldInfo Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectfieldinfo-function.md)  
 <span data-ttu-id="4884d-108">Ottiene l'offset per un campo dall'inizio di un oggetto e il valore del campo, usando il puntatore all'oggetto e il nome di campo forniti.</span><span class="sxs-lookup"><span data-stu-id="4884d-108">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
 [<span data-ttu-id="4884d-109">Funzione _EFN_GetManagedObjectName</span><span class="sxs-lookup"><span data-stu-id="4884d-109">_EFN_GetManagedObjectName Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectname-function.md)  
 <span data-ttu-id="4884d-110">Ottiene il nome di un tipo usando il puntatore all'oggetto gestito fornito.</span><span class="sxs-lookup"><span data-stu-id="4884d-110">Gets the name of a type by using the provided managed object pointer.</span></span>  
  
 [<span data-ttu-id="4884d-111">Funzione _EFN_StackTrace</span><span class="sxs-lookup"><span data-stu-id="4884d-111">_EFN_StackTrace Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/efn-stacktrace-function.md)  
 <span data-ttu-id="4884d-112">Fornisce una rappresentazione testuale di una traccia dello stack gestito e una matrice di record `CONTEXT`, uno per ogni transizione tra codice non gestito e gestito.</span><span class="sxs-lookup"><span data-stu-id="4884d-112">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
 [<span data-ttu-id="4884d-113">Funzione CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="4884d-113">CLRDataCreateInstance Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatacreateinstance-function.md)  
 <span data-ttu-id="4884d-114">Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per creare l'oggetto all'interfaccia specificata per il processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="4884d-114">Called by the common language runtime (CLR) data access services to create the specified interface object for the specified target process.</span></span>  
  
 [<span data-ttu-id="4884d-115">Puntatore alla funzione PFN_CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="4884d-115">PFN_CLRDataCreateInstance Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/debugging/pfn-clrdatacreateinstance-function-pointer.md)  
 <span data-ttu-id="4884d-116">Punta a una funzione chiamata dai servizi di accesso ai dati di CLR per creare l'oggetto all'interfaccia specificata per il processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="4884d-116">Points to a function that is called by the CLR data access services to create the specified interface object for the specified target process.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4884d-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="4884d-117">Related Sections</span></span>  
 [<span data-ttu-id="4884d-118">Coclassi di debug</span><span class="sxs-lookup"><span data-stu-id="4884d-118">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="4884d-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4884d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="4884d-120">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="4884d-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="4884d-121">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="4884d-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
