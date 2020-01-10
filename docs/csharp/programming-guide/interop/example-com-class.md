---
title: Esempio di classe COM - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- examples [C#], COM classes
- COM, exposing Visual C# objects to
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
ms.openlocfilehash: 6af85d0314a44acbde0996cecbe6dad82cdcc8db
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712078"
---
# <a name="example-com-class-c-programming-guide"></a><span data-ttu-id="d6bf3-102">Esempio di classe COM (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d6bf3-102">Example COM Class (C# Programming Guide)</span></span>
<span data-ttu-id="d6bf3-103">Di seguito è riportato un esempio di una classe esposta come oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-103">The following is an example of a class that you would expose as a COM object.</span></span> <span data-ttu-id="d6bf3-104">Dopo aver inserito questo codice in un file con estensione cs e averlo aggiunto al progetto, impostare la proprietà **Registra per interoperabilità COM** su **True**.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-104">After this code has been placed in a .cs file and added to your project, set the **Register for COM Interop** property to **True**.</span></span> <span data-ttu-id="d6bf3-105">Per altre informazioni, vedere [Procedura: Registrare un componente per l'interoperabilità COM](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d6bf3-105">For more information, see [How to: Register a Component for COM Interop](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100)).</span></span>
  
 <span data-ttu-id="d6bf3-106">Per esporre gli oggetti Visual C# a COM è necessario dichiarare un'interfaccia di classe e un'interfaccia di eventi, se necessaria, oltre alla classe stessa.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-106">Exposing Visual C# objects to COM requires declaring a class interface, an events interface if it is required, and the class itself.</span></span> <span data-ttu-id="d6bf3-107">Per essere visibili per COM i membri della classe devono rispettare le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6bf3-107">Class members must follow these rules to be visible to COM:</span></span>  
  
- <span data-ttu-id="d6bf3-108">La classe deve essere public.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-108">The class must be public.</span></span>  
  
- <span data-ttu-id="d6bf3-109">Le proprietà, i metodi e gli eventi devono essere public.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-109">Properties, methods, and events must be public.</span></span>  
  
- <span data-ttu-id="d6bf3-110">Le proprietà e i metodi devono essere dichiarati nell'interfaccia di classe.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-110">Properties and methods must be declared on the class interface.</span></span>  
  
- <span data-ttu-id="d6bf3-111">Gli eventi devono essere dichiarati nell'interfaccia eventi.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-111">Events must be declared in the event interface.</span></span>  
  
 <span data-ttu-id="d6bf3-112">Gli altri membri public della classe non dichiarati in queste interfacce non saranno visibili per COM ma lo saranno per altri oggetti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-112">Other public members in the class that are not declared in these interfaces will not be visible to COM, but they will be visible to other .NET Framework objects.</span></span>  
  
 <span data-ttu-id="d6bf3-113">Per esporre le proprietà e i metodi a COM, è necessario dichiararli nell'interfaccia di classe e contrassegnarli con un attributo `DispId`, nonché implementarli nella classe stessa.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-113">To expose properties and methods to COM, you must declare them on the class interface and mark them with a `DispId` attribute, and implement them in the class.</span></span> <span data-ttu-id="d6bf3-114">L'ordine con cui i membri vengono dichiarati nell'interfaccia è quello usato per la vtable COM.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-114">The order in which the members are declared in the interface is the order used for the COM vtable.</span></span>  
  
 <span data-ttu-id="d6bf3-115">Per esporre gli eventi all'esterno della classe, è necessario dichiararli nell'interfaccia eventi e contrassegnarli con un attributo `DispId`.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-115">To expose events from your class, you must declare them on the events interface and mark them with a `DispId` attribute.</span></span> <span data-ttu-id="d6bf3-116">La classe non deve implementare questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-116">The class should not implement this interface.</span></span>  
  
 <span data-ttu-id="d6bf3-117">La classe implementa l'interfaccia di classe. È in grado di implementare più interfacce, ma la prima implementazione sarà quella dell'interfaccia di classe predefinita.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-117">The class implements the class interface; it can implement more than one interface, but the first implementation will be the default class interface.</span></span> <span data-ttu-id="d6bf3-118">A questo punto, implementare i metodi e le proprietà esposte a COM,</span><span class="sxs-lookup"><span data-stu-id="d6bf3-118">Implement the methods and properties exposed to COM here.</span></span> <span data-ttu-id="d6bf3-119">che devono essere contrassegnati come public e corrispondere alle dichiarazioni presenti nell'interfaccia di classe.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-119">They must be marked public and must match the declarations in the class interface.</span></span> <span data-ttu-id="d6bf3-120">Dichiarare anche gli eventi generati dalla classe,</span><span class="sxs-lookup"><span data-stu-id="d6bf3-120">Also, declare the events raised by the class here.</span></span> <span data-ttu-id="d6bf3-121">che devono essere contrassegnati come public e corrispondere alle dichiarazioni presenti nell'interfaccia eventi.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-121">They must be marked public and must match the declarations in the events interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6bf3-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6bf3-122">Example</span></span>  
 [!code-csharp[csProgGuideInterop#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/ExampleCOM.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="d6bf3-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6bf3-123">See also</span></span>

- [<span data-ttu-id="d6bf3-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d6bf3-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d6bf3-125">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="d6bf3-125">Interoperability</span></span>](./index.md)
- [<span data-ttu-id="d6bf3-126">Pagina Compilazione, Creazione progetti (C#)</span><span class="sxs-lookup"><span data-stu-id="d6bf3-126">Build Page, Project Designer (C#)</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)
