---
title: Chiamata a una funzione di DLL
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b842f44711d38a996b9d710dbe8bd369d30c5443
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71051877"
---
# <a name="calling-a-dll-function"></a><span data-ttu-id="8c03f-102">Chiamata a una funzione di DLL</span><span class="sxs-lookup"><span data-stu-id="8c03f-102">Calling a DLL Function</span></span>
<span data-ttu-id="8c03f-103">Anche se le chiamate a funzioni di DLL non gestite sono quasi identiche alle chiamate ad altro codice gestito, esistono alcune differenze che possono rendere apparentemente poco chiaro l'uso delle funzioni di DLL.</span><span class="sxs-lookup"><span data-stu-id="8c03f-103">Although calling unmanaged DLL functions is nearly identical to calling other managed code, there are differences that can make DLL functions seem confusing at first.</span></span> <span data-ttu-id="8c03f-104">In questa sezione vengono presentati argomenti che descrivono alcuni aspetti meno comuni delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="8c03f-104">This section introduces topics that describe some of the unusual calling-related issues.</span></span>  
  
 <span data-ttu-id="8c03f-105">Le strutture che vengono restituite dalle chiamate platform invoke devono essere tipi di dati contenenti la stessa rappresentazione in codice gestito e non gestito.</span><span class="sxs-lookup"><span data-stu-id="8c03f-105">Structures that are returned from platform invoke calls must be data types that have the same representation in managed and unmanaged code.</span></span> <span data-ttu-id="8c03f-106">Questi tipi sono definiti *tipi copiabili da BLT* perché non richiedono la conversione. Vedere [Tipi copiabili e non copiabili da BLT](blittable-and-non-blittable-types.md).</span><span class="sxs-lookup"><span data-stu-id="8c03f-106">Such types are called *blittable types* because they do not require conversion (see [Blittable and Non-Blittable Types](blittable-and-non-blittable-types.md)).</span></span> <span data-ttu-id="8c03f-107">Per chiamare una funzione con una struttura non copiabile da BLT come tipo restituito, è possibile definire un tipo di helper copiabile da BLT della stessa dimensione del tipo non copiabile da BLT e convertire i dati dopo la restituzione della funzione.</span><span class="sxs-lookup"><span data-stu-id="8c03f-107">To call a function that has a non-blittable structure as its return type, you can define a blittable helper type of the same size as the non-blittable type and convert the data after the function returns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c03f-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="8c03f-108">In This Section</span></span>  
 [<span data-ttu-id="8c03f-109">Passaggio di strutture</span><span class="sxs-lookup"><span data-stu-id="8c03f-109">Passing Structures</span></span>](passing-structures.md)  
 <span data-ttu-id="8c03f-110">Identifica le problematiche relative al passaggio di strutture di dati con un layout predefinito.</span><span class="sxs-lookup"><span data-stu-id="8c03f-110">Identifies the issues of passing data structures with a predefined layout.</span></span>  
  
 [<span data-ttu-id="8c03f-111">Funzioni di callback</span><span class="sxs-lookup"><span data-stu-id="8c03f-111">Callback Functions</span></span>](callback-functions.md)  
 <span data-ttu-id="8c03f-112">Include informazioni di base sulle funzioni di callback.</span><span class="sxs-lookup"><span data-stu-id="8c03f-112">Provides basic information about callback functions.</span></span>  
  
 [<span data-ttu-id="8c03f-113">Procedura: Implementare funzioni di callback</span><span class="sxs-lookup"><span data-stu-id="8c03f-113">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)  
 <span data-ttu-id="8c03f-114">Descrive come implementare funzioni di callback nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="8c03f-114">Describes how to implement callback functions in managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8c03f-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="8c03f-115">Related Sections</span></span>  
 [<span data-ttu-id="8c03f-116">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="8c03f-116">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="8c03f-117">Descrive come chiamare funzioni di DLL non gestite con platform invoke.</span><span class="sxs-lookup"><span data-stu-id="8c03f-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="8c03f-118">Marshalling dei dati con platform invoke</span><span class="sxs-lookup"><span data-stu-id="8c03f-118">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)  
 <span data-ttu-id="8c03f-119">Descrive come dichiarare i parametri dei metodi e passare gli argomenti alle funzioni esportate dalle librerie non gestite.</span><span class="sxs-lookup"><span data-stu-id="8c03f-119">Describes how to declare method parameters and pass arguments to functions exported by unmanaged libraries.</span></span>
