---
title: 'Procedura: Generare eventi della classe di base in classi derivate - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: 11f34e230a1f953ba3d886e416f1ece4253e3c8d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239618"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="e8198-102">Procedura: Generare eventi della classe di base in classi derivate (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e8198-102">How to: Raise Base Class Events in Derived Classes (C# Programming Guide)</span></span>
<span data-ttu-id="e8198-103">L'esempio seguente illustra il metodo standard di dichiarazione degli eventi in una classe base in modo che possano essere generati anche dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="e8198-103">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="e8198-104">Questo modello è usato spesso nelle classi Windows Forms nella libreria di classi [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8198-104">This pattern is used extensively in Windows Forms classes in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library.</span></span>  
  
 <span data-ttu-id="e8198-105">Quando si crea una classe che può essere usata come classe base di altre classi, è necessario tenere presente che gli eventi sono un tipo speciale di delegati che possono essere richiamati solo dall'interno della classe che li ha dichiarati.</span><span class="sxs-lookup"><span data-stu-id="e8198-105">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="e8198-106">Le classi derivate non possono richiamare direttamente gli eventi dichiarati all'interno della classe base.</span><span class="sxs-lookup"><span data-stu-id="e8198-106">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="e8198-107">Nonostante sia necessario a volte un evento che possa essere generato solo dalla classe base, nella maggior parte dei casi è opportuno consentire alla classe derivata di richiamare eventi della classe base.</span><span class="sxs-lookup"><span data-stu-id="e8198-107">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="e8198-108">A tale scopo, è possibile creare un metodo di chiamata protetto nella classe base che esegue il wrapping dell'evento.</span><span class="sxs-lookup"><span data-stu-id="e8198-108">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="e8198-109">Le classi derivate possono richiamare indirettamente l'evento richiamando o eseguendo l'override di questo metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e8198-109">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8198-110">Non dichiarare eventi virtuali in una classe base ed eseguire l'override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="e8198-110">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="e8198-111">Il compilatore C# non è in grado di gestirli correttamente e non è possibile prevedere se un sottoscrittore dell'evento derivato sottoscriverà effettivamente l'evento della classe base.</span><span class="sxs-lookup"><span data-stu-id="e8198-111">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8198-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8198-112">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-raise-base-class-events-in-derived-classes_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e8198-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8198-113">See Also</span></span>

- [<span data-ttu-id="e8198-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e8198-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e8198-115">Eventi</span><span class="sxs-lookup"><span data-stu-id="e8198-115">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="e8198-116">Delegati</span><span class="sxs-lookup"><span data-stu-id="e8198-116">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
- [<span data-ttu-id="e8198-117">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="e8198-117">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [<span data-ttu-id="e8198-118">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e8198-118">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
