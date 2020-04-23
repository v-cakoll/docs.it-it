---
title: Creazione di una classe che contenga le funzioni di DLL
ms.date: 03/30/2017
helpviewer_keywords:
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, creating class for functions
- DLL functions
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
ms.openlocfilehash: 765d4344553a6e65b930a7bf586a41144d220fc6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123632"
---
# <a name="creating-a-class-to-hold-dll-functions"></a><span data-ttu-id="0be4d-102">Creazione di una classe che contenga le funzioni di DLL</span><span class="sxs-lookup"><span data-stu-id="0be4d-102">Creating a Class to Hold DLL Functions</span></span>
<span data-ttu-id="0be4d-103">Il wrapping di una funzione di DLL frequentemente usata in una classe gestita è un modo efficace per incapsulare la funzionalità della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="0be4d-103">Wrapping a frequently used DLL function in a managed class is an effective approach to encapsulate platform functionality.</span></span> <span data-ttu-id="0be4d-104">Anche se non è obbligatorio in tutti i casi, è preferibile fornire un wrapper di classe, perché la definizione delle funzioni di DLL è un'attività complessa e soggetta a errori.</span><span class="sxs-lookup"><span data-stu-id="0be4d-104">Although it is not mandatory to do so in every case, providing a class wrapper is convenient because defining DLL functions can be cumbersome and error-prone.</span></span> <span data-ttu-id="0be4d-105">In caso di programmazione in C# o in Visual Basic, è necessario dichiarare le funzioni di DLL in una classe o in un modulo Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0be4d-105">If you are programming in Visual Basic or C#, you must declare DLL functions within a class or Visual Basic module.</span></span>  
  
 <span data-ttu-id="0be4d-106">All'interno di una classe si definisce un metodo statico per ogni funzione di DLL che si vuole chiamare.</span><span class="sxs-lookup"><span data-stu-id="0be4d-106">Within a class, you define a static method for each DLL function you want to call.</span></span> <span data-ttu-id="0be4d-107">La definizione può includere informazioni aggiuntive, come il set di caratteri o la convenzione di chiamata usata per passare gli argomenti del metodo. Se si omettono queste informazioni, verranno usate le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="0be4d-107">The definition can include additional information, such as the character set or the calling convention used in passing method arguments; by omitting this information, you select the default settings.</span></span> <span data-ttu-id="0be4d-108">Per un elenco completo delle opzioni di dichiarazione e delle relative impostazioni predefinite, vedere [Creazione di prototipi nel codice gestito](creating-prototypes-in-managed-code.md).</span><span class="sxs-lookup"><span data-stu-id="0be4d-108">For a complete list of declaration options and their default settings, see [Creating Prototypes in Managed Code](creating-prototypes-in-managed-code.md).</span></span>  
  
 <span data-ttu-id="0be4d-109">Una volta effettuato il wrapping è possibile chiamare i metodi della classe, così come si chiamano i metodi statici di qualsiasi altra classe.</span><span class="sxs-lookup"><span data-stu-id="0be4d-109">Once wrapped, you can call the methods on the class as you call static methods on any other class.</span></span> <span data-ttu-id="0be4d-110">Con platform invoke, la funzione esportata sottostante viene gestita automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0be4d-110">Platform invoke handles the underlying exported function automatically.</span></span>  
  
 <span data-ttu-id="0be4d-111">Quando si progetta una classe gestita che supporti platform invoke, è necessario tenere in considerazione le relazioni tra le classi e le funzioni di DLL.</span><span class="sxs-lookup"><span data-stu-id="0be4d-111">When designing a managed class for platform invoke, consider the relationships between classes and DLL functions.</span></span> <span data-ttu-id="0be4d-112">Ad esempio, è possibile:</span><span class="sxs-lookup"><span data-stu-id="0be4d-112">For example, you can:</span></span>  
  
- <span data-ttu-id="0be4d-113">Dichiarare funzioni di DLL in una classe esistente.</span><span class="sxs-lookup"><span data-stu-id="0be4d-113">Declare DLL functions within an existing class.</span></span>  
  
- <span data-ttu-id="0be4d-114">Creare una classe distinta per ciascuna funzione di DLL, mantenendo le funzioni isolate e facilmente rintracciabili.</span><span class="sxs-lookup"><span data-stu-id="0be4d-114">Create an individual class for each DLL function, keeping functions isolated and easy to find.</span></span>  
  
- <span data-ttu-id="0be4d-115">Creare una sola classe per un insieme di funzioni di DLL correlate, al fine di formare raggruppamenti logici e ridurre l'overhead.</span><span class="sxs-lookup"><span data-stu-id="0be4d-115">Create one class for a set of related DLL functions to form logical groupings and reduce overhead.</span></span>  
  
 <span data-ttu-id="0be4d-116">È possibile assegnare alla classe e ai relativi metodi i nomi che si preferiscono.</span><span class="sxs-lookup"><span data-stu-id="0be4d-116">You can name the class and its methods as you please.</span></span> <span data-ttu-id="0be4d-117">Per alcuni esempi che mostrano come costruire dichiarazioni basate su .NET da usare con platform invoke, vedere , vedere [Marshalling dei dati con platform invoke](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="0be4d-117">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be4d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0be4d-118">See also</span></span>

- [<span data-ttu-id="0be4d-119">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="0be4d-119">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="0be4d-120">Identificazione delle funzioni nelle DLL</span><span class="sxs-lookup"><span data-stu-id="0be4d-120">Identifying Functions in DLLs</span></span>](identifying-functions-in-dlls.md)
- [<span data-ttu-id="0be4d-121">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="0be4d-121">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="0be4d-122">Chiamata a una funzione di DLL</span><span class="sxs-lookup"><span data-stu-id="0be4d-122">Calling a DLL Function</span></span>](calling-a-dll-function.md)
