---
title: Come generare eventi di classe base nelle classi derivate-guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: e2d2dfc2809a4de1756bfc362880eebc79076b94
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84240629"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="8a265-102">Come generare eventi di classe base nelle classi derivate (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="8a265-102">How to raise base class events in derived classes (C# Programming Guide)</span></span>
<span data-ttu-id="8a265-103">L'esempio seguente illustra il metodo standard di dichiarazione degli eventi in una classe base in modo che possano essere generati anche dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="8a265-103">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="8a265-104">Questo modello viene ampiamente usato nelle classi Windows Forms nelle librerie di classi .NET.</span><span class="sxs-lookup"><span data-stu-id="8a265-104">This pattern is used extensively in Windows Forms classes in the .NET class libraries.</span></span>  
  
 <span data-ttu-id="8a265-105">Quando si crea una classe che può essere usata come classe base di altre classi, è necessario tenere presente che gli eventi sono un tipo speciale di delegati che possono essere richiamati solo dall'interno della classe che li ha dichiarati.</span><span class="sxs-lookup"><span data-stu-id="8a265-105">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="8a265-106">Le classi derivate non possono richiamare direttamente gli eventi dichiarati all'interno della classe base.</span><span class="sxs-lookup"><span data-stu-id="8a265-106">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="8a265-107">Nonostante sia necessario a volte un evento che possa essere generato solo dalla classe base, nella maggior parte dei casi è opportuno consentire alla classe derivata di richiamare eventi della classe base.</span><span class="sxs-lookup"><span data-stu-id="8a265-107">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="8a265-108">A tale scopo, è possibile creare un metodo di chiamata protetto nella classe base che esegue il wrapping dell'evento.</span><span class="sxs-lookup"><span data-stu-id="8a265-108">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="8a265-109">Le classi derivate possono richiamare indirettamente l'evento richiamando o eseguendo l'override di questo metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="8a265-109">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a265-110">Non dichiarare eventi virtuali in una classe base ed eseguire l'override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="8a265-110">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="8a265-111">Il compilatore C# non è in grado di gestirli correttamente e non è possibile prevedere se un sottoscrittore dell'evento derivato sottoscriverà effettivamente l'evento della classe base.</span><span class="sxs-lookup"><span data-stu-id="8a265-111">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a265-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a265-112">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8a265-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a265-113">See also</span></span>

- [<span data-ttu-id="8a265-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8a265-114">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8a265-115">Events</span><span class="sxs-lookup"><span data-stu-id="8a265-115">Events</span></span>](./index.md)
- [<span data-ttu-id="8a265-116">Delegati</span><span class="sxs-lookup"><span data-stu-id="8a265-116">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="8a265-117">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="8a265-117">Access Modifiers</span></span>](../classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="8a265-118">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="8a265-118">Creating Event Handlers in Windows Forms</span></span>](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
