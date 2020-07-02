---
title: Funzioni di callback
description: Leggere le informazioni sulle funzioni di callback, ovvero codice con un'applicazione gestita che consente a una funzione di DLL non gestita di completare un'attività.
ms.date: 03/30/2017
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
ms.openlocfilehash: e28756b5ed935aff83363b38d6f33982e87718b2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621717"
---
# <a name="callback-functions"></a><span data-ttu-id="7b7c3-103">Funzioni di callback</span><span class="sxs-lookup"><span data-stu-id="7b7c3-103">Callback Functions</span></span>
<span data-ttu-id="7b7c3-104">Una funzione di callback è il codice di un'applicazione gestita che agevola una funzione di DLL non gestita nel completamento di un'attività.</span><span class="sxs-lookup"><span data-stu-id="7b7c3-104">A callback function is code within a managed application that helps an unmanaged DLL function complete a task.</span></span> <span data-ttu-id="7b7c3-105">Le chiamate a una funzione di callback passano indirettamente da un'applicazione gestita a una funzione di DLL, per poi tornare nuovamente all'implementazione gestita.</span><span class="sxs-lookup"><span data-stu-id="7b7c3-105">Calls to a callback function pass indirectly from a managed application, through a DLL function, and back to the managed implementation.</span></span> <span data-ttu-id="7b7c3-106">Alcune delle numerose funzioni di DLL chiamate tramite platform invoke richiedono, per essere eseguite in modo corretto, una funzione di callback nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="7b7c3-106">Some of the many DLL functions called with platform invoke require a callback function in managed code to run properly.</span></span>  
  
 <span data-ttu-id="7b7c3-107">Nella maggior parte dei casi, per chiamare una funzione di DLL dal codice gestito, si crea e si usa una definizione gestita della funzione.</span><span class="sxs-lookup"><span data-stu-id="7b7c3-107">To call most DLL functions from managed code, you create a managed definition of the function and then call it.</span></span> <span data-ttu-id="7b7c3-108">Il processo è semplice.</span><span class="sxs-lookup"><span data-stu-id="7b7c3-108">The process is straightforward.</span></span>  
  
 <span data-ttu-id="7b7c3-109">L'utilizzo di una funzione di DLL che richiede una funzione di callback prevede alcuni passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="7b7c3-109">Using a DLL function that requires a callback function has some additional steps.</span></span> <span data-ttu-id="7b7c3-110">In primo luogo è necessario determinare se la funzione richiede un callback controllando la documentazione relativa alla funzione.</span><span class="sxs-lookup"><span data-stu-id="7b7c3-110">First, you must determine whether the function requires a callback by looking at the documentation for the function.</span></span> <span data-ttu-id="7b7c3-111">Successivamente occorre creare la funzione di callback nell'applicazione gestita.</span><span class="sxs-lookup"><span data-stu-id="7b7c3-111">Next, you have to create the callback function in your managed application.</span></span> <span data-ttu-id="7b7c3-112">Infine si chiama la funzione di DLL passandole come argomento un puntatore alla funzione di callback.</span><span class="sxs-lookup"><span data-stu-id="7b7c3-112">Finally, you call the DLL function, passing a pointer to the callback function as an argument.</span></span>

 <span data-ttu-id="7b7c3-113">La figura seguente presenta una riepilogo della funzione di callback e dei passaggi di implementazione:</span><span class="sxs-lookup"><span data-stu-id="7b7c3-113">The following illustration summarizes the callback function and implementation steps:</span></span>  
  
 ![Diagramma che illustra il processo di callback di platform invoke.](./media/callback-functions/platform-invoke-callback-process.gif)  
  
 <span data-ttu-id="7b7c3-115">Le funzioni di callback sono ideali per i casi in cui un'attività viene eseguita ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="7b7c3-115">Callback functions are ideal for use in situations in which a task is performed repeatedly.</span></span> <span data-ttu-id="7b7c3-116">Un altro utilizzo comune è quello con le funzioni di enumerazione, ad esempio **EnumFontFamilies**, **EnumPrinters** e **EnumWindows** nell'API Windows.</span><span class="sxs-lookup"><span data-stu-id="7b7c3-116">Another common usage is with enumeration functions, such as **EnumFontFamilies**, **EnumPrinters**, and **EnumWindows** in the Windows API.</span></span> <span data-ttu-id="7b7c3-117">La funzione **EnumWindows** esegue l'enumerazione di tutte le finestre esistenti nel computer, chiamando la funzione di callback per eseguire un'attività su ogni finestra.</span><span class="sxs-lookup"><span data-stu-id="7b7c3-117">The **EnumWindows** function enumerates through all existing windows on your computer, calling the callback function to perform a task on each window.</span></span> <span data-ttu-id="7b7c3-118">Per istruzioni e per un esempio, vedere [Procedura: Implementare funzioni di callback](how-to-implement-callback-functions.md).</span><span class="sxs-lookup"><span data-stu-id="7b7c3-118">For instructions and an example, see [How to: Implement Callback Functions](how-to-implement-callback-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b7c3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b7c3-119">See also</span></span>

- [<span data-ttu-id="7b7c3-120">Procedura: Implementare funzioni di callback</span><span class="sxs-lookup"><span data-stu-id="7b7c3-120">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)
- [<span data-ttu-id="7b7c3-121">Chiamata a una funzione di DLL</span><span class="sxs-lookup"><span data-stu-id="7b7c3-121">Calling a DLL Function</span></span>](calling-a-dll-function.md)
